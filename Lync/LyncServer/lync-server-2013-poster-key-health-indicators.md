---
title: 'Lync Server 2013: poster: indicatori di integrità chiave'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9454197642ac87f5d8bc0d768795854d792f9a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a>Indicatori di integrità chiave in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-10_

Questo articolo è un complemento per gli [indicatori di integrità chiave: la base per il mantenimento](http://go.microsoft.com/fwlink/?linkid=391838) di un poster di Lync Server sani, che è possibile scaricare dall'area download.

![Poster che descrive la risoluzione dei problemi con KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "poster che descrive la risoluzione dei problemi usando i dati di KHI")

Puoi usare questo poster per informazioni sugli indicatori di integrità chiave (KHIs), sui contatori delle prestazioni con soglie mirate a rivelare i problemi di esperienza utente. La raccolta dei dati di KHI è in genere il primo passaggio per implementare la metodologia di qualità delle chiamate (CQM), focalizzata sulla garanzia di un'esperienza audio di qualità per gli utenti di Lync.

In caso di domande su come usare CQM, è possibile inviare le proprie domande a cqmfeedback@microsoft.com.

Il poster illustra le aree seguenti:

  - Che cosa sono gli indicatori di integrità chiave?

  - Per raccogliere dati di KHI

  - Flusso di correzione per tutti i ruoli del server

  - Glossario

  - Server front-end

  - Server SQL back-end

  - Mediation Server

  - Edge Server

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>Che cosa sono gli indicatori di integrità chiave?

Gli indicatori di integrità principali sono contatori delle prestazioni con soglie mirate a rivelare i problemi di esperienza utente. La raccolta dei dati di KHI è in genere il primo passaggio per implementare la metodologia di qualità delle chiamate (CQM), focalizzata sulla garanzia di un'esperienza audio di qualità per gli utenti di Lync.

KHIs vengono usati in aggiunta alle soluzioni di monitoraggio di Lync standard (ad esempio System Center Operations Manager, transazioni sintetiche, server di monitoraggio) e non al posto di tali soluzioni.

Raccogliere i contatori delle prestazioni di KHI e popolare il foglio di calcolo di KHI che accompagna la guida alla rete per produrre una scorecard che consentirà di determinare l'integrità del server di una distribuzione Lync. Una volta popolato, ti guida a ripristinare l'ambiente e offre ulteriori informazioni ad altri stakeholder. Valuta KHIs su base mensile e incorporali nei processi operativi in corso per qualsiasi distribuzione.

Scaricare la [Guida alla rete Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677) per visualizzare l'elenco completo di KHIs e per ottenere i fogli di calcolo correlati.

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>Per raccogliere dati di KHI

1.  Eseguire lo script KHI incluso nella Guida di rete di Lync Server in ogni server Lync. Verrà creato un agente di raccolta dati all'interno di performance monitor e denominarlo KHI. Per impostazione predefinita, i dati verranno interrogati ogni 15 secondi.

2.  Prima dell'inizio del giorno lavorativo della società, accedere a ogni server Lync e avviare l'agente di raccolta dati di KHI.

3.  Alla fine del giorno, arrestare l'agente di raccolta dati KHI e copiare i dati in una posizione centrale.

4.  Dopo aver usato Performance Monitor per compilare il foglio di calcolo di KHI incluso nel download di Lync Server Networking Guide, confrontare i risultati con le destinazioni consigliate.

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>Flusso di correzione per tutti i ruoli del server

Per ogni server nell'implementazione di Lync, iniziare verificando che le prestazioni di integrità e di sistema del componente del server siano pari o superiori al livello desiderato. Solo dopo che dovrebbero essere esaminati gli indicatori relativi al ruolo del server nell'implementazione complessiva di Lync.

Iniziare raccogliendo i dati sulle prestazioni di KHI per tutti i server. Per ogni ruolo di sistema (dettagli descritti più avanti in questo documento) determinare se i componenti di sistema di base soddisfano le destinazioni consigliate. In caso contrario, correggere le prestazioni del sistema e quindi riraccogliere i dati di KHI e garantire l'integrità del sistema prima di esaminare le metriche specifiche del ruolo del server nell'implementazione di Lync. L'integrità dei componenti per tutti i ruoli è definita come segue:

  - Utilizzo della CPU \< 80%

  - Media scrittura \< disco 10 ms

  - Media Disk Read \< 10 ms

  - Memoria \>disponibile 20% System Total MB

  - Lunghezza \< coda di rete 2

  - Pacchetti scartati (in/out) = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>Glossario

In questo poster vengono usati i termini e gli acronimi seguenti:

Come MCU = unità di controllo a più punti di condivisione applicazioni

MCU AV = MCU audio/video

MCU IM = MCU di messaggistica istantanea

UCWA = API Web per comunicazioni unificate

AV Edge = attraversamento di audio/video tramite Edge

AV auth = autenticazione audio/video

SIP stack = contiene l'implementazione SIP di base di Lync

Proxy dati = usato per i servizi di conferenza Edge

LySS = servizio di archiviazione Lync

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>Server front-end

Le destinazioni di KHI consigliate seguenti sono specifiche per i server front-end oltre all'integrità dei componenti di base:


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
<td><p>Stato &lt;integrità MCU 2</p></td>
</tr>
<tr class="even">
<td><p>Componenti Web</p></td>
<td><p>Timeout degli annunci di espansione della &lt;lista di distribuzione 0</p>
<p>Errori di ABWQ = 0</p>
<p>Errori LIS = 0</p>
<p>Errori &lt; di autenticazione 1/sec</p>
<p>Richieste di ASP.NET v4 rifiutate = 0</p></td>
</tr>
<tr class="odd">
<td><p>Stack SIP</p></td>
<td><p>AVG. elaborazione &lt; del messaggio in arrivo 1 sec</p>
<p>Risposte in arrivo cadute &lt; 1/sec richieste in arrivo perse &lt; 1/sec</p>
<p>Latenza &lt; della coda 100 ms</p>
<p>Latenza &lt; SPROC 100 ms</p>
<p>Richieste strozzate = 0</p>
<p>Errori &lt; di autenticazione 1/sec</p>
<p>Messaggi in arrivo scaduti &lt; 2</p>
<p>Media messaggio in arrivo in attesa &lt; 1 sec</p>
<p>Connessioni &lt; controllate in flusso 2</p>
<p>Ritardo &lt; della coda media fuori 2 sec</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>% dello spazio usato dal servizio di archiviazione &lt; dB 80</p>
<p>#degli errori di replica della replica = 0</p>
<p>#di eventi di perdita dei dati = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Speranza di vita della &gt; pagina 300 sec.</p>
<p>Richieste batch/sec &lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>Server SQL back-end

Le destinazioni di KHI consigliate seguenti sono specifiche dei server SQL oltre all'integrità del componente di base:


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
<td><p>Speranza di vita della &gt; pagina 300 sec.</p>
<p>Richieste batch/sec &lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>Mediation Server

Le destinazioni di KHI consigliate seguenti sono specifiche di Mediation Server oltre a integrità dei componenti di base:


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
<td><p>Carica indice di errore chiamata = 0</p>
<p>Chiamate non riuscite a &lt;causa del proxy 10</p>
<p>Chiamate non riuscite a &lt;causa del gateway 10</p>
<p>Chiamate (dentro o fuori) rifiutate = 0</p>
<p>Candidati multimediali mancanti = 0</p>
<p>Errori di verifica della connettività multimediale = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>Edge Server

Le destinazioni di KHI consigliate seguenti sono specifiche per i server Edge oltre alla salute dei componenti di base:


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
<td><p>AV auth</p></td>
<td><p>Richieste &lt; errate 20/sec</p></td>
</tr>
<tr class="even">
<td><p>AV Edge</p></td>
<td><p>Auth. Failures &lt;20/sec</p>
<p>Errori &lt;di allocazione 20/sec</p>
<p>Pacchetti eliminati &lt;300/sec</p></td>
</tr>
<tr class="odd">
<td><p>Proxy dati</p></td>
<td><p>Connessioni &lt; server strozzate 3</p>
<p>Il sistema sta strozzando &lt;1</p></td>
</tr>
<tr class="even">
<td><p>Stack SIP</p></td>
<td><p>Connessioni oltre il limite &lt; 1</p>
<p>Invia scaduta &lt;10</p>
<p>Connessioni &lt;controllate in flusso 100</p>
<p>Richieste in arrivo perse &lt; 1/sec</p>
<p>Media elaborazione &lt; del messaggio 3 sec</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vedere anche


[Guida alla rete di Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Indicatori di integrità chiave: la base per il mantenimento di server Lync integri](http://go.microsoft.com/fwlink/?linkid=391838)  
[Metodologia di qualità delle chiamate di Lync](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

