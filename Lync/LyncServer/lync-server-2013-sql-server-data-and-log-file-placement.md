---
title: 'Lync Server 2013: disposizione dei file di registro e di dati di SQL Server'
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
ms.openlocfilehash: dfae4aef6e6f5ec0a33fe64d42ea7bfd093badee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Disposizione dei file di registro e di dati di SQL Server per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Durante la pianificazione e la distribuzione di Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2 SP1 per il pool Front End di Lync Server 2013, è importante considerare la disposizione dei file di dati e di registro su dischi rigidi fisici per le prestazioni. La configurazione del disco consigliata consiste nell'implementazione di un set RAID 1 + 0 con 6 mandrini. Inserimento di tutti i file di database e di registro utilizzati dal pool Front end e dai ruoli e servizi del server associati (ovvero archiviazione e Monitoring Server, servizio Response Group di Lync Server, servizio parcheggio di chiamata di Lync Server) nel set di unità RAID tramite Lync Server La distribuzione guidata provocherà una configurazione che è stata testata per una buona prestazione. I file di database e la relativa funzione vengono spiegati in dettaglio nella tabella seguente.

<div>


> [!NOTE]  
> Se i criteri e le configurazioni di SQL Server richiedono un'installazione più specializzata, è possibile installare il database e i file di registro in qualsiasi percorso predefinito utilizzando Lync Server Management Shell. Per ulteriori informazioni, vedere <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">installazione di database mediante Lync Server Management Shell in Lync server 2013</A> .



</div>

### <a name="data-and-log-files-for-central-management-store"></a>File di dati e di registro per l'archivio di gestione centrale

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>File di database dell'archivio di gestione centrale</th>
<th>Scopi del file di dati o del registro</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XDS. ldf</p></td>
<td><p>File di registro delle transazioni per l'archivio di gestione centrale</p></td>
</tr>
<tr class="even">
<td><p>XDS. MDF</p></td>
<td><p>Gestisce la configurazione della topologia di Lync Server 2013 corrente, come definito e pubblicato da generatore di topologie</p></td>
</tr>
<tr class="odd">
<td><p>LIS. MDF</p></td>
<td><p>File di dati del servizio informazioni percorso</p></td>
</tr>
<tr class="even">
<td><p>LIS. ldf</p></td>
<td><p>Log delle transazioni per il file di dati del servizio informazioni percorso</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>File di dati e di registro per utenti, conferenze e Rubrica

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>File di database di base di Lync Server 2013</th>
<th>Scopi del file di dati o del registro</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTC. MDF</p></td>
<td><p>Dati utente permanenti (ad esempio, elenchi di controllo di accesso (ACL, Access Control List), contatti, conferenze pianificate</p></td>
</tr>
<tr class="even">
<td><p>RTC. ldf</p></td>
<td><p>Log delle transazioni per i dati RTC</p></td>
</tr>
<tr class="odd">
<td><p>RTCDyn. MDF</p></td>
<td><p>Mantiene i dati utente temporanei (dati di runtime di presenza)</p></td>
</tr>
<tr class="even">
<td><p>RTCDyn. ldf</p></td>
<td><p>Log delle transazioni per i dati di RTCDyn</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab. MDF</p></td>
<td><p>Il database della rubrica per la comunicazione in tempo reale è l'archivio di SQL Server in cui sono memorizzate le informazioni per il servizio Rubrica</p></td>
</tr>
<tr class="even">
<td><p>Rtcab. ldf</p></td>
<td><p>Registro delle transazioni per il servizio Rubrica</p></td>
</tr>
<tr class="odd">
<td><p>RTCLocal. mdb</p></td>
<td><p>Ospita la directory conferenze</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds. MDF</p></td>
<td><p>Gestisce il backup per i dati utente</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds. ldf</p></td>
<td><p>Log delle transazioni per i dati di rtcxds</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>File di dati e di registro per Parcheggio di chiamata e Response Group

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Database dell'applicazione</th>
<th>Scopi del file di dati o del registro</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn. MDF</p></td>
<td><p>Database delle informazioni dinamiche per l'applicazione Parcheggio di chiamata</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn. ldf</p></td>
<td><p>Log delle transazioni per il file di dati dell'applicazione Parcheggio di chiamata</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig. MDF</p></td>
<td><p>File di dati del servizio Response Group di Lync Server per la configurazione dei servizi</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig. ldf</p></td>
<td><p>File di registro delle transazioni per la configurazione dell'applicazione Response Group</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn. MDF</p></td>
<td><p>File di dati del servizio Response Group per le operazioni di runtime</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn. ldf</p></td>
<td><p>Registro delle transazioni per il file di dati del runtime del servizio Response Group</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>File di dati e di registro per il server di archiviazione e Monitoring Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>File dei database di archiviazione e monitoraggio</th>
<th>Scopi del file di dati o del registro</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr. MDF</p></td>
<td><p>Archivio dati per il processo di registrazione dettagli chiamata (CDR) del Monitoring Server</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr. ldf</p></td>
<td><p>Registro delle transazioni per i dati di registrazione dettagli chiamata</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics. MDF</p></td>
<td><p>File di dati di qualità di esperienza memorizzato dal Monitoring Server</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics. ldf</p></td>
<td><p>Registro delle transazioni per i dati di monitoraggio</p></td>
</tr>
<tr class="odd">
<td><p>LcsLog. MDF</p></td>
<td><p>File di dati per la conservazione dei dati di messaggistica istantanea e delle conferenze in un server di archiviazione</p></td>
</tr>
<tr class="even">
<td><p>LcsLog. ldf</p></td>
<td><p>Registro delle transazioni per l'archiviazione dei dati</p></td>
</tr>
</tbody>
</table>


In questo argomento si fa riferimento a set di dischi e RAID. Si noti che per la configurazione delle risorse di SQL Server, i riferimenti a un disco indicano un singolo dispositivo hardware. Un'unità disco rigido con due partizioni, una per i file di registro e l'altra per i file di dati, non equivale a due dischi ognuno dedicato ai file di registro o ai file di dati.

Per quanto riguarda i set RAID, esistono numerose tecnologie RAID diverse da vari fornitori. Con la proliferazione delle reti SAN (Storage Area Network), inoltre, i set RAID dedicati a un singolo sistema sono più rari. È consigliabile consultare il fornitore RAID o SAN per determinare quale sia la configurazione migliore per il layout del disco durante la configurazione delle prestazioni di SQL Server con Lync Server 2013.

Si noti inoltre che non tutte le unità disco vengono create in modo uguale e alcune offrono prestazioni migliori di altre. Anche unità dello stesso produttore possono offrire prestazioni variabili a seconda di velocità di rotazione, dimensioni della cache hardware e altri fattori.

</div>

<span> </span>

</div>

</div>

</div>

