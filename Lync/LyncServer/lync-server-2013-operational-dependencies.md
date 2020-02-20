---
title: 'Lync Server 2013: dipendenze operative'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9901d664f667dce2e669b9f20e040b6b2b7ff1a1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a>Dipendenze operative in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-05-15_

L'architettura di riferimento descritta in questo documento consentirà di disporre di una distribuzione di Lync Server 2013 che non solo si adatta ai requisiti dell'organizzazione, ma è stata architettata secondo le procedure consigliate di Microsoft. È possibile che l'implementazione di Lync Server 2013 sia un servizio dinamico e, come qualsiasi altro servizio nell'organizzazione, richiede ancora il monitoraggio e la gestione proattiva per mantenere elevato il livello di disponibilità del servizio e la qualità del servizio per l'azienda.

Dato che Lync Server 2013 diventa profondamente radicato nell'attività quotidiana dell'organizzazione, è importante che il servizio sia gestito da una gestione accurata e tangibile del livello di servizio. L'architettura di sistema di Lync può diventare complessa e molto integrata e per mantenere una gestione dei livelli di servizio efficace e stabilire SLA per Lync Server 2013 diventa fondamentale comprendere le dipendenze del sistema su altre piattaforme e server. Altrettanto importante è tenere presente che i servizi aziendali, ad esempio le applicazioni integrate vocali e UC, diventano dipendenti da Lync.

Lync Server 2013 deve essere stabilito notando tutte le dipendenze suddette. La mappa dei servizi consentirà di formulare un SLA tra Lync e il relativo servizio dipendente e di fornire un punto di partenza per la negoziazione del contratto di servizio.

Nella tabella seguente sono elencati i servizi di dipendenza tipici per un'infrastruttura di Lync. Ognuna di queste tecnologie deve disporre di un monitoraggio proattivo.

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
<td><p>Domain Naming Service</p></td>
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
<td><p>Gestione del sistema – monitoraggio e distribuzione</p></td>
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
<td><p>Infrastruttura di rete – interno (LAN/WAN)</p></td>
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


Si presuppone che l'organizzazione sia operativamente matura nell'esercizio delle funzioni di base di gestione del livello di servizio, ad esempio la gestione delle modifiche, degli incidenti e delle rilasci come prescritto dal MOF. La soluzione Lync deve essere adottata da queste funzioni ed essere soggetta agli stessi processi di gestione operativi.

Basandosi sulle informazioni ottenute in alto, ora si ha una maggiore comprensione di ciò che può influire sul servizio Lync nell'organizzazione. Per garantire la disponibilità e la qualità dei servizi di Lync Server 2013, è necessario che gli strumenti di monitoraggio seguenti accompagnino la distribuzione dell'architettura di riferimento:

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
<td><p>Distribuire almeno un ruolo del server di monitoraggio di Lync Server 2013 per sito centrale e configurare il pacchetto di report su qualità di esperienza (QoE).</p>
<p>Per ulteriori informazioni, vedere la documentazione relativa alla distribuzione di Lync Server 2013:</p>
<p><a href="lync-server-2013-deploying-monitoring.md">Distribuzione del monitoraggio in Lync Server 2013</a></p></td>
<td><p>Siti centrali</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Legare ogni pool all'istanza più vicina del ruolo Monitoring Server.</p></td>
<td><p>Siti centrali</p>
<p>Siti di succursale</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>System Center Operations Manager 2012 con Microsoft Lync Server 2013 Management Pack (MP) importato.</p>
<p>Il Management Pack implementa il registro eventi tradizionale e la strumentazione basata sui contatori delle prestazioni viene utilizzata e abilitando la strumentazione appena disponibile in Lync Server 2013.</p></td>
<td><p>Siti centrali</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Assicurarsi che l'individuazione centrale per l'individuazione di ruoli e componenti che devono essere monitorati sia completata automaticamente in base a uno script di individuazione centrale che legge il documento della topologia pubblicato nel database di gestione centrale.</p></td>
<td><p>Sito centrale</p>
<p>Sito di succursale</p>
<p>Sito perimetrale</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Distribuire gli agenti di System Centre Operations Manager 2007 a tutti i server distribuiti che eseguono Lync Server.</p></td>
<td><p>Sito centrale</p>
<p>Sito di succursale</p>
<p>Sito perimetrale</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Verificare che gli avvisi con priorità siano configurati per la notifica:</p>
<p>Avvisi con priorità alta</p>
<p>Avvisi di priorità media</p>
<p>Altri avvisi.</p></td>
<td><p>Sito centrale</p>
<p>Sito di succursale</p>
<p>Sito perimetrale</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Configurare il monitoraggio delle porte per la distribuzione.</p></td>
<td><p>Sito centrale</p>
<p>Sito di succursale</p>
<p>Sito perimetrale</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Configurare il monitoraggio degli URL per la distribuzione</p></td>
<td><p>Sito centrale</p></td>
</tr>
<tr class="odd">
<td><p>Integrazione di Lync e System Center Operations Manager</p></td>
<td><p>Distribuire l'affidabilità delle chiamate e la qualità multimediale MonitoringCall affidabilità e monitoraggio della qualità multimediale utilizzare il computer Monitoring Server come nodo Watcher per monitorare l'affidabilità delle chiamate e la qualità multimediale di Lync Server. Entrambe queste funzionalità eseguono una query sui database del Monitoring Server per eseguire l'analisi.</p></td>
<td><p>Sito centrale</p>
<p>Sito di succursale</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Verificare che le soglie di avviso per la qualità multimediale siano configurate correttamente. Nella tabella seguente vengono indicati i punteggi massimi di opinione della rete media per codec. In produzione questi punteggi devono essere monitorati per un periodo stabilito e devono essere stabilite soglie accettabili in base ai punteggi di NMOS specifici dell'organizzazione.</p></td>
<td><p>Sito centrale</p>
<p>Sito di succursale</p></td>
</tr>
<tr class="odd">
<td><p>Analizzatore delle transazioni sintetiche di Lync Server 2013</p></td>
<td><p>Distribuire un server Lync dedicato come Watcher delle transazioni sintetiche.</p>
<p>Le transazioni sintetiche sono cmdlet di Lync Server 2013 di Windows PowerShell che vengono attivati automaticamente dal Management Pack su un intervallo predefinito. Queste operazioni vengono eseguite in un nodo di monitoraggio delle transazioni sintetico che è un server designato dall'amministratore responsabile dell'individuazione e dell'esecuzione dei token di servizio per ogni pool.</p>
<p>Non è consigliabile utilizzare un server Microsoft Lync Server 2013 esistente come nodo di Watcher delle transazioni sintetiche. Ciò è dovuto ai requisiti di utilizzo della CPU e della memoria elevati per l'esecuzione delle STs. Utilizzare un nuovo computer server (o un server virtuale) per il nodo Watcher delle transazioni sintetiche.</p></td>
<td><p>Sito centrale</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Nodo di Watcher per la distribuzione di transazioni sintetiche.</p>
<p>Fare riferimento al documento MonitoringCS_withSCOM. docx dalla documentazione di UCTAP Connect.</p></td>
<td><p>Sito centrale</p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a>Massimi punteggi MOS di rete per codec

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
<td><p>4.10</p></td>
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


Al di sopra delle attività di monitoraggio pro-attive precedenti, le attività di manutenzione devono essere eseguite per i siti centrali, perimetrali e di succursale su base giornaliera, settimanale e mensile ricorrenti, come definito nella Guida alle operazioni di Lync RA.

</div>

<span> </span>

</div>

</div>

</div>

