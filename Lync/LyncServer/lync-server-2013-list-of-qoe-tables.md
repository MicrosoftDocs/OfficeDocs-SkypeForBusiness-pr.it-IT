---
title: 'Lync Server 2013: elenco delle tabelle QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b15cab5a39e74cbbc1813fb9d4f5ce56d777408
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a>Elenco delle tabelle QoE in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

Lo schema del database è costituito dalle tabelle seguenti.

**Tabelle di supporto**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>tavolo</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Tabella AppSharingMetricsThreshold in Lync Server 2013</a></p></td>
<td><p>Archivia i valori ottimali e accettabili per le metriche sulla qualità delle esperienze utilizzate con la condivisione di applicazioni.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">Tabella CodecDescription in Lync Server 2013</a></p></td>
<td><p>Consente di mappare gli identificatori di codec univoci al codec corrispondente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">Tabella IPAddress in Lync Server 2013</a></p></td>
<td><p>Consente di eseguire il mapping degli indirizzi IP agli identificatori di indirizzi IP univoci utilizzati altrove nel database Quality of Experience.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">Tabella NetworkConnectionDetail in Lync Server 2013</a></p></td>
<td><p>Esegue il mapping dei tipi di connessione di rete agli identificatori di connessione di rete utilizzati in altri punti del database Quality of Experience.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">Tabella PurgeSettings (QoE) in Lync Server 2013</a></p></td>
<td><p>Archivia le informazioni che specificano se (e quando) i record di qualità di esperienza obsoleti verranno eliminati automaticamente dal database QoE.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">Tabella TraceRoute in Lync Server 2013</a></p></td>
<td><p>Archivia le informazioni di routing per le chiamate.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a></p></td>
<td><p>Questa tabella contiene il mapping degli identificatori degli agenti utente ai nomi descrittivi degli agenti.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">Tabella VideoMetricsThreshold in Lync Server 2013</a></p></td>
<td><p>Archivia valori ottimali e accettabili per le metriche sulla qualità delle esperienze utilizzate con le videochiamate.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">Tabella UserAgent in Lync Server 2013</a></p></td>
<td><p>Archivia le stringhe degli agenti utente SIP (Session Initiation Protocol) e i tipi UA utilizzati nelle sessioni audio e video.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">Tabella user in Lync Server 2013</a></p></td>
<td><p>Archivia gli URI degli utenti, delle conferenze e dei telefoni utilizzati nelle sessioni audio e video.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Tabella endpoint in Lync Server 2013</a></p></td>
<td><p>Archivia i nomi dei computer FQDN degli endpoint che partecipano alle sessioni audio e video.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Tabella del pool in Lync Server 2013</a></p></td>
<td><p>Archivia i nomi dei pool a cui appartengono i dati della metrica.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Tabella Device in Lync Server 2013</a></p></td>
<td><p>Archivia i dispositivi di acquisizione e i dispositivi di rendering utilizzati nelle chiamate audio/video.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Tabella QRTDDriver in Lync Server 2013</a></p></td>
<td><p>Archivia il driver per il dispositivo di acquisizione e il dispositivo di rendering utilizzati nelle chiamate audio/video.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Tabella conferenze in Lync Server 2013</a></p></td>
<td><p>Archivia gli URI di conferenza per gli scenari di conferenza o DialogID per altri scenari.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Tabella SessionCorrelation in Lync Server 2013</a></p></td>
<td><p>Consente di archiviare CorrelationID per le chiamate PSTN.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a></p></td>
<td><p>Archivia il codec utilizzato nelle chiamate audio/video.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Tabella AppliedBandwidthSource in Lync Server 2013</a></p></td>
<td><p>Archivia l'origine della larghezza di banda utilizzata nelle chiamate audio/video.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Tabella MacAddress in Lync Server 2013</a></p></td>
<td><p>Archivia l'indirizzo MAC degli endpoint che partecipano alle sessioni audio e video.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Tabella Dialog in Lync Server 2013</a></p></td>
<td><p>Archivia l'ID della finestra di dialogo delle sessioni audio e video.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Tabella Region in Lync Server 2013</a></p></td>
<td><p>Archivia l'area di rete definita nell'impostazione NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">Tabella UserSite in Lync Server 2013</a></p></td>
<td><p>Archivia il sito di rete definito nell'impostazione NCS.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Tabella subnet in Lync Server 2013</a></p></td>
<td><p>Archivia la subnet definita nell'impostazione NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">Tabella MonitoredRegionLink in Lync Server 2013</a></p></td>
<td><p>Archivia il collegamento area definito nell'impostazione NCS.</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">Tabella MonitoredUserSiteLink</a></p></td>
<td><p>Archivia i collegamenti di sito di rete definiti nell'impostazione NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Tabella EndpointSubnet in Lync Server 2013</a></p></td>
<td><p>Archivia la subnet dell'endpoint che partecipa a una sessione audio e video.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Tabella server in Lync Server 2013</a></p></td>
<td><p>Archivia il nome di dominio completo o l'indirizzo IP del server che passa attraverso il supporto.</p></td>
</tr>
</tbody>
</table>


**Tabelle per i dati di metrica**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>tavolo</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingstream-table.md">Tabella AppSharingStream in Lync Server 2013</a></p></td>
<td><p>Archivia le metriche relative alla qualità delle esperienze per i flussi di rete utilizzati per la condivisione delle applicazioni. Metriche sulla qualità delle esperienze per i flussi di rete utilizzati per la condivisione delle applicazioni.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Tabella di sessione in Lync Server 2013</a></p></td>
<td><p>Archivia le informazioni generali su una sessione audio o audio/video. Una sessione è definita come una finestra di dialogo SIP audio o video tra due endpoint.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a></p></td>
<td><p>Archivia informazioni su ogni linea multimediale in una sessione. Una linea multimediale è una raccolta di uno o più flussi audio e video. In genere, una singola linea multimediale avrà due flussi, audio o video.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">Tabella AudioStream in Lync Server 2013</a></p></td>
<td><p>Archivia le metriche per la qualità del supporto audio per ogni flusso audio della linea multimediale.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">Tabella AudioSignal in Lync Server 2013</a></p></td>
<td><p>Archivia le metriche relative alla qualità multimediale audio nella linea multimediale. Sono incluse le metriche di annullamento dell'eco acustico (AEC) e di controllo di guadagno automatico (AGC).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Tabella VideoStream in Lync Server 2013</a></p></td>
<td><p>Archivia le metriche di qualità multimediale video per ogni flusso audio nella linea multimediale.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Tabella AudioClientEvent in Lync Server 2013</a></p></td>
<td><p>Archivia le metriche di qualità multimediale audio raccolte dall'evento client.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Tabella VideoClientEvent in Lync Server 2013</a></p></td>
<td><p>Archivia le metriche di qualità multimediale video raccolte dall'evento client.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabella DiagnosticData</strong></p></td>
<td><p>Archivia i dati di diagnostica solo per uso interno.</p></td>
</tr>
</tbody>
</table>


**Tabelle per i dati di riepilogo**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>tavolo</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Tabella ServerSummary</strong></p></td>
<td><p>Archivia i dati di riepilogo per i server, questi dati vengono utilizzati solo per i report di qualità di esperienza (QoE).</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabella UserSummary</strong></p></td>
<td><p>Archivia i dati di riepilogo per gli utenti, questi dati vengono utilizzati solo per i report QoE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabella CallTypeSummary</strong></p></td>
<td><p>Archivia i dati di riepilogo per i tipi di chiamata, questi dati vengono utilizzati solo per i report QoE.</p></td>
</tr>
</tbody>
</table>


**Tabelle per l'utilizzo interno da parte di Monitoring Server**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>tavolo</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DbConfigDateTime</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabella FrontEnd</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabella Task</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MetricsThreshold</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZones</strong></p></td>
<td><p>Solo per utilizzo interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabella CallSummary</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabella DeviceCallSumary</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabella Tenant</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoCallSummaryTable</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ASCallSummaryTable</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

