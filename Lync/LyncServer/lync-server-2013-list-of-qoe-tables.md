---
title: 'Lync Server 2013: Elenco delle tabelle QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c82c38a995fd9e847057fedbbce1422085332b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a>Elenco delle tabelle QoE in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

Lo schema del database è costituito dalle tabelle seguenti.

**Tabelle di supporto**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tabella</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Tabella AppSharingMetricsThreshold in Lync Server 2013</a></p></td>
<td><p>Consente di archiviare valori ottimali e accettabili per la qualità delle metriche di esperienza usate con la condivisione delle applicazioni.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">Tabella CodecDescription in Lync Server 2013</a></p></td>
<td><p>Associa gli identificatori di codec univoci al relativo codec.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">Tabella IPAddress in Lync Server 2013</a></p></td>
<td><p>Esegue il mapping degli indirizzi IP agli identificatori di indirizzi IP univoci usati altrove nel database qualità di esperienza.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">Tabella NetworkConnectionDetail in Lync Server 2013</a></p></td>
<td><p>Associa i tipi di connessione di rete agli identificatori di connessione di rete usati in un altro punto del database qualità dell'esperienza.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">Tabella PurgeSettings (QoE) in Lync Server 2013</a></p></td>
<td><p>Archivia le informazioni che specificano se (e quando) la qualità obsoleta dei record dell'esperienza verrà eliminata automaticamente dal database QoE.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">Tabella TraceRoute in Lync Server 2013</a></p></td>
<td><p>Archivia le informazioni di routing per le chiamate.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a></p></td>
<td><p>Associa gli identificatori dell'agente utente ai nomi descrittivi dell'agente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">Tabella VideoMetricsThreshold in Lync Server 2013</a></p></td>
<td><p>Consente di archiviare valori ottimali e accettabili per la qualità delle metriche delle esperienze usate con videochiamate.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">Tabella UserAgent in Lync Server 2013</a></p></td>
<td><p>Archivia le stringhe degli agenti utente SIP (Session Initiation Protocol) e i tipi UA usati nelle sessioni audio e video.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">Tabella User in Lync Server 2013</a></p></td>
<td><p>Archivia gli URI dell'utente, della conferenza e del telefono usati nelle sessioni audio e video.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Tabella Endpoint in Lync Server 2013</a></p></td>
<td><p>Archivia i nomi di computer FQDN degli endpoint che partecipano a sessioni audio e video.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Tabella Pool in Lync Server 2013</a></p></td>
<td><p>Archivia i nomi dei pool a cui appartengono i dati della metrica.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Tabella Device in Lync Server 2013</a></p></td>
<td><p>Archivia i dispositivi di acquisizione e i dispositivi di rendering usati in una chiamata audio/video.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Tabella DeviceDriver in Lync Server 2013</a></p></td>
<td><p>Archivia il driver per il dispositivo di acquisizione e il dispositivo di rendering usato nelle chiamate audio/video.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Tabella Conference in Lync Server 2013</a></p></td>
<td><p>Archivia gli URI della conferenza per gli scenari di conferenza o DialogID per altri scenari.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Tabella SessionCorrelation in Lync Server 2013</a></p></td>
<td><p>Memorizza CorrelationID per le chiamate PSTN.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a></p></td>
<td><p>Archivia il codec usato nelle chiamate audio/video.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Tabella AppliedBandwidthSource in Lync Server 2013</a></p></td>
<td><p>Archivia l'origine della larghezza di banda usata nelle chiamate audio/video.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Tabella MacAddress in Lync Server 2013</a></p></td>
<td><p>Archivia l'indirizzo MAC degli endpoint che partecipano a sessioni audio e video.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Tabella Dialog in Lync Server 2013</a></p></td>
<td><p>Archivia l'ID della finestra di dialogo delle sessioni audio e video.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Tabella Region in Lync Server 2013</a></p></td>
<td><p>Archivia l'area di rete definita in impostazione NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">Tabella UserSite in Lync Server 2013</a></p></td>
<td><p>Archivia il sito di rete definito nell'impostazione NCS.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Tabella Subnet in Lync Server 2013</a></p></td>
<td><p>Archivia la subnet definita nell'impostazione NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">Tabella MonitoredRegionLink in Lync Server 2013</a></p></td>
<td><p>Archivia il collegamento all'area geografica definito nell'impostazione NCS.</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">Tabella MonitoredUserSiteLink</a></p></td>
<td><p>Archivia i collegamenti ai siti di rete definiti nell'impostazione NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Tabella EndpointSubnet in Lync Server 2013</a></p></td>
<td><p>Archivia la subnet dell'endpoint che partecipa a una sessione audio e video.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Tabella Server in Lync Server 2013</a></p></td>
<td><p>Archivia il nome di dominio completo o l'indirizzo IP del server in cui passa il contenuto multimediale.</p></td>
</tr>
</tbody>
</table>


**Tabelle per i dati delle metriche**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tabella</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingstream-table.md">Tabella AppSharingStream in Lync Server 2013</a></p></td>
<td><p>Archivia la qualità delle metriche dell'esperienza per i flussi di rete usati per la condivisione delle applicazioni. Qualità delle metriche dell'esperienza per i flussi di rete usati per la condivisione delle applicazioni.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Tabella Session in Lync Server 2013</a></p></td>
<td><p>Archivia informazioni generali su una sessione audio o audio/video. Una sessione viene definita come una finestra di dialogo SIP audio o video tra due endpoint.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a></p></td>
<td><p>Archivia informazioni su ogni riga multimediale di una sessione. Una linea media è una raccolta di uno o più flussi audio e video. In genere, una singola linea multimediale avrà due flussi, audio o video.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">Tabella AudioStream in Lync Server 2013</a></p></td>
<td><p>Memorizza le metriche per la qualità del supporto audio per ogni flusso audio nella linea media.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">Tabella AudioSignal in Lync Server 2013</a></p></td>
<td><p>Memorizza le metriche di qualità per i supporti audio nella linea media. Sono incluse le metriche per l'annullamento dell'eco acustica (AEC) e il controllo automatico del guadagno (AGC).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Tabella VideoStream in Lync Server 2013</a></p></td>
<td><p>Archivia le metriche di qualità multimediali video per ogni flusso audio nella linea media.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Tabella AudioClientEvent in Lync Server 2013</a></p></td>
<td><p>Archivia le metriche di qualità del supporto audio raccolte dall'evento client.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Tabella VideoClientEvent in Lync Server 2013</a></p></td>
<td><p>Archivia le metriche di qualità multimediali video raccolte dall'evento client.</p></td>
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
<th><strong>Tabella</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Tabella ServerSummary</strong></p></td>
<td><p>Archivia i dati di riepilogo per i server, questi dati vengono usati solo per i report di qualità dell'esperienza (QoE).</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabella UserSummary</strong></p></td>
<td><p>Archivia i dati di riepilogo per gli utenti, questi dati vengono usati solo per i report QoE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabella CallTypeSummary</strong></p></td>
<td><p>Archiviare i dati di riepilogo per i tipi di chiamata, questi dati vengono usati solo per i report QoE.</p></td>
</tr>
</tbody>
</table>


**Tabelle per l'uso interno tramite Monitoring Server**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tabella</strong></th>
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
<td><p><strong>Tabella delle attività</strong></p></td>
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
<td><p>Solo per uso interno.</p></td>
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
<td><p><strong>Tabella tenant</strong></p></td>
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

