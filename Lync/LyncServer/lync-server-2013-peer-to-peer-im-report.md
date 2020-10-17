---
title: 'Lync Server 2013: rapporto di messaggistica istantanea peer-to-peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16098a1d549c155f9a642f7e68f056f07973217d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524373"
---
# <a name="peer-to-peer-im-report-in-lync-server-2013"></a>Rapporto di messaggistica istantanea peer-to-peer in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Nel rapporto di messaggistica istantanea peer-to-peer vengono fornite informazioni sulla tendenza delle sessioni di messaggistica istantanea suddivise per pool e per tipo di autenticazione. Il rapporto può inoltre indicare il numero totale di sessioni organizzate oppure segnalare il numero complessivo di messaggi istantanei inviati nel periodo specificato (ad esempio, Giorno o Ora).

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a>Accesso al rapporto di messaggistica istantanea peer-to-peer

È possibile accedere al rapporto di messaggistica istantanea peer-to-peer solo aprendo il [rapporto riepilogativo attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) e quindi facendo clic su una delle metriche seguenti:

  - Totale sessioni di messaggistica istantanea peer-to-peer

  - Totale messaggi istantanei peer-to-peer

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>Utilizzo ottimale del rapporto di messaggistica istantanea peer-to-peer

Nel rapporto di messaggistica istantanea peer-to-peer vengono mostrati, per impostazione predefinita, il numero di messaggi per ora (o giorno, a seconda dell'impostazione configurata). Tuttavia, è anche possibile scegliere di visualizzare il giorno in base alle sessioni per ora. In tal caso, fare clic su **Nascondi/mostra parametri** nell'angolo superiore destro della finestra relativa ai rapporti e quindi fare clic su **Numero di sessioni** nell'elenco **Rapporto di**.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più mirato o di visualizzare i dati restituiti in diversi modi. Nella tabella seguente sono riportati i filtri utilizzabili con il rapporto di messaggistica istantanea peer-to-peer.

### <a name="peer-to-peer-im-report-filters"></a>Filtri per il rapporto di messaggistica istantanea peer-to-peer

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
<td><p><strong>From</strong></p></td>
<td><p>Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di inizio come segue:</p>
<p>07/07/2012 13.00</p>
<p>Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare i dati in base alla settimana o al mese, immettere una data che rientri nella settimana o nel mese desiderato (non è necessario immettere il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane vanno sempre dal lunedì alla domenica.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di fine come segue:</p>
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
<li><p>Mensile (possono essere visualizzati al massimo 12 mesi)</p></li>
</ul>
<p>Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori, a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo Giornaliero con 07/07/2012 come data di inizio e 28/02/2012 come data di fine, verranno visualizzati i dati dalla mezzanotte del 7 agosto 2012 alla mezzanotte del 7 settembre 2012, ovvero i dati per un totale di 31 giorni.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rapporto di</strong></p></td>
<td><p>Indica i valori da utilizzare nel rapporto. Selezionare una delle impostazioni seguenti:</p>
<ul>
<li><p>Numero di sessioni</p></li>
<li><p>Numero messaggi</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Metrica delle sessioni di messaggistica istantanea peer-to-peer in base al pool

Nella tabella seguente vengono riportate le informazioni fornite nel rapporto di messaggistica istantanea peer-to-peer.

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Metrica del rapporto di messaggistica istantanea peer-to-peer in base al pool

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Elemento utilizzabile per eseguire l'ordinamento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>No</p></td>
<td><p>Nome del pool di registrazione o del server perimetrale.</p></td>
</tr>
<tr class="even">
<td><p><strong>Data/ora</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui hanno avuto luogo le sessioni.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni o di messaggi.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Metrica delle sessioni di messaggistica istantanea peer-to-peer in base al tipo di autenticazione

Nella tabella seguente vengono riportate le informazioni fornite nel rapporto di messaggistica istantanea peer-to-peer per ogni tipo di autenticazione utilizzato dai partecipanti a una sessione peer-to-peer.

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Metrica delle sessioni di messaggistica istantanea peer-to-peer in base al tipo di autenticazione

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Elemento utilizzabile per eseguire l'ordinamento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Tipo di autenticazione</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo di autenticazione utilizzato dai partecipanti alla sessione. I valori validi in genere sono i seguenti:</p>
<ul>
<li><p>Enterprise</p></li>
<li><p>Federati</p></li>
<li><p>PIC</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Data/ora</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui hanno avuto luogo le sessioni.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni o di messaggi.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

