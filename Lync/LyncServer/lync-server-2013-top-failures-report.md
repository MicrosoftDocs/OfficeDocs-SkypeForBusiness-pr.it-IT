---
title: 'Lync Server 2013: rapporto errori principali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47bb2a36d3d165150735a4b0e4b44907a0d86011
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503763"
---
# <a name="top-failures-report-in-lync-server-2013"></a>Rapporto errori principali in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Nel Rapporto errori principali vengono esaminati gli errori rilevati più di frequente con la relativa tendenza nel tempo. Gli errori sono basati su una combinazione delle due metriche seguenti:

  - **ID diagnostica**. Identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi relativi alle chiamate.

  - **Codice di risposta**. I codici di risposta vengono utilizzati nelle sessioni di comunicazione SIP per rispondere alle richieste SIP. Ad esempio, si supponga che Ken invii la richiesta di invito a Pilar Ackerman (ovvero, supponiamo che Ken remario chiami Pilar Ackerman). Se le risposte di Pilar, il suo telefono invierà il codice di risposta 200 (OK), lasciando che il telefono di Ken sappia che Pilar ha risposto. Il rapporto errori principali include solo codici di risposta inviati in risposta a un errore di chiamata; Lync Server non tiene conto di tutti i codici di risposta rilasciati durante il corso di una chiamata.

Le informazioni vengono registrate nel rapporto non solo per il numero totale di sessioni in cui si è verificato un errore, ma anche per il numero totale di utenti che hanno subito l'errore.

<div>

## <a name="accessing-the-top-failures-report"></a>Accesso al Rapporto errori principali

È possibile accedere al Rapporto errori principali dalla home page Relazioni monitoraggio. Se si fa clic sulla metrica sessioni segnalate, verrà visualizzato il [rapporto distribuzione errori in Lync Server 2013](lync-server-2013-failure-distribution-report.md).

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a>Utilizzo ottimale del Rapporto errori principali

Il Rapporto errori principali è insolito per un aspetto: consente di applicare un filtro che può includere fino a 5 ID diagnostica alla volta, laddove in genere può includere un solo elemento, ad esempio un indirizzo SIP utente alla volta. Per applicare un filtro in base a più ID diagnostica, è sufficiente immettere i singoli ID nella casella apposita separandoli tramite virgole. Se si vuole, è possibile lasciare uno spazio bianco dopo ogni virgola, come nell'esempio:

1011, 2412, 1033, 52116, 1008

Così facendo verranno visualizzate solo le chiamate non riuscite che hanno riportato almeno uno dei cinque ID diagnostica indicati.

Se si tiene il mouse posizionato su un codice di risposta, viene visualizzata una descrizione comando che ne spiega il significato. Se ad esempio si tiene il mouse posizionato sul codice di risposta 486, verrà visualizzato il messaggio seguente:

Non disponibile qui.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Il Rapporto errori principali ad esempio consente di filtrare i dati restituiti in base a fattori come il tipo di attività, ovvero sessione peer-to-peer o di conferenza, oppure in base al codice di risposta SIP associato alla sessione in cui si è verificato l'errore. È inoltre possibile scegliere come raggruppare i dati. In questo caso, gli utilizzi vengono raggruppati per ora, giorno, settimana o mese.

Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto errori principali.

### <a name="top-failures-report-filters"></a>Filtri del Rapporto errori principali

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</p>
<p>07/07/2012 13.00</p>
<p>Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane vanno sempre dal lunedì alla domenica.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</p>
<p>07/07/2012 13.00</p>
<p>Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane vengono calcolate sempre dal lunedì alla domenica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo di attività</strong></p></td>
<td><p>Tipo di attività. Selezionare uno dei valori seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Peer-to-peer</p></li>
<li><p>Conferenza</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Modalità</strong></p></td>
<td><p>L'unica opzione disponibile attualmente è <strong>[Tutto]</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su <strong>[Tutto]</strong> per visualizzare i dati relativi a tutti i pool. Questo elenco a discesa viene popolato automaticamente in base ai record del database.</p></td>
</tr>
<tr class="even">
<td><p><strong>Categoria</strong></p></td>
<td><p>Tipo di errore. Selezionare uno dei tipi seguenti:</p>
<ul>
<li><p>Errore sia previsto che imprevisto</p></li>
<li><p>Errore imprevisto</p></li>
</ul>
<p>Un &quot; errore previsto &quot; è un errore che dovrebbe verificarsi. Se ad esempio un utente ha impostato il proprio stato su Non disturbare, è previsto che le chiamate effettuate per tale utente abbiano esito negativo. Un &quot; errore imprevisto &quot; è un errore che si verifica in un sistema altrimenti integro. Una chiamata ad esempio non dovrebbe interrompersi quando il chiamante viene messo in attesa. Se la chiamata si interrompe, l'evento verrà contrassegnato come errore imprevisto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Codice di risposta</strong></p></td>
<td><p>Codice di risposta SIP inviato quando si è verificato l'errore di conferenza. Immettere l'intero codice di risposta, ad esempio:</p>
<p>400</p></td>
</tr>
<tr class="even">
<td><p><strong>ID diagnostica</strong></p></td>
<td><p>Identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi. Le intestazioni di diagnostica sono facoltative (è possibile che in alcune sessioni SIP non siano incluse queste intestazioni) e gli ID diagnostica sono spesso indicati solo per sessioni in cui si sono verificati problemi di un determinato tipo.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente vengono elencate le informazioni fornite nel Rapporto errori principali.

### <a name="top-failures-report-metrics"></a>Metrica del Rapporto errori principali

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Elemento utilizzabile per eseguire l'ordinamento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Classificazione</strong></p></td>
<td><p>Sì</p></td>
<td><p>Classificazione relativa basata sul numero di sessioni segnalate.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessioni segnalate</strong></p></td>
<td><p>Sì</p></td>
<td><p>Numero totale di sessioni non riuscite in base all'ID diagnostica e al codice di risposta SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Utenti interessati</strong></p></td>
<td><p>Sì</p></td>
<td><p>Numero totale di utenti interessati dalla sessione non riuscita.</p></td>
</tr>
<tr class="even">
<td><p><strong>Informazioni sull'errore</strong></p></td>
<td><p>No</p></td>
<td><p>Informazioni dettagliate sull'errore, tra cui l'ID diagnostica, il codice di risposta SIP e la descrizione del motivo per cui la sessione ha avuto esito negativo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tendenza passato</strong></p></td>
<td><p>No</p></td>
<td><p>Rappresentazione grafica delle sessioni non riuscite nel tempo.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

