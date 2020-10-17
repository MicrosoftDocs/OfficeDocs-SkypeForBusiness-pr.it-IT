---
title: 'Lync Server 2013: poster: indicatori di integrità chiave'
description: 'Lync Server 2013: poster: indicatori di integrità chiave.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9962d1764d5d2c664bb8415261344d9b48c81149
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566342"
---
# <a name="key-health-indicators-in-lync-server-2013"></a>Indicatori di integrità chiave in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-10_

Questo articolo è una compagna degli [indicatori di integrità principali: la base per il mantenimento di un poster integro di Lync Server](https://go.microsoft.com/fwlink/?linkid=391838) , che è possibile scaricare dall'area download.

![Poster che descrive la risoluzione dei problemi utilizzando i dati di KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster che descrive la risoluzione dei problemi utilizzando i dati di KHI")

È possibile utilizzare questo poster per informazioni sugli indicatori di integrità chiave (KHIs), sui contatori delle prestazioni con soglie volte a rivelare i problemi relativi all'esperienza utente. La raccolta dei dati di KHI è in genere il primo passaggio per l'implementazione della metodologia della qualità delle chiamate (CQM), che si concentra sul garantire un'esperienza audio di qualità per gli utenti di Lync.

In caso di domande sull'utilizzo di CQM, è possibile inoltrare le proprie domande a cqmfeedback@microsoft.com.

Nel poster vengono illustrate le aree seguenti:

  - Che cosa sono gli indicatori di integrità principali?

  - Per raccogliere i dati di KHI

  - Flusso di correzione per tutti i ruoli del server

  - Glossario

  - Server front-end

  - Server SQL back-end

  - Mediation Server

  - server perimetrali

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>Che cosa sono gli indicatori di integrità principali?

Gli indicatori di integrità principali sono contatori delle prestazioni con soglie volte a rivelare i problemi relativi all'esperienza utente. La raccolta dei dati di KHI è in genere il primo passaggio per l'implementazione della metodologia della qualità delle chiamate (CQM), che si concentra sul garantire un'esperienza audio di qualità per gli utenti di Lync.

KHIs vengono utilizzati oltre alle soluzioni di monitoraggio di Lync standard (ad esempio System Center Operations Manager, transazioni sintetiche, Monitoring Server) e non invece di tali soluzioni.

Raccogliere i contatori delle prestazioni di KHI e popolare il foglio di calcolo di KHI che accompagna la guida alla rete per produrre una scorecard che consenta di determinare l'integrità del server di una distribuzione di Lync. Una volta popolata, viene fornita una guida per la riparazione dell'ambiente e per informazioni aggiuntive su altre parti interessate. Valutare KHIs su base mensile e inserirli nei processi operativi in continua distribuzione.

Scaricare la [Guida alla rete di Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677) per visualizzare l'elenco completo di KHIs e per ottenere i fogli di calcolo correlati.

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>Per raccogliere i dati di KHI

1.  Eseguire lo script KHI incluso nella Guida alla rete di Lync Server in ogni server Lync. In questo modo verrà creato un agente di raccolta dati all'interno di performance monitor e il nome KHI. Per impostazione predefinita, i dati verranno sottoposti a polling ogni 15 secondi.

2.  Prima dell'inizio della giornata lavorativa della società, passare a ogni server Lync e avviare l'agente di raccolta dati di KHI.

3.  Alla fine di quel giorno, arrestare l'agente di raccolta dati di KHI e copiare i dati in una posizione centrale.

4.  Dopo aver utilizzato Performance Monitor per compilare il foglio di calcolo di KHI incluso nel download della Guida alla rete di Lync Server, confrontare i risultati con gli obiettivi consigliati.

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>Flusso di correzione per tutti i ruoli del server

Per ogni server dell'implementazione di Lync, iniziare verificando che le prestazioni del sistema e dell'integrità del componente del server siano pari o superiori al livello desiderato. Solo dopo, è necessario esaminare gli indicatori relativi al ruolo del server nell'implementazione complessiva di Lync.

Iniziare raccogliendo i dati sulle prestazioni di KHI per tutti i server. Per ogni ruolo di sistema (dettagli descritti più avanti in questo documento) determinare se i componenti di sistema di base soddisfano le destinazioni consigliate. In caso contrario, correggere le prestazioni del sistema e quindi raccogliere di nuovo i dati di KHI e garantire l'integrità del sistema prima di esaminare le metriche specifiche del ruolo del server nell'implementazione di Lync. L'integrità dei componenti per tutti i ruoli è definita come segue:

  - Utilizzo della CPU \< 80%

  - AVG. Disk Write \< 10 ms

  - AVG. Disk Read \< 10 ms

  - Memoria disponibile \> 20% System Total MB

  - Lunghezza coda di rete \< 2

  - Pacchetti scartati (in/out) = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>Glossario

In questo poster vengono utilizzati i termini e gli acronimi seguenti:

Come MCU = unità di controllo a più punti di condivisione applicazioni

MCU AV = MCU audio/video

MCU IM = MCU di messaggistica istantanea

UCWA = API Web per le comunicazioni unificate

AV Edge = attraversamento di audio/video tramite Edge

AV auth = autenticazione audio/video

SIP stack = contiene l'implementazione SIP di base di Lync

Proxy di dati = utilizzato per le conferenze Edge

LySS = servizio di archiviazione di Lync

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>Server front-end

Le seguenti destinazioni KHI consigliate sono specifiche per i server front-end oltre all'integrità dei componenti di base:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Area funzionale</th>
<th>Metriche di destinazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>MCU AS/AV/IM</p></td>
<td><p>Stato di integrità MCU &lt; 2</p></td>
</tr>
<tr class="even">
<td><p>Web Components</p></td>
<td><p>Timeout di espansione della lista di distribuzione- &lt; 0</p>
<p>Errori di ABWQ = 0</p>
<p>Errori LIS = 0</p>
<p>Errori di autenticazione &lt; 1/sec</p>
<p>Richieste di ASP.NET v4 rifiutate = 0</p></td>
</tr>
<tr class="odd">
<td><p>Stack SIP</p></td>
<td><p>Elaborazione dei messaggi in arrivo &lt; 1 secondo</p>
<p>Risposte in ingresso rilasciate &lt; 1/sec le richieste in arrivo sono state perse &lt; 1/sec</p>
<p>Latenza coda &lt; 100 ms</p>
<p>Latenza SPROC &lt; 100 ms</p>
<p>Richieste limitate = 0</p>
<p>Errori di autenticazione &lt; 1/sec</p>
<p>Timeout dei messaggi in arrivo &lt; 2</p>
<p>AVG. messaggio in arrivo in attesa &lt; 1 secondo</p>
<p>Connessioni controllate dal flusso &lt; 2</p>
<p>Ritardo della coda di AVG. out &lt; 2 sec</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>% dello spazio utilizzato dal servizio di archiviazione DB &lt; 80</p>
<p># degli errori di replica di replica = 0</p>
<p># degli eventi di perdita di dati = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Durata della pagina &gt; 300 sec.</p>
<p>Richieste batch/sec &lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>Server SQL back-end

Le seguenti destinazioni KHI consigliate sono specifiche per i server SQL oltre che per l'integrità dei componenti di base:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Area funzionale</th>
<th>Metriche di destinazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Durata della pagina &gt; 300 sec.</p>
<p>Richieste batch/sec &lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>Mediation Server

Le seguenti destinazioni KHI consigliate sono specifiche per i Mediation Server oltre all'integrità dei componenti di base:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Area funzionale</th>
<th>Metriche di destinazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servizio Mediation Server</p></td>
<td><p>Indice di errore di chiamata di carico = 0</p>
<p>Chiamate non riuscite a causa del proxy &lt; 10</p>
<p>Chiamate non riuscite a causa del gateway &lt; 10</p>
<p>Chiamate (dentro o fuori) rifiutate = 0</p>
<p>Candidati ai media mancanti = 0</p>
<p>Errori di controllo della connettività multimediale = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>server perimetrali

Le seguenti destinazioni KHI consigliate sono specifiche per i server perimetrali oltre all'integrità dei componenti di base:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Area funzionale</th>
<th>Metriche di destinazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autenticazione AV</p></td>
<td><p>Richieste non valide &lt; 20/sec</p></td>
</tr>
<tr class="even">
<td><p>AV Edge</p></td>
<td><p>Auth. Failures &lt; 20/sec</p>
<p>Errori di allocazione &lt; 20/sec</p>
<p>Pacchetti rilasciati &lt; 300/sec</p></td>
</tr>
<tr class="odd">
<td><p>Proxy di dati</p></td>
<td><p>Connessioni server limitate &lt; 3</p>
<p>Il sistema ha la limitazione &lt; 1</p></td>
</tr>
<tr class="even">
<td><p>Stack SIP</p></td>
<td><p>Connessioni su limite eliminato &lt; 1</p>
<p>Invia scaduta &lt; 10</p>
<p>Connessioni controllate dal flusso &lt; 100</p>
<p>Richieste in ingresso interrotte &lt; 1/sec</p>
<p>Elaborazione media dei messaggi &lt; 3 sec</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vedere anche


[Guida alla rete di Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[Indicatori di integrità chiave: la base per la gestione dei server Lync integri](https://go.microsoft.com/fwlink/?linkid=391838)  
[Metodologia qualità chiamata Lync](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

