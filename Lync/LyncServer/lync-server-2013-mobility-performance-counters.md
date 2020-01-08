---
title: 'Lync Server 2013: contatori delle prestazioni mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c0759ccd6a9203dfac87f0ec55f555d49d19ccc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a>Contatori delle prestazioni di mobilità in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

Le tabelle seguenti elencano i nomi e le descrizioni dei contatori delle prestazioni che è possibile usare per monitorare i server che usano Unified Communications Web API (UCWA) e il servizio di mobilità MCX di Lync Server 2013.

Il nome della categoria per i contatori nella tabella UCWA è **ls: Web – UCWA**.

Il nome della categoria per i contatori nella tabella del servizio di mobilità MCX è **ls: Web-servizio di comunicazione mobile**.

<div>

## <a name="performance-counters-for-ucwa"></a>Contatori delle prestazioni per UCWA


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Contatore</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Conteggio applicazioni attive</p></td>
<td><p>Numero corrente di applicazioni</p></td>
</tr>
<tr class="even">
<td><p>Conteggio delle modalità di condivisione delle applicazioni attive</p></td>
<td><p>Numero corrente di modalità di condivisione delle applicazioni</p></td>
</tr>
<tr class="odd">
<td><p>Conteggio modalità audio attiva</p></td>
<td><p>Numero corrente di modalità audio</p></td>
</tr>
<tr class="even">
<td><p>Conteggio delle modalità di collaborazione con i dati attivi</p></td>
<td><p>Numero corrente di modalità di collaborazione dei dati</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory Photo Get latenza (MS)</p></td>
<td><p>Questo contatore mostra il tempo medio (in millisecondi) per recuperare una foto da Active Directory</p></td>
</tr>
<tr class="even">
<td><p>Conteggio delle modalità di messaggistica attiva</p></td>
<td><p>Numero corrente di modalità di messaggistica</p></td>
</tr>
<tr class="odd">
<td><p>Conteggio delle modalità video panoramico attivo</p></td>
<td><p>Numero corrente di modalità video panoramico</p></td>
</tr>
<tr class="even">
<td><p>Conteggio in sospeso attivo</p></td>
<td><p>Il numero di ritorni in sospeso attualmente attivi; connessioni Long-Held al server</p></td>
</tr>
<tr class="odd">
<td><p>Conteggio sessioni attive</p></td>
<td><p>Numero corrente di endpoint registrati in UCWA per applicazione e totale</p></td>
</tr>
<tr class="even">
<td><p>Conteggio istanze utente attivo</p></td>
<td><p>Numero corrente di istanze utente</p></td>
</tr>
<tr class="odd">
<td><p>Istanze utente attive senza applicazione</p></td>
<td><p>Numero corrente di istanze utente senza applicazione</p></td>
</tr>
<tr class="even">
<td><p>Conteggio modalità video attivo</p></td>
<td><p>Numero corrente di modalità video</p></td>
</tr>
<tr class="odd">
<td><p>Richieste di creazione di applicazioni ricevute/seconde</p></td>
<td><p>Tasso per secondo delle richieste di creazione di applicazioni ricevute</p></td>
</tr>
<tr class="even">
<td><p>Errori di join di MCU</p></td>
<td><p>Numero di errori di join di MCU</p></td>
</tr>
<tr class="odd">
<td><p>Errore di join di MCU AV</p></td>
<td><p>Numero di errori di join di MCU AV</p></td>
</tr>
<tr class="even">
<td><p>Tempo di avvio dell'applicazione medio (MS)</p></td>
<td><p>Tempo di avvio dell'applicazione medio in millisecondi</p></td>
</tr>
<tr class="odd">
<td><p>Durata media per la sessione (MS)</p></td>
<td><p>Durata media per una sessione in millisecondi</p></td>
</tr>
<tr class="even">
<td><p>Errori di join di MCU dati</p></td>
<td><p>Numero di errori di join di MCU dati</p></td>
</tr>
<tr class="odd">
<td><p>Latenza ricerca contatti di Exchange (MS)</p></td>
<td><p>Questo contatore mostra il tempo medio (in millisecondi) per cercare il contatto in Exchange</p></td>
</tr>
<tr class="even">
<td><p>Exchange HD Photo Get latenza (MS)</p></td>
<td><p>Questo contatore mostra il tempo medio (in millisecondi) per recuperare una foto da Exchange</p></td>
</tr>
<tr class="odd">
<td><p>Risposte 4xx HTTP/secondo</p></td>
<td><p>Il tasso di risposta al secondo con il codice HTTP 4xx</p></td>
</tr>
<tr class="even">
<td><p>Risposte 5xx HTTP/secondo</p></td>
<td><p>Il tasso di risposta al secondo con il codice HTTP 5xx</p></td>
</tr>
<tr class="odd">
<td><p>Errori di join di MCU di messaggistica istantanea</p></td>
<td><p>Numero di errori di join di MCU di messaggistica istantanea</p></td>
</tr>
<tr class="even">
<td><p>Numero di foto di Active Directory Get Failures</p></td>
<td><p>Numero totale di errori per il recupero di foto da Active Directory</p></td>
</tr>
<tr class="odd">
<td><p>Numero di errori di ricerca dei contatti</p></td>
<td><p>Numero totale di errori per cercare i contatti in Exchange</p></td>
</tr>
<tr class="even">
<td><p>Numero di errori di deserializzazione</p></td>
<td><p>Numero totale di errori di deserializzazione</p></td>
</tr>
<tr class="odd">
<td><p>Numero di errori di ottenimento della foto HD</p></td>
<td><p>Numero totale di errori per recuperare le foto HD da Exchange</p></td>
</tr>
<tr class="even">
<td><p>Oltre il numero massimo di abbonamenti per applicazione</p></td>
<td><p>Numero di richieste di sottoscrizione sul massimo consentito per ogni applicazione</p></td>
</tr>
<tr class="odd">
<td><p>Oltre il numero massimo di abbonamenti per batch</p></td>
<td><p>Numero di richieste di sottoscrizione sul massimo consentito per batch</p></td>
</tr>
<tr class="even">
<td><p>Errori di sottoscrizione presenza</p></td>
<td><p>Numero di errori di sottoscrizione della presenza</p></td>
</tr>
<tr class="odd">
<td><p>Registrazione degli errori di endpoint</p></td>
<td><p>Numero di errori per la registrazione degli endpoint</p></td>
</tr>
<tr class="even">
<td><p>Richieste ricevute/seconde</p></td>
<td><p>Tasso per secondo delle richieste ricevute</p></td>
</tr>
<tr class="odd">
<td><p>Richieste succeeded/Second</p></td>
<td><p>Il tasso per secondo delle richieste di successo (codici di risposta HTTP 2xx/3xx)</p></td>
</tr>
<tr class="even">
<td><p>Succeeded Create application requests/Second</p></td>
<td><p>Tasso per secondo delle richieste di creazione di applicazioni di successo</p></td>
</tr>
<tr class="odd">
<td><p>Conteggio scaduto in sospeso</p></td>
<td><p>Il numero di operazioni in sospeso viene scaduta</p></td>
</tr>
<tr class="even">
<td><p>Totale richieste di creazione di applicazioni ricevute</p></td>
<td><p>Numero totale di richieste di creazione di applicazioni ricevute dopo l'avvio del servizio</p></td>
</tr>
<tr class="odd">
<td><p>Risposte 4xx totali HTTP</p></td>
<td><p>Numero totale di risposte 4xx HTTP</p></td>
</tr>
<tr class="even">
<td><p>Risposte 5xx totali HTTP</p></td>
<td><p>Numero totale di risposte 5xx HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Totale richieste ricevute nel canale di comando</p></td>
<td><p>Numero totale di richieste ricevute nel canale di comando</p></td>
</tr>
<tr class="even">
<td><p>Totale richieste riuscite</p></td>
<td><p>Numero totale di richieste che sono state riuscite</p></td>
</tr>
<tr class="odd">
<td><p>Totale delle sessioni avviate</p></td>
<td><p>Numero totale di sessioni avviate dopo l'avvio del servizio</p></td>
</tr>
<tr class="even">
<td><p>Totale delle sessioni terminate a causa del timeout inattivo</p></td>
<td><p>Numero totale di sessioni terminate a causa del timeout di inattività dell'utente</p></td>
</tr>
<tr class="odd">
<td><p>Totale applicazioni a limitazione</p></td>
<td><p>Numero di applicazioni limitate</p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a>Contatori delle prestazioni per il servizio di mobilità MCX

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Contatore</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Durata media per una sessione in millisecondi</p></td>
<td><p>Durata media per una sessione in millisecondi</p></td>
</tr>
<tr class="even">
<td><p>Abbonamenti alle notifiche push correnti</p></td>
<td><p>Numero corrente di abbonamenti alle notifiche push. Questo numero, in combinazione con il conteggio delle sessioni attivo, rappresenta il sottoinsieme delle sessioni attualmente attive registrate per i dispositivi Windows Mobile o iPhone.</p></td>
</tr>
<tr class="odd">
<td><p>Conteggio del sondaggio di timeout di rete attualmente attivo</p></td>
<td><p>Numero di sondaggi di rete scaduti</p></td>
</tr>
<tr class="even">
<td><p>Conteggio sondaggi attualmente attivi</p></td>
<td><p>Numero di sondaggi attualmente attivi (connessioni a lungo termine al server)</p></td>
</tr>
<tr class="odd">
<td><p>Conteggio sessioni attualmente attivo</p></td>
<td><p>Numero corrente di endpoint registrati nel servizio mobilità</p></td>
</tr>
<tr class="even">
<td><p>Conteggio sessioni attivo con abbonamenti alla presenza attiva</p></td>
<td><p>Numero di sessioni attualmente attive con abbonamenti a presenza attiva</p></td>
</tr>
<tr class="odd">
<td><p>Richieste di notifica push fallite/seconde</p></td>
<td><p>Frequenza per il secondo delle notifiche push non riuscite</p></td>
</tr>
<tr class="even">
<td><p>Richieste di notifica push succeeded/Second</p></td>
<td><p>Il tasso al secondo delle notifiche push di successo</p></td>
</tr>
<tr class="odd">
<td><p>Richieste di notifica push Throttled/Second</p></td>
<td><p>Il tasso al secondo delle notifiche push limitate</p></td>
</tr>
<tr class="even">
<td><p>Richieste di notifica push/secondo</p></td>
<td><p>Il tasso al secondo delle notifiche push inviate</p></td>
</tr>
<tr class="odd">
<td><p>Richieste non riuscite/secondo</p></td>
<td><p>Tasso per secondo delle richieste non riuscite</p></td>
</tr>
<tr class="even">
<td><p>Richieste ricevute/seconde</p></td>
<td><p>Tasso per secondo delle richieste ricevute</p></td>
</tr>
<tr class="odd">
<td><p>Richieste rifiutate/seconde</p></td>
<td><p>Tasso al secondo delle richieste rifiutate</p></td>
</tr>
<tr class="even">
<td><p>Richieste succeeded/Second</p></td>
<td><p>Il tasso al secondo delle richieste di successo</p></td>
</tr>
<tr class="odd">
<td><p>Le richieste di sessione avviate sono successe al secondo</p></td>
<td><p>Il tasso al secondo delle richieste di posizione di ottenimento riuscito. Le richieste di avvio di una sessione utilizzano la maggior parte della CPU nel server. Il carico supportato di picco è 12/secondo. La sostenibilità dipende da altri carichi nel server. L'avvio di una sessione in genere indica un accesso per un utente che è stato disconnesso per un periodo di tempo prolungato.</p></td>
</tr>
<tr class="even">
<td><p>Chiamate vocali in ingresso rifiutate totali</p></td>
<td><p>Numero totale di chiamate vocali in ingresso rifiutate</p></td>
</tr>
<tr class="odd">
<td><p>Totale chiamate vocali in ingresso non riuscito</p></td>
<td><p>Numero totale di chiamate vocali in ingresso non riuscite</p></td>
</tr>
<tr class="even">
<td><p>Totale chiamate vocali in uscita non riuscite</p></td>
<td><p>Numero totale di chiamate vocali in uscita non riuscite</p></td>
</tr>
<tr class="odd">
<td><p>Numero totale di sessioni terminate dall'utente</p></td>
<td><p>Numero totale di sessioni terminate dagli utenti</p></td>
</tr>
<tr class="even">
<td><p>Totale richieste di notifica push</p></td>
<td><p>Numero totale di richieste di notifica push</p></td>
</tr>
<tr class="odd">
<td><p>Totale richieste di notifica push non riuscite</p></td>
<td><p>Numero totale di richieste di notifica push non riuscite</p></td>
</tr>
<tr class="even">
<td><p>Totale richieste di notifica push riuscite</p></td>
<td><p>Numero totale di richieste di notifica push che hanno avuto esito positivo</p></td>
</tr>
<tr class="odd">
<td><p>Richieste di notifica push totali limitate</p></td>
<td><p>Numero totale di richieste di notifica push che sono state strozzate</p></td>
</tr>
<tr class="even">
<td><p>Totale richieste non riuscite</p></td>
<td><p>Numero totale di richieste non riuscite</p></td>
</tr>
<tr class="odd">
<td><p>Totale richieste ricevute nel canale di comando</p></td>
<td><p>Numero totale di richieste ricevute nel canale di comando</p></td>
</tr>
<tr class="even">
<td><p>Totale richieste rifiutate</p></td>
<td><p>Numero totale di richieste rifiutate</p></td>
</tr>
<tr class="odd">
<td><p>Totale richieste riuscite</p></td>
<td><p>Numero totale di richieste effettuate al servizio di mobilità riuscito</p></td>
</tr>
<tr class="even">
<td><p>Numero totale avviato dalla sessione</p></td>
<td><p>Numero totale di sessioni avviate da quando è stato avviato il servizio di mobilità</p></td>
</tr>
<tr class="odd">
<td><p>Totale delle sessioni terminate a causa del timeout di inattività dell'utente</p></td>
<td><p>Numero totale di sessioni terminate a causa del timeout di inattività dell'utente</p></td>
</tr>
<tr class="even">
<td><p>Totale successo delle chiamate vocali in entrata</p></td>
<td><p>Numero totale di chiamate vocali in entrata che hanno avuto esito positivo</p></td>
</tr>
<tr class="odd">
<td><p>Totale successo delle chiamate vocali in uscita</p></td>
<td><p>Numero totale di chiamate vocali in uscita che hanno avuto esito positivo</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

