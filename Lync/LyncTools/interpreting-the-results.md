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
ms.openlocfilehash: 484f10757dcbd1463b54cf70ac8d725402decb44
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>Interpretazione dei risultati

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-24_

Lo strumento Lync Server 2013 stress and performance (LyncPerfTool. exe) dispone di numerosi contatori che è possibile utilizzare per capire cosa sta facendo il client e se si verificano problemi.

<div>

## <a name="client-counters"></a>Contatori client

Ogni istanza di LyncPerfTool. exe in esecuzione dispone di un'istanza distinta dei contatori. Ogni istanza è denominata dal relativo ID di processo.

Se i client sono sovraccarichi, è possibile che si verifichino problemi. Per evitare questi problemi, eseguire le operazioni seguenti:

1.  Monitorare la CPU e l'utilizzo della memoria nei computer client. Se la CPU è costantemente al di sopra del 90%, ridurre il numero di utenti.

2.  Se l'ingombro della memoria è elevato, è possibile che si verifichino problemi se il file di paging non è abbastanza grande. Verificare che la carica di commit non colpisca il limite del computer. Se si esegue in limiti di memoria, è consigliabile aumentare le dimensioni del file di paging o ridurre il numero di utenti

Nelle tabelle riportate di seguito sono elencati i contatori delle prestazioni principali di LyncPerfTool.

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
<td><p>Tempo impiegato in minuti</p></td>
<td><p>Tempo trascorso dopo l'avvio del processo.</p></td>
</tr>
<tr class="even">
<td><p>Endpoint attivi</p></td>
<td><p>Numero di endpoint attualmente connessi al server.</p></td>
</tr>
<tr class="odd">
<td><p>Accessi non riusciti</p></td>
<td><p>Numero totale di errori di accesso endpoint.</p></td>
</tr>
<tr class="even">
<td><p>Tentativi di accesso</p></td>
<td><p>Numero totale di tentativi di accesso all'endpoint.</p></td>
</tr>
<tr class="odd">
<td><p>Endpoint disconnessi</p></td>
<td><p>Numero totale di endpoint che sono stati disconnessi.</p></td>
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
<td><p>Numero totale di tentativi di modifica della presenza. Per i diversi tipi di modifiche alla presenza, vedere il contatore delle prestazioni chiamate di tipo sepresence (Presence Type).</p></td>
</tr>
<tr class="even">
<td><p>Risposte di NNN per la presenza</p></td>
<td><p>Numero totale di codici di risposta nnn ricevuti dal server.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate GetPresence</p></td>
<td><p>Numero totale di tentativi di richiesta di presenza per ottenere.</p></td>
</tr>
<tr class="even">
<td><p>Risposte di NNN per GetPresence</p></td>
<td><p>Numero totale di codici di risposta nnn ricevuti dal server.</p></td>
</tr>
</tbody>
</table>


**Informazioni sul servizio Rubrica**

In questa categoria sono inclusi i contatori utilizzati per monitorare i download di file in ABS (Address Book Service) e le richieste del servizio query Web della Rubrica.


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
<td><p>Download di file in ABS Full/Delta tentati</p></td>
<td><p>Numero totale di richieste di download di file completi o Delta tentate.</p></td>
</tr>
<tr class="even">
<td><p>Download di file completi/Delta in ABS con esito positivo</p></td>
<td><p>Numero totale di richieste di download di file completi o Delta tentate.</p></td>
</tr>
<tr class="odd">
<td><p>Contatori correlati al servizio query Web della Rubrica</p></td>
<td><p>Contatori relativi al download di file della Rubrica.</p></td>
</tr>
<tr class="even">
<td><p>Tentativi di WS ABS</p></td>
<td><p>Numero totale di richieste del servizio query Web della rubrica tentate.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate in ABS WS con esito positivo</p></td>
<td><p>Numero totale di richieste del servizio di query Web della rubrica che hanno restituito un codice di risposta corretto.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate in ABS WS non riuscite</p></td>
<td><p>Numero totale di richieste del servizio di query Web della rubrica che hanno restituito un codice di risposta di errore.</p></td>
</tr>
</tbody>
</table>


**Informazioni sulle liste di distribuzione (DL)**


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
<td><p>Tentativi di chiamata</p></td>
<td><p>Numero totale di richieste del servizio Web di espansione della lista di distribuzione (DLX) tentate.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate con esito positivo</p></td>
<td><p>Numero totale di richieste del servizio Web DLX che hanno restituito un codice di risposta corretto.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate non riuscite</p></td>
<td><p>Numero totale di richieste del servizio Web DLX che hanno restituito un codice di risposta di errore.</p></td>
</tr>
</tbody>
</table>


**Informazioni di base sul VoIP**

I contatori delle prestazioni elencati di seguito numeri di rapporto per tutte le chiamate VoIP (Voice over IP), incluse le chiamate a Mediation Server, A/V Conferencing Server, Edge Server, Response Group Application e Conference Auto Attendant, quando questi scenari sono abilitati.


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
<td><p>Numero totale di chiamate vocali in ingresso/in uscita attualmente in corso.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate terminate</p></td>
<td><p>Numero totale di chiamate vocali in ingresso/in uscita già terminate.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate rifiutate</p></td>
<td><p>Il numero totale di chiamate vocali in ingresso è stato rifiutato.</p></td>
</tr>
<tr class="even">
<td><p>Tentativi di chiamata in arrivo/in uscita</p></td>
<td><p>Numero totale di chiamate vocali in ingresso/in uscita tentate.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate in ingresso/in uscita stabilite</p></td>
<td><p>Numero totale di chiamate vocali in ingresso/in uscita stabilite.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate NNN ricevute</p></td>
<td><p>Numero totale di codici di risposta nnn ricevuti dal server.</p></td>
</tr>
<tr class="odd">
<td><p>Velocità di passaggio VoIP (%)</p></td>
<td><p>Total calls established/Total calls Tented.</p></td>
</tr>
</tbody>
</table>


**Informazioni sulle chiamate di servizio di Response Group**


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
<td><p>Tentativi di chiamata</p></td>
<td><p>Numero totale di chiamate tentate.</p></td>
</tr>
</tbody>
</table>


**Informazioni sulle chiamate di messaggistica immediata**


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
<td><p>Numero totale di chiamate di messaggistica istantanea in ingresso/in uscita già terminate.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate NNN ricevute</p></td>
<td><p>Numero totale di codici di risposta nnn ricevuti dal server.</p></td>
</tr>
<tr class="even">
<td><p>Messaggi di messaggistica istantanea ricevuti/inviati</p></td>
<td><p>Numero totale di messaggi ricevuti o inviati per tutte le sessioni.</p></td>
</tr>
<tr class="odd">
<td><p>Tentativi di chiamata in arrivo/in uscita</p></td>
<td><p>Numero totale di chiamate di messaggistica istantanea in arrivo/in uscita tentate.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate in ingresso/in uscita stabilite</p></td>
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
<td><p>Numero totale di chiamate di condivisione delle applicazioni in arrivo/in uscita.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate terminate</p></td>
<td><p>Numero totale di chiamate di condivisione applicazioni in ingresso/in uscita già terminate.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate NNN ricevute</p></td>
<td><p>Numero totale di codici di risposta nnn ricevuti dal server.</p></td>
</tr>
<tr class="even">
<td><p>Tentativi di chiamata in arrivo/in uscita</p></td>
<td><p>Numero totale di chiamate di condivisione applicazioni in ingresso/in uscita tentate.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamate in ingresso/in uscita stabilite</p></td>
<td><p>Numero totale di chiamate di condivisione delle applicazioni in ingresso/in uscita stabilite.</p></td>
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
<td><p>Numero totale di chiamate PSTN (Public Switched Telephone Network) in ingresso/in uscita attualmente in corso.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate terminate</p></td>
<td><p>Numero totale di chiamate PSTN in ingresso/in uscita già terminate.</p></td>
</tr>
<tr class="odd">
<td><p>Tentativi di chiamata in arrivo/in uscita</p></td>
<td><p>Numero totale di chiamate PSTN in ingresso/in uscita tentate.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate in ingresso/in uscita stabilite</p></td>
<td><p>Numero totale di chiamate PSTN in ingresso/in uscita stabilite.</p></td>
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
<td><p>Conferenze di messaggistica istantanea attive</p></td>
<td><p>Numero totale di conferenze di messaggistica istantanea in continuo.</p></td>
</tr>
<tr class="even">
<td><p>Conferenze audio/video attive</p></td>
<td><p>Numero totale di conferenze audio/video (A/V) in uscita.</p></td>
</tr>
<tr class="odd">
<td><p>Conferenze di condivisione applicazioni attive</p></td>
<td><p>Numero totale di conferenze di condivisione applicazioni in uscita.</p></td>
</tr>
<tr class="even">
<td><p>Numero di partecipanti</p></td>
<td><p>Numero totale di partecipanti attualmente connessi a conferenze.</p></td>
</tr>
<tr class="odd">
<td><p>Errore della pianificazione delle conferenze</p></td>
<td><p>Numero totale di errori durante il tentativo di pianificazione di una conferenza.</p></td>
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
<td><p>Numero totale di join IMMCU con esito positivo</p></td>
<td><p>Numero totale di conferenze di messaggistica istantanea Unite.</p></td>
</tr>
<tr class="even">
<td><p>Numero totale di join DMCU con esito positivo</p></td>
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

