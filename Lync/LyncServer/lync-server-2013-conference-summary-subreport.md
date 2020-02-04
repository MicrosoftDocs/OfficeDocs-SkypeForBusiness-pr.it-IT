---
title: 'Lync Server 2013: sottoreport riepilogo conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2537cbe959639baee6f0f986b3faea1ebd79b5a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a>Sottoreport riepilogo conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-06_

Il sottoreport riepilogo conferenze offre una visualizzazione complessiva delle sessioni di conferenza non riuscite. Queste sessioni non riuscite sono ulteriormente suddivise per tipo di sessione: sessioni di stato di attivazione e sessioni MCU.

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il sottoreport di riepilogo conferenza.

### <a name="conference-summary-subreport-filters"></a>Filtri per i sottoreport di riepilogo conferenza

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
<td><p><strong>Da</strong></p></td>
<td><p>Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane si eseguono sempre da domenica a sabato.</p></td>
</tr>
<tr class="even">
<td><p><strong>A</strong></p></td>
<td><p>Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane si eseguono sempre da domenica a sabato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su <strong>[tutti]</strong> per visualizzare i dati per tutti i pool. Questo elenco a discesa viene compilato automaticamente in base ai record nel database.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel sottoreport di riepilogo conferenza.

### <a name="conference-summary-subreport-metrics"></a>Metriche del sottoreport di riepilogo conferenza

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Si può ordinare su questo elemento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Totale conferenze</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze organizzate.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale delle sessioni di conferenza</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni di conferenza. Una singola conferenza può avere più sessioni; ad esempio, una conferenza può includere sia una sessione dello stato di attivazione che una sessione MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasso di errore complessivo della sessione</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di tutte le conferenze non riuscite.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessioni di stato attiva</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni di stato attivate.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasso di errore dello stato di avanzamento</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale delle sessioni di stato di attivazione non riuscite.</p></td>
</tr>
<tr class="even">
<td><p>Sessioni MCU</p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasso di errore MCU</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di sessioni MCU non riuscite.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessioni MCU per modalità</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni MCU, raggruppate per modalità (ad esempio, servizi di conferenza di messaggistica istantanea).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasso di errore per modalità</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di sessioni MCU non riuscite, raggruppate per modalità (ad esempio, servizi di conferenza di messaggistica istantanea).</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

