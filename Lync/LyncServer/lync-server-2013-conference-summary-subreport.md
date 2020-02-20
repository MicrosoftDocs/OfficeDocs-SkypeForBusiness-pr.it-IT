---
title: 'Lync Server 2013: sottorapporto riepilogativo conferenze'
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
ms.openlocfilehash: 9cc0e61333b491a4d28e42167a9e60823e0331d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a>Sottoreport riepilogativo conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-06_

Il sottorapporto riepilogativo conferenze offre una visualizzazione generale delle sessioni di conferenza non riuscite. Tali sessioni vengono ulteriormente suddivise per tipo: sessioni Focus e sessioni MCU.

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più appropriato, nonché visualizzare i dati restituiti in diversi modi. Nella tabella che segue sono elencati i filtri che è possibile usare con il sottorapporto riepilogativo conferenze.

### <a name="conference-summary-subreport-filters"></a>Filtri del sottorapporto riepilogativo conferenze

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</p>
<p>07/07/2012 13.00</p>
<p>Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane iniziano sempre con il lunedì e terminano con la domenica.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</p>
<p>07/07/2012 13.00</p>
<p>Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane vanno sempre dal lunedì alla domenica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su <strong>[Tutto]</strong> per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel sottoreport riepilogativo conferenze.

### <a name="conference-summary-subreport-metrics"></a>Metriche del sottorapporto riepilogativo conferenze

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Elemento utilizzabile per eseguire l'ordinamento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Totale conferenze</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze effettuate.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale sessioni conferenza</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni di conferenza. Una singola conferenza può includere più sessioni, ad esempio una sessione Focus e una sessione MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Frequenza generale errori sessione</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di tutte le conferenze non riuscite.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessioni Focus</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni Focus.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Frequenza errori Focus</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di sessioni Focus non riuscite.</p></td>
</tr>
<tr class="even">
<td><p>Sessioni MCU</p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Frequenza errori MCU</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di sessioni MCU non riuscite.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessioni MCU per modalità</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni MCU, raggruppate per modalità (ad esempio IM Conferencing).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Frequenza errori per modalità</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di sessioni MCU non riuscite, raggruppate per modalità (ad esempio IM Conferencing).</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

