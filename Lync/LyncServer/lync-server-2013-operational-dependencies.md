---
title: 'Lync Server 2013: dipendenze operative'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d54ef9959f48c085ad4f5f28f182b86442ebec8c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a>Dipendenze operative in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-05-15_

L'architettura di riferimento discussa in questo documento consentirà di avere una distribuzione di Lync Server 2013 che non solo si adatta ai requisiti dell'organizzazione, ma è stata architettata come per le procedure consigliate Microsoft. Sia che l'implementazione di Lync Server 2013 sia un servizio dinamico e, come tutti gli altri servizi dell'organizzazione, richiede ancora il monitoraggio e la gestione proattiva per mantenere un livello elevato di disponibilità del servizio e qualità dei servizi per l'azienda.

Dato che Lync Server 2013 diventa profondamente radicato nell'attività quotidiana dell'organizzazione, è importante che il servizio sia gestito da una gestione accurata e tangibile dei livelli di servizio. L'architettura di sistema di Lync può diventare complessa e molto integrata e per mantenere una gestione efficace dei livelli di servizio e stabilire gli SLA per Lync Server 2013 diventa fondamentale comprendere le dipendenze del sistema in altre piattaforme e server. Altrettanto importante è tenere presente che i servizi commerciali, come la voce e le applicazioni integrate UC, diventano dipendenti da Lync.

Lync Server 2013 deve essere stabilito notando tutte le dipendenze suddette. La mappa dei servizi consente di formulare un contratto di SLA tra Lync e il servizio dipendente e di creare un punto di partenza per la negoziazione di SLA.

La tabella seguente elenca i servizi di dipendenza tipici per un'infrastruttura Lync. Ognuna di queste tecnologie dovrebbe avere il proprio monitoraggio proattivo.

### <a name="typical-dependency-services"></a>Servizi di dipendenza tipici

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Servizio di dipendenza</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Sistemi operativi</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Hardware del server</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Active Directory</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Infrastruttura a chiave pubblica</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Servizio di denominazione dei domini</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Servizi di database</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Servizi di archiviazione</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Gestione di sistemi-monitoraggio e distribuzione</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Servizi di sicurezza-antivirus</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Infrastruttura di rete-Internet</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Infrastruttura di rete-interno (LAN/WAN)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Infrastruttura di telefonia-IP-PBX e gateway</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Servizi cloud</p></td>
<td></td>
</tr>
</tbody>
</table>


Si presuppone che l'organizzazione sia operativamente matura nell'esercizio di funzioni di base per la gestione dei livelli di servizio, come la gestione delle modifiche, degli incidenti e delle versioni, come prescritto da MOF. La soluzione Lync deve essere adottata da queste funzioni e diventare soggetta agli stessi processi di gestione operativa.

Basandosi sulle informazioni ottenute in precedenza, ora abbiamo una maggiore comprensione di ciò che può influire sul servizio Lync nell'organizzazione. Per garantire la disponibilità e la qualità dei servizi di Lync Server 2013, gli strumenti di monitoraggio seguenti devono accompagnare la distribuzione dell'architettura di riferimento:

### <a name="monitoring-tools"></a>Strumenti di monitoraggio

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Descrizione</th>
<th>Sito applicabile</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Server di monitoraggio di Lync Server 2013</p></td>
<td><p>Distribuire almeno un ruolo del server di monitoraggio di Lync Server 2013 per sito centrale e configurare il pacchetto di report di qualità dell'esperienza (QoE).</p>
<p>Per ulteriori informazioni, vedere la documentazione relativa alla distribuzione di Lync Server 2013:</p>
<p><a href="lync-server-2013-deploying-monitoring.md">Distribuzione del monitoraggio in Lync Server 2013</a></p></td>
<td><p>Siti centrali</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Legare ogni pool all'istanza più vicina del ruolo del server di monitoraggio.</p></td>
<td><p>Siti centrali</p>
<p>Siti di succursale</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>System Center Operations Manager 2012 con il Microsoft Lync Server 2013 Management Pack (MP) importato.</p>
<p>Il Management Pack implementa il registro eventi tradizionale e la strumentazione basata su contatori delle prestazioni viene utilizzata oltre a consentire la strumentazione appena disponibile in Lync Server 2013.</p></td>
<td><p>Siti centrali</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Verificare che l'individuazione centralizzata dell'individuazione di ruoli e componenti da monitorare venga completata automaticamente in base a uno script di individuazione centralizzato che legge il documento di topologia pubblicato nel database di gestione centrale.</p></td>
<td><p>Sito centrale</p>
<p>Sito filiale</p>
<p>Sito Edge</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Distribuire gli agenti di System Centre Operations Manager 2007 a tutti i server distribuiti che utilizzano Lync Server.</p></td>
<td><p>Sito centrale</p>
<p>Sito filiale</p>
<p>Sito Edge</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Verificare che gli avvisi con priorità siano configurati per la notifica:</p>
<p>Avvisi con priorità alta</p>
<p>Avvisi di priorità media</p>
<p>Altri avvisi.</p></td>
<td><p>Sito centrale</p>
<p>Sito filiale</p>
<p>Sito Edge</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Configurare il monitoraggio della porta per la distribuzione.</p></td>
<td><p>Sito centrale</p>
<p>Sito filiale</p>
<p>Sito Edge</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Configurare il monitoraggio degli URL per la distribuzione</p></td>
<td><p>Sito centrale</p></td>
</tr>
<tr class="odd">
<td><p>Integrazione di Lync e System Center Operations Manager</p></td>
<td><p>Distribuire l'affidabilità delle chiamate e la qualità dei contenuti multimediali MonitoringCall monitoraggio della qualità dei contenuti multimediali usare il computer server di monitoraggio come nodo Watcher per monitorare l'affidabilità delle chiamate e la qualità dei contenuti multimediali di Lync Server. Entrambe le funzionalità eseguono query sui database del server di monitoraggio per eseguire l'analisi.</p></td>
<td><p>Sito centrale</p>
<p>Sito filiale</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Verificare che le soglie di avviso per la qualità multimediale siano configurate accuratamente. La tabella seguente indica i punteggi di opinione della rete massima per codec. Nella produzione questi punteggi devono essere controllati per un periodo impostato e le soglie accettabili devono essere stabilite in base ai punteggi NMOS specifici dell'organizzazione.</p></td>
<td><p>Sito centrale</p>
<p>Sito filiale</p></td>
</tr>
<tr class="odd">
<td><p>Monitoraggio delle transazioni sintetiche di Lync Server 2013</p></td>
<td><p>Distribuire un server Lync dedicato come Watcher delle transazioni sintetiche.</p>
<p>Le transazioni sintetiche sono cmdlet di Windows PowerShell di Lync Server 2013 attivati automaticamente dal Management Pack in base a un intervallo predefinito. Queste operazioni vengono eseguite in un nodo di Watcher delle transazioni sintetiche che è un server designato dall'amministratore responsabile dell'individuazione e dell'esecuzione del servizio STs per ogni pool.</p>
<p>Non è consigliabile usare un server Microsoft Lync Server 2013 esistente come nodo di Watcher delle transazioni sintetiche. Ciò è dovuto ai requisiti di utilizzo della CPU e della memoria elevati per l'uso di STs. Usare un nuovo computer server (o un server virtuale) per il nodo di Watcher delle transazioni sintetiche.</p></td>
<td><p>Sito centrale</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Distribuzione di nodi di Watcher delle transazioni sintetiche.</p>
<p>Fare riferimento al documento MonitoringCS_withSCOM. docx dalla documentazione di UCTAP Connect.</p></td>
<td><p>Sito centrale</p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a>Punteggi massimi MOS di rete per codec

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Scenario</th>
<th>Codec</th>
<th>Max NMOS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamata UC-UC</p></td>
<td><p>RTAudio WB</p></td>
<td><p>4,10</p></td>
</tr>
<tr class="even">
<td><p>Chiamata UC-UC</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>Conferenza telefonica</p></td>
<td><p>Sirena</p></td>
<td><p>3,72</p></td>
</tr>
<tr class="even">
<td><p>Chiamata UC-PSTN</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>Chiamata UC-PSTN</p></td>
<td><p>G-711</p></td>
<td><p>3,61</p></td>
</tr>
</tbody>
</table>


Oltre alle attività di monitoraggio pro-attive precedenti, le attività di manutenzione devono essere eseguite per i siti centrali, perimetrali e di succursale su base giornaliera, settimanale e mensile ricorrenti, come definito nella Guida operativa di Lync RA.

</div>

<span> </span>

</div>

</div>

</div>

