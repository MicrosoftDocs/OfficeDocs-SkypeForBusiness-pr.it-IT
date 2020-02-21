---
title: 'Lync Server 2013: rapporto tempo di partecipazione alla conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76388655fc8ed893e09b192ae24c7807b46f9f6c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a>Rapporto tempo di partecipazione alla conferenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-04-23_

Il rapporto Tempo di partecipazione alla conferenza consente di determinare il tempo richiesto agli utenti per partecipare a una conferenza. Nel rapporto viene visualizzato il tempo medio di partecipazione (in millisecondi) e sono inoltre disponibili informazioni suddivise che indicano il numero di utenti in grado di partecipare a una conferenza in massimo 2 secondi, il numero di utenti che hanno impiegato tra 2 e 5 secondi per partecipare e così via.

<div>

## <a name="accessing-the-conference-join-time-report"></a>Accesso al rapporto Tempo di partecipazione alla conferenza

È possibile accedere al rapporto Tempo di partecipazione alla conferenza dalla home page Relazioni monitoraggio.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il rapporto Tempo di partecipazione alla conferenza.

### <a name="conference-join-time-report-filters"></a>Filtri del rapporto Tempo di partecipazione alla conferenza

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
<p>Le settimane vanno sempre dal lunedì alla domenica.</p></td>
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
<td><p><strong>Intervallo</strong></p></td>
<td><p>Selezionare uno dei seguenti:</p>
<ul>
<li><p>Orario (è possibile visualizzare un massimo di 25 ore)</p></li>
<li><p>Giornaliero (è possibile visualizzare un massimo di 31 giorni)</p></li>
<li><p>Settimanale (è possibile visualizzare un massimo di 12 settimane)</p></li>
<li><p>Mensile (è possibile visualizzare un massimo di 12 mesi)</p></li>
</ul>
<p>Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo giornaliero con data di inizio 07/07/2012 e data di fine 28/02/2012, verranno visualizzati i dati per i giorni da 07/08/2012 ore 00.00 a 07/09/2012 ore 00:00 (per un totale di 31 giorni).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su <strong>[Tutto]</strong> per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni conferenza</strong></p></td>
<td><p>Tipo di sessione. I valori consentiti sono:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Sessioni di messa a fuoco (lo stato attivo è il criterio centrale e il responsabile dello stato per le riunioni online e coordina tutti gli aspetti di una conferenza</p></li>
<li><p>Condivisione applicazioni</p></li>
<li><p>Conferenze audio/video</p></li>
</ul>
<p>Se si seleziona [Tutto], nella parte superiore del rapporto verrà visualizzato il tempo totale di partecipazione alla conferenza. Si noti che questi totali sono riferiti solo alle conferenze pianificate tramite Microsoft Exchange o Microsoft Outlook.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

La tabella seguente elenca le informazioni disponibili nel rapporto Tempo di partecipazione alla conferenza.

### <a name="conference-join-time-report-metrics"></a>Metriche del rapporto Tempo di partecipazione alla conferenza

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
<td><p><strong>Data</strong></p>
<p>Il titolo effettivo di questa metrica varia in base all'intervallo selezionato.</p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui ha avuto luogo la conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale sessioni</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni, comprendente le sessioni con esito positivo, le sessioni con esito negativo (per errori sia previsti che imprevisti) e le sessioni senza categoria.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Media (ms)</strong></p></td>
<td><p>No</p></td>
<td><p>Quantità media di tempo (in millisecondi) impiegato dai partecipanti per partecipare alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessioni &lt; 2 secondi, volume</strong></p></td>
<td><p>No</p></td>
<td><p>Numero di partecipanti che sono riusciti a partecipare alla conferenza in meno di 2 secondi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni &lt; 2 secondi, percentuale</strong></p></td>
<td><p>No</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>Sessioni 2-5 secondi, Volume</strong></p></td>
<td><p>No</p></td>
<td><p>Numero di partecipanti che hanno impiegato da 2 a 5 secondi per partecipare alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni 2-5 secondi, Percentuale</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale del numero totale di partecipanti che hanno impiegato da 2 a 5 secondi per partecipare alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessioni 5-10 secondi, Volume</strong></p></td>
<td><p>No</p></td>
<td><p>Numero di partecipanti che hanno impiegato da 5 a 10 secondi per partecipare alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni 5-10 secondi, Percentuale</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale del numero totale di partecipanti che hanno impiegato da 5 a 10 secondi per partecipare alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessioni &gt; 10 secondi, volume</strong></p></td>
<td><p>No</p></td>
<td><p>Numero di partecipanti che hanno impiegato più di 10 secondi per partecipare alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni &gt; 10 secondi, percentuale</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale del numero totale di partecipanti che hanno impiegato più di 10 secondi per partecipare alla conferenza.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

