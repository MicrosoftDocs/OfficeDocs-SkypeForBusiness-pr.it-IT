---
title: 'Lync Server 2013: tabella ConferenceJoinTimeThresholds'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d6ce43adee4c00a945325cf31c4194816e7ee14
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a>Tabella ConferenceJoinTimeThresholds in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

La tabella ConferenceJoinTimeThresholds include i limiti di classificazione utilizzati dal rapporto riepilogativo Tempo di partecipazione alla conferenza. Questo rapporto riepiloga la quantità di tempo richiesto agli utenti per partecipare a una conferenza. I valori temporali vengono riportati come media e in una delle categorie seguenti:

  - Meno di 2 secondi.

  - Tra 2 e 5 secondi.

  - Tra 5 e 10 secondi.

  - Più di 10 secondi.

La tabella ConferenceJoinTimeThresholds include i valori di classificazione 2 secondi, 5 secondi e 10 secondi.

Questa tabella è stata introdotta in Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Tipo di dati</th>
<th>Chiave/indice</th>
<th>Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ThresholdId</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>Identificatore univoco della classificazione.</p></td>
</tr>
<tr class="even">
<td><p><strong>ThresholdValue:</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Limite superiore per la classificazione. I valori consentiti sono:</p>
<ol>
<li><p>2</p></li>
<li><p>5</p></li>
<li><p>10 </p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

