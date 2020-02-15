---
title: 'Lync Server 2013: tabella AppSharingMetricsThreshold'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89260bb2e854087ec1167ff0fd8039c58ac99300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a>Tabella AppSharingMetricsThreshold in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-12-08_

La tabella AppSharingMetricsThreshold contiene i valori ottimali e accettabili delle metriche QoE utilizzate con la condivisione delle applicazioni. Questi valori soglia sono utilizzati per determinare se l'esperienza di condivisione deve essere classificata come insufficiente.

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
<td><p>Tipo di chiamata effettuata.</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimitOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Limitazione ottimale della larghezza di banda per la condivisione delle applicazioni. Il valore predefinito è 1000000.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthLimitAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Limitazione accettabile della larghezza di banda per la condivisione delle applicazioni. Il valore predefinito è 500000.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotalOptimal</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td></td>
<td><p>Tasso percentuale ottimale delle sezioni “danneggiate” per la classificazione della qualità di una condivisione delle applicazioni. Questo valore rappresenta la percentuale di contenuto del condivisore che non ha raggiunto il visualizzatore. Il contenuto potrebbe essere scartato (o danneggiato) rispettivamente quando il condivisore scarta le sezioni dall'origine grafica o ASMCU scarica le sezioni dal condivisore. Il valore predefinito è 11 percento.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentTotalAcceptable</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td></td>
<td><p>Tasso percentuale accettabile delle sezioni “danneggiate” per la classificazione della qualità di una condivisione delle applicazioni. Questo valore rappresenta la percentuale di contenuto del condivisore che non ha raggiunto il visualizzatore. Il contenuto potrebbe essere scartato (o danneggiato) rispettivamente quando il condivisore scarta le sezioni dall'origine grafica o ASMCU scarica le sezioni dal condivisore. Il valore predefinito è 36 percento.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensityOptimal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensityAcceptable</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverageOptimal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Valore ottimale per il ritardo unidirezionale relativo tra i due endpoint multimediali coinvolti nella condivisione delle applicazioni. È una misura della latenza a hop singolo. Il valore predefinito è 1,0 secondi.</p>
<p>La colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverageAcceptable</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Valore ottimale per il ritardo unidirezionale relativo tra i due endpoint multimediali coinvolti nella condivisione delle applicazioni. È una misura della latenza a hop singolo. Il valore predefinito è 1,75 secondi.</p>
<p>La colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyAverageOptimal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Latenza ottimale di elaborazione delle sezioni RDP nel server per conferenze di Condivisione applicazioni per tutta la durata della sessione di visualizzazione. Latenza è la differenza di tempo tra quando la cornice iniziale è codificata sul server (condivisore o MCU a seconda dello scenario) e lo stesso frame iniziale viene decodificato nel visualizzatore.</p>
<p>Una media elevata è sintomo di un ritardo superiore nell'esperienza di visualizzazione. In un server per conferenze sovraccarico possono verificarsi ritardi medi superiori. Il valore predefinito è 200 ms.</p>
<p>La colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverageAcceptable</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Latenza accettabile di elaborazione delle sezioni RDP nel server per conferenze di Condivisione applicazioni per tutta la durata della sessione di visualizzazione. Latenza è la differenza di tempo tra quando la cornice iniziale è codificata sul server (condivisore o MCU a seconda dello scenario) e lo stesso frame iniziale viene decodificato nel visualizzatore.</p>
<p>Una media elevata è sintomo di un ritardo superiore nell'esperienza di visualizzazione. In un server per conferenze sovraccarico possono verificarsi ritardi medi superiori. Il valore predefinito è 200 ms.</p>
<p>La colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

