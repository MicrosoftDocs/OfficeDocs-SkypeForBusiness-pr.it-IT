---
title: 'Lync Server 2013: Posizionamento dei file di log e dei file di dati di SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 197141ea62307631eab206fce5403d25b4d89583
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Posizionamento dei file di log e dei file di dati di SQL Server per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Durante la pianificazione e la distribuzione di Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2 SP1 per il pool di front end di Lync Server 2013, è importante considerare la posizione dei dati e i file di log sui dischi rigidi fisici per le prestazioni. La configurazione del disco consigliata consiste nell'implementare un set RAID da 1 + 0 con 6 fusi. Posizionare tutti i file di database e di log usati dal pool Front-end e i ruoli e i servizi del server associato, ovvero l'archiviazione e il server di monitoraggio, il servizio di Response Group di Lync Server, il servizio di parcheggio di Lync Server, nel set di unità RAID tramite Lync Server La distribuzione guidata comporterà una configurazione che è stata testata per una buona prestazione. I file di database e i relativi responsabili sono dettagliati nella tabella seguente.

<div>


> [!NOTE]  
> Se i criteri e le configurazioni di SQL Server richiedono un'installazione più specializzata, il database e i file di log possono essere installati in qualsiasi posizione predefinita tramite Lync Server Management Shell. Per altre informazioni, vedere <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">installazione di database tramite Lync Server Management Shell in Lync server 2013</A> .



</div>

### <a name="data-and-log-files-for-central-management-store"></a>File di dati e di log per Central Management store

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>File di database di Central Management store</th>
<th>Scopo del file di dati o del log</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XDS. ldf</p></td>
<td><p>File di log delle transazioni per l'archivio di gestione centrale</p></td>
</tr>
<tr class="even">
<td><p>XDS. MDF</p></td>
<td><p>Gestisce la configurazione della topologia di Lync Server 2013 corrente, come definita e pubblicata da generatore di topologie</p></td>
</tr>
<tr class="odd">
<td><p>LIS. MDF</p></td>
<td><p>File di dati del servizio informazioni sulla posizione</p></td>
</tr>
<tr class="even">
<td><p>LIS. ldf</p></td>
<td><p>Log delle transazioni per il file di dati del servizio informazioni sulla posizione</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>File di dati e di log per gli utenti, i servizi di conferenza e la Rubrica

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>File di database di base di Lync Server 2013</th>
<th>Scopo del file di dati o del log</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTC. MDF</p></td>
<td><p>Dati utente permanenti (ad esempio, elenchi di controllo di accesso (ACL), contatti, conferenze pianificate)</p></td>
</tr>
<tr class="even">
<td><p>RTC. ldf</p></td>
<td><p>Log delle transazioni per i dati RTC</p></td>
</tr>
<tr class="odd">
<td><p>RTCDyn. MDF</p></td>
<td><p>Gestisce i dati utente temporanei (dati di runtime di presenza)</p></td>
</tr>
<tr class="even">
<td><p>RTCDyn. ldf</p></td>
<td><p>Log delle transazioni per i dati di RTCDyn</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab. MDF</p></td>
<td><p>Il database della Rubrica di comunicazioni in tempo reale (RTC) è il repository di SQL Server in cui sono archiviate le informazioni sul servizio Rubrica</p></td>
</tr>
<tr class="even">
<td><p>Rtcab. ldf</p></td>
<td><p>Log delle transazioni per il servizio Rubrica</p></td>
</tr>
<tr class="odd">
<td><p>RTCLocal. mdb</p></td>
<td><p>Ospita la directory conferenza</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds. MDF</p></td>
<td><p>Mantiene il backup dei dati degli utenti</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds. ldf</p></td>
<td><p>Log delle transazioni per i dati di rtcxds</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>File di dati e di log per il gruppo di chiamate e Response Park

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Database dell'applicazione</th>
<th>Scopo del file di dati o del log</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn. MDF</p></td>
<td><p>Database di informazioni dinamiche per l'applicazione Call Park</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn. ldf</p></td>
<td><p>Log delle transazioni per il file di dati dell'applicazione Call Park</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig. MDF</p></td>
<td><p>File di dati del servizio Response Group di Lync Server per la configurazione dei servizi</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig. ldf</p></td>
<td><p>File di log delle transazioni per la configurazione dell'Response Group Application</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn. MDF</p></td>
<td><p>File di dati del servizio Response Group per le operazioni di runtime</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn. ldf</p></td>
<td><p>Log delle transazioni per il file di dati runtime del servizio Response Group</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>File di dati e log per l'archiviazione e il monitoraggio del server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Archiviazione e monitoraggio dei file di database</th>
<th>Scopo del file di dati o del log</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr. MDF</p></td>
<td><p>Archivio dati per il processo di registrazione dei dettagli delle chiamate (CDR) del server di monitoraggio</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr. ldf</p></td>
<td><p>Log delle transazioni per i dati di registrazione dei dettagli delle chiamate (CDR)</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics. MDF</p></td>
<td><p>File di dati di qualità dell'esperienza archiviato nel server di monitoraggio</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics. ldf</p></td>
<td><p>Log delle transazioni per il monitoraggio dei dati</p></td>
</tr>
<tr class="odd">
<td><p>LcsLog. MDF</p></td>
<td><p>File di dati per il mantenimento dei dati di messaggistica istantanea e di conferenza in un server di archiviazione</p></td>
</tr>
<tr class="even">
<td><p>LcsLog. ldf</p></td>
<td><p>Log delle transazioni per l'archiviazione dei dati</p></td>
</tr>
</tbody>
</table>


In questo argomento vengono eseguiti i riferimenti al disco e al set RAID. Tieni presente che nella configurazione delle risorse di SQL Server il riferimento a un disco indica un singolo dispositivo hardware. Un'unità disco rigido con due partizioni, una che tiene i file di log e gli altri file di dati della partizione, non è uguale a due dischi, ognuno dedicato ai file di log o di dati.

In riferimento a set di RAID è disponibile una serie di tecnologie RAID diverse da diversi fornitori. E, con la proliferazione delle reti di archiviazione (SAN), i set RAID dedicati a un singolo sistema sono più rari. Per determinare qual è la configurazione migliore per il layout del disco durante la configurazione delle prestazioni di SQL Server con Lync Server 2013, è consigliabile consultarsi con il proprio fornitore RAID o SAN.

Si noti inoltre che non tutte le unità disco vengono create equamente; alcune prestazioni sono migliori di altre. Anche le unità dello stesso produttore possono variare in base alle prestazioni a causa della velocità di rotazione, della dimensione della cache hardware e di altri fattori.

</div>

<span> </span>

</div>

</div>

</div>

