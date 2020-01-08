---
title: 'Lync Server 2013: tabella AppSharingMetricsThreshold'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0f8dc1dac3dc7a9ec362473221d36191dd7dd0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a>Tabella AppSharingMetricsThreshold in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-12-08_

La tabella AppSharingMetricsThreshold contiene valori ottimali e accettabili per la qualità delle metriche delle esperienze usate con la condivisione delle applicazioni. Queste soglie vengono usate per determinare se l'esperienza di condivisione dell'applicazione deve essere classificata come scadente.

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
<th><strong>Colonna</strong></th>
<th><strong>Tipo di dati</strong></th>
<th><strong>Chiave/indice</strong></th>
<th><strong>Dettagli</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>Tipo di chiamata inserita.</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimitOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Limitazione ottimale della larghezza di banda per la condivisione delle applicazioni. Il valore predefinito è 1 milione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthLimitAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Limitazione della larghezza di banda accettabile per la condivisione delle applicazioni. Il valore predefinito è 500000.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotalOptimal</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td></td>
<td><p>Tasso percentuale ottimale per i riquadri "viziati" per la classificazione di una qualità di condivisione delle applicazioni. Questo valore è la percentuale del contenuto del condivisore che non ha raggiunto il visualizzatore. Il contenuto può essere scartato (o viziato) quando il condivisore Elimina i riquadri dall'origine grafica o i riquadri di ASMCU scartano rispettivamente i riquadri di condivisione. Il valore predefinito è 11%.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentTotalAcceptable</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td></td>
<td><p>tasso percentuale cceptable per i riquadri "viziati" per la classificazione di una qualità di condivisione delle applicazioni. Questo valore è la percentuale del contenuto del condivisore che non ha raggiunto il visualizzatore. Il contenuto può essere scartato (o viziato) quando il condivisore Elimina i riquadri dall'origine grafica o i riquadri di ASMCU scartano rispettivamente i riquadri di condivisione. Il valore predefinito è 36%.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Questa colonna non viene usata in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Questa colonna non viene usata in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensityOptimal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Questa colonna non viene usata in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensityAcceptable</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Questa colonna non viene usata in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Questa colonna non viene usata in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Questa colonna non viene usata in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverageOptimal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Valore ottimale per il ritardo unidirezionale relativo tra i due endpoint multimediali coinvolti nella condivisione dell'applicazione. Si tratta di una misura di latenza single-hop. Il valore predefinito è 1,0 secondi.</p>
<p>La colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverageAcceptable</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Valore ottimale per il ritardo unidirezionale relativo tra i due endpoint multimediali coinvolti nella condivisione dell'applicazione. Si tratta di una misura di latenza single-hop. Il valore predefinito è 1,75 secondi.</p>
<p>La colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyAverageOptimal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Valore ottimale della latenza media di elaborazione dei riquadri RDP nel server dei servizi di conferenza durante la durata della sessione di visualizzazione. La latenza è la differenza di orario tra il momento in cui il fotogramma iniziale è codificato nel server (condivisore o MCU a seconda dello scenario) e lo stesso fotogramma iniziale viene decodificato nel visualizzatore.</p>
<p>Una media elevata riflette un ritardo maggiore nell'esperienza di visualizzazione. Un server di conferenza di overload può avere ritardi medi più alti. Il valore predefinito è 200ms.</p>
<p>La colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverageAcceptable</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Valore accettabile della latenza media di elaborazione dei riquadri RDP nel server dei servizi di conferenza durante la durata della sessione di visualizzazione. La latenza è la differenza di orario tra il momento in cui il fotogramma iniziale è codificato nel server (condivisore o MCU a seconda dello scenario) e lo stesso fotogramma iniziale viene decodificato nel visualizzatore.</p>
<p>Una media elevata riflette un ritardo maggiore nell'esperienza di visualizzazione. Un server di conferenza di overload può avere ritardi medi più alti. Il valore predefinito è 200ms.</p>
<p>La colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

