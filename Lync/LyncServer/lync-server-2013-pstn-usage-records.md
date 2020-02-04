---
title: 'Lync Server 2013: Record utilizzo PSTN'
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
ms.openlocfilehash: 5909494b4e4b6901964a7642481302ca221fe086
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a>Record utilizzo PSTN in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-23_

La pianificazione dei record di utilizzo PSTN consiste principalmente nell'elencare tutte le autorizzazioni di chiamata attualmente in vigore nell'organizzazione, dall'amministratore delegato a lavoratori temporanei, consulenti e personale contingente. Questo processo offre anche l'opportunità di riesaminare le autorizzazioni di chiamata esistenti e di modificarle. È possibile creare record di utilizzo PSTN solo per le autorizzazioni di chiamata applicabili agli utenti di VoIP aziendale previsti, ma una soluzione migliore a lungo raggio può essere quella di creare record di utilizzo PSTN per tutte le autorizzazioni di chiamata, indipendentemente dal fatto che alcuni potrebbero non essere attualmente si applicano al gruppo di utenti che deve essere abilitato per VoIP aziendale. Se le autorizzazioni di chiamata cambiano o vengono aggiunti nuovi utenti con autorizzazioni di chiamata diverse, saranno già stati creati i record di utilizzo PSTN necessari.

La tabella seguente mostra una tipica tabella di utilizzo PSTN.

### <a name="pstn-usage-records"></a>Record utilizzo PSTN

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attributo Phone</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Locale</p></td>
<td><p>Chiamate locali</p></td>
</tr>
<tr class="even">
<td><p>Lunga distanza</p></td>
<td><p>Chiamate interurbane</p></td>
</tr>
<tr class="odd">
<td><p>Internazionale</p></td>
<td><p>Chiamate internazionali</p></td>
</tr>
<tr class="even">
<td><p>Delhi</p></td>
<td><p>Dipendenti a tempo pieno di Delhi</p></td>
</tr>
<tr class="odd">
<td><p>Redmond</p></td>
<td><p>Dipendenti a tempo pieno Redmond</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>Dipendenti temporanei Redmond</p></td>
</tr>
<tr class="odd">
<td><p>Zurigo</p></td>
<td><p>Dipendenti a tempo pieno di Zurigo</p></td>
</tr>
</tbody>
</table>


Da solo, i record di utilizzo PSTN non eseguono alcuna operazione. Affinché funzioni, è necessario associarle con le operazioni seguenti:

  - Criteri vocali, assegnati agli utenti.

  - Route, assegnate ai numeri di telefono.

Per informazioni dettagliate sui criteri vocali e le route, vedere [criteri vocali in Lync server 2013](lync-server-2013-voice-policies.md) e [route vocali in Lync Server 2013](lync-server-2013-voice-routes.md). Per informazioni dettagliate su come crearle e configurarle, vedere [configurazione delle route vocali per le chiamate in uscita in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).

</div>

<span> </span>

</div>

</div>

</div>

