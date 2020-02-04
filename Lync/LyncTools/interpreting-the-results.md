---
title: Interpretazione dei risultati
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dcb1d84392cf9f56f2996281eb53e798690ba1e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>Interpretazione dei risultati

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-24_

Lo strumento per lo stress e le prestazioni di Lync Server 2013 (LyncPerfTool. exe) contiene molti contatori che è possibile usare per capire cosa sta facendo il client e se si verificano problemi.

<div>

## <a name="client-counters"></a>Contatori client

Ogni istanza di LyncPerfTool. exe in uso ha un'istanza distinta dei contatori. Ogni istanza è denominata dall'ID processo.

Se i client sono sovraccaricati, è possibile che si verifichino problemi. Per evitare questi problemi, eseguire le operazioni seguenti:

1.  Monitorare la CPU e l'utilizzo della memoria nei computer client. Se la CPU è sempre superiore a 90%, ridurre il numero di utenti.

2.  Se l'impronta di memoria è elevata, è possibile che si verificano problemi se il file di pagina non è abbastanza grande. Verificare che la carica di conferma non colpisca il limite nel computer. Se si stanno esaurendo i limiti di memoria, valutare la possibilità di aumentare le dimensioni del file di pagina o ridurre il numero di utenti

Le tabelle seguenti elencano i contatori delle prestazioni LyncPerfTool chiave.

**Informazioni generali**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contatore delle prestazioni</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tempo trascorso in minuti</p></td>
<td><p>Tempo trascorso da quando il processo è stato avviato.</p></td>
</tr>
<tr class="even">
<td><p>Endpoint attivi</p></td>
<td><p>Numero di endpoint attualmente connessi al server.</p></td>
</tr>
<tr class="odd">
<td><p>Accessi non riusciti</p></td>
<td><p>Numero totale di errori di accesso di endpoint.</p></td>
</tr>
<tr class="even">
<td><p>Tentativi di accesso</p></td>
<td><p>Numero totale di tentativi di accesso di endpoint.</p></td>
</tr>
<tr class="odd">
<td><p>Endpoint disconnessi</p></td>
<td><p>Numero totale di endpoint disconnessi.</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**Informazioni sulla presenza**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contatore delle prestazioni</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamate di sepresenza</p></td>
<td><p>Numero totale di tentativi di modifica della presenza. Per i diversi tipi di modifiche alla presenza, Vedi il contatore delle prestazioni chiamate sepresenza (tipo presenza).</p></td>
</tr>
<tr class="even">
<td><p>Risposte di NNN per sepresenza</p></td>
<td><p>Numero totale di codici di risposta nnn ricevuti dal server.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate GetPresence</p></td>
<td><p>Numero totale di tentativi di richiesta di presenza Get.</p></td>
</tr>
<tr class="even">
<td><p>Risposte di NNN per GetPresence</p></td>
<td><p>Numero totale di codici di risposta nnn ricevuti dal server.</p></td>
</tr>
</tbody>
</table>


**Informazioni sul servizio Rubrica**

Questa categoria include i contatori usati per monitorare i download di file in ABS e le richieste di servizio query Web della Rubrica.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contatore delle prestazioni</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Download di file in ABS Full/Delta tentato</p></td>
<td><p>Numero totale di richieste di download di file completi o Delta tentate.</p></td>
</tr>
<tr class="even">
<td><p>Download di file completi/Delta di ABS riuscito</p></td>
<td><p>Numero totale di richieste di download di file completi o Delta tentate.</p></td>
</tr>
<tr class="odd">
<td><p>Contatori correlati al servizio query Web di Rubrica</p></td>
<td><p>Contatori correlati per il download del file della Rubrica.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate in ABS WS tentate</p></td>
<td><p>Numero totale di richieste di servizio query Web per la Rubrica.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate in ABS WS succeeded</p></td>
<td><p>Numero totale di richieste di servizio query Web per la rubrica che hanno restituito un codice di risposta riuscito.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate in ABS WS non riuscite</p></td>
<td><p>Numero totale di richieste di servizio query Web per la rubrica che hanno restituito un codice di risposta di errore.</p></td>
</tr>
</tbody>
</table>


**Informazioni sulla lista di distribuzione (DL)**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contatore delle prestazioni</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamate tentativo</p></td>
<td><p>Numero totale di richieste di servizio Web di espansione della lista di distribuzione (DLX) tentato.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate succeeded</p></td>
<td><p>Numero totale di richieste di servizio Web DLX che hanno restituito un codice di risposta riuscito.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate non riuscite</p></td>
<td><p>Numero totale di richieste di servizio Web DLX che hanno restituito un codice di risposta di errore.</p></td>
</tr>
</tbody>
</table>


**Informazioni di base su VoIP**

I contatori delle prestazioni elencati sotto i numeri di report per tutte le chiamate VoIP (Voice over IP), incluse le chiamate a Mediation Server, A/V Conferencing Server, Edge Server, Response Group Application e Conference Auto Attendant, quando questi scenari sono abilitati.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contatore delle prestazioni</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamate attive</p></td>
<td><p>Numero totale di chiamate vocali in arrivo/in uscita attualmente in corso.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate terminate</p></td>
<td><p>Numero totale di chiamate vocali in arrivo/in uscita già terminate.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate rifiutate</p></td>
<td><p>Numero totale di chiamate vocali in arrivo rifiutate.</p></td>
</tr>
<tr class="even">
<td><p>Tentativi di chiamata in arrivo/in uscita</p></td>
<td><p>Numero totale di chiamate vocali in arrivo/in uscita tentate.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate in arrivo/in uscita stabilite</p></td>
<td><p>Numero totale di chiamate vocali in arrivo/in uscita stabilite.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate di NNN ricevute</p></td>
<td><p>Numero totale di codici di risposta nnn ricevuti dal server.</p></td>
</tr>
<tr class="odd">
<td><p>Frequenza di abbonamento VoIP (%)</p></td>
<td><p>Total calls established/Total calls Tented.</p></td>
</tr>
</tbody>
</table>


**Informazioni sulle chiamate di servizio Response Group**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contatore delle prestazioni</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamate attive</p></td>
<td><p>Numero totale di chiamate attive all'applicazione Response Group.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate tentativo</p></td>
<td><p>Numero totale di chiamate tentate.</p></td>
</tr>
</tbody>
</table>


**Informazioni sulle chiamate di messaggistica istantanea (IM)**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contatore delle prestazioni</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamate attive</p></td>
<td><p>Numero totale di chiamate di messaggistica istantanea in arrivo/in uscita.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate terminate</p></td>
<td><p>Numero totale di chiamate di messaggistica istantanea in arrivo/in uscita già terminate.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate di NNN ricevute</p></td>
<td><p>Numero totale di codici di risposta nnn ricevuti dal server.</p></td>
</tr>
<tr class="even">
<td><p>Messaggi ISTANTANEi ricevuti/inviati</p></td>
<td><p>Numero totale di messaggi ricevuti o inviati per tutte le sessioni.</p></td>
</tr>
<tr class="odd">
<td><p>Tentativi di chiamata in arrivo/in uscita</p></td>
<td><p>Numero totale di chiamate di messaggistica istantanea in arrivo/in uscita tentate.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate in arrivo/in uscita stabilite</p></td>
<td><p>Numero totale di chiamate di messaggi istantanei in arrivo/in uscita stabilite.</p></td>
</tr>
</tbody>
</table>


**Informazioni sulle chiamate di condivisione delle app**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contatore delle prestazioni</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamate attive</p></td>
<td><p>Numero totale di chiamate di condivisione delle applicazioni in entrata e in uscita.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate terminate</p></td>
<td><p>Numero totale di chiamate di condivisione delle applicazioni in arrivo/in uscita già terminate.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate di NNN ricevute</p></td>
<td><p>Numero totale di codici di risposta nnn ricevuti dal server.</p></td>
</tr>
<tr class="even">
<td><p>Tentativi di chiamata in arrivo/in uscita</p></td>
<td><p>Numero totale di chiamate di condivisione delle applicazioni in arrivo/in uscita tentate.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate in arrivo/in uscita stabilite</p></td>
<td><p>Numero totale di chiamate di condivisione delle applicazioni in arrivo/in uscita stabilite.</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**Informazioni sulle chiamate CAA**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contatore delle prestazioni</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiamate attive</p></td>
<td><p>Numero totale di chiamate PSTN (Public Switched Telephone Network) in arrivo/in uscita attualmente in corso.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate terminate</p></td>
<td><p>Numero totale di chiamate PSTN in arrivo/in uscita già terminate.</p></td>
</tr>
<tr class="odd">
<td><p>Tentativi di chiamata in arrivo/in uscita</p></td>
<td><p>Numero totale di chiamate PSTN in arrivo/in uscita tentate.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate in arrivo/in uscita stabilite</p></td>
<td><p>Numero totale di chiamate PSTN in arrivo/in uscita stabilite.</p></td>
</tr>
</tbody>
</table>


**Informazioni sulla conferenza**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contatore delle prestazioni</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Conferenze di messaggistica istantanea attiva</p></td>
<td><p>Numero totale di conferenze di messaggistica istantanea in corso.</p></td>
</tr>
<tr class="even">
<td><p>Conferenze audio/video attive</p></td>
<td><p>Numero totale di conferenze audio/video (A/V) in corso.</p></td>
</tr>
<tr class="odd">
<td><p>Conferenze per la condivisione di applicazioni attive</p></td>
<td><p>Numero totale di conferenze di condivisione applicazioni in corso.</p></td>
</tr>
<tr class="even">
<td><p>Numero di partecipanti</p></td>
<td><p>Numero totale di partecipanti attualmente connessi alle conferenze.</p></td>
</tr>
<tr class="odd">
<td><p>Errore di programmazione conferenze</p></td>
<td><p>Numero totale di errori durante il tentativo di pianificare una conferenza.</p></td>
</tr>
<tr class="even">
<td><p>Partecipare a una conferenza non riuscita</p></td>
<td><p>Numero totale di errori durante il tentativo di connessione a una conferenza.</p></td>
</tr>
</tbody>
</table>


**Contatori client di UCWA**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contatore delle prestazioni</strong></th>
<th><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Numero totale di join IMMCU riusciti</p></td>
<td><p>Numero totale di conferenze di messaggistica istantanea Unite.</p></td>
</tr>
<tr class="even">
<td><p>Numero totale di join DMCU riusciti</p></td>
<td><p>Numero totale di conferenze A/V Unite.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

