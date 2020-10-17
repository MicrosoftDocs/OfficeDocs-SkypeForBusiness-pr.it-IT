---
title: 'Lync Server 2013: contatori delle prestazioni per dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37e36b4492814043317fcafb2612a28c9f4d7b91
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513603"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a>Contatori delle prestazioni per dispositivi mobili in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

Nelle tabelle riportate di seguito sono elencati i nomi e le descrizioni dei contatori delle prestazioni che è possibile utilizzare per monitorare i server che eseguono Unified Communications Web API (UCWA) e il servizio per dispositivi mobili di Lync Server 2013 MCX.

Il nome della categoria per i contatori nella tabella UCWA è **ls: Web – UCWA**.

Il nome della categoria per i contatori nella tabella dei servizi per dispositivi mobili di MCX è **ls: servizio di comunicazione web-mobile**.

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
<td><p>Numero di applicazioni attive</p></td>
<td><p>Il numero corrente di applicazioni</p></td>
</tr>
<tr class="even">
<td><p>Conteggio delle modalità di condivisione delle applicazioni attive</p></td>
<td><p>Numero corrente di modalità di condivisione delle applicazioni</p></td>
</tr>
<tr class="odd">
<td><p>Conteggio modalità audio attivo</p></td>
<td><p>Numero corrente di modalità audio</p></td>
</tr>
<tr class="even">
<td><p>Conteggio delle modalità di collaborazione dei dati attivi</p></td>
<td><p>Il numero corrente di modalità di collaborazione dei dati</p></td>
</tr>
<tr class="odd">
<td><p>Latenza della foto di Active Directory (MS)</p></td>
<td><p>Questo contatore indica il tempo medio (in millisecondi) per recuperare una foto da Active Directory</p></td>
</tr>
<tr class="even">
<td><p>Conteggio modalità di messaggistica attiva</p></td>
<td><p>Numero corrente di modalità di messaggistica</p></td>
</tr>
<tr class="odd">
<td><p>Conteggio delle modalità video panoramico attivo</p></td>
<td><p>Il numero corrente di modalità video panoramico</p></td>
</tr>
<tr class="even">
<td><p>Conteggio di ottenere attivo in sospeso</p></td>
<td><p>Il numero di in sospeso corrente viene attivato. connessioni Long-Held al server</p></td>
</tr>
<tr class="odd">
<td><p>Conteggio delle sessioni attive</p></td>
<td><p>Numero corrente di endpoint registrati in UCWA per applicazione e totale</p></td>
</tr>
<tr class="even">
<td><p>Conteggio delle istanze dell'utente attivo</p></td>
<td><p>Numero corrente di istanze utente</p></td>
</tr>
<tr class="odd">
<td><p>Istanze utente attive senza applicazione</p></td>
<td><p>Numero corrente di istanze utente senza applicazione</p></td>
</tr>
<tr class="even">
<td><p>Conteggio delle modalità video attivo</p></td>
<td><p>Il numero corrente di modalità video</p></td>
</tr>
<tr class="odd">
<td><p>Richieste di creazione di applicazioni ricevute al secondo</p></td>
<td><p>La percentuale di richieste di creazione di applicazioni ricevute al secondo</p></td>
</tr>
<tr class="even">
<td><p>Gli errori di join di MCU</p></td>
<td><p>Numero di errori di join di MCU</p></td>
</tr>
<tr class="odd">
<td><p>Errore di join di MCU AV</p></td>
<td><p>Numero di errori di join di MCU AV</p></td>
</tr>
<tr class="even">
<td><p>Tempo medio di avvio dell'applicazione (MS)</p></td>
<td><p>Tempo di avvio medio dell'applicazione in millisecondi</p></td>
</tr>
<tr class="odd">
<td><p>Durata media della sessione (MS)</p></td>
<td><p>Durata media di una sessione in millisecondi</p></td>
</tr>
<tr class="even">
<td><p>Errori di join dei dati MCU</p></td>
<td><p>Numero di errori di join di MCU di dati</p></td>
</tr>
<tr class="odd">
<td><p>Latenza ricerca contatti di Exchange (MS)</p></td>
<td><p>Questo contatore indica il tempo medio (in millisecondi) per il contatto di ricerca in Exchange</p></td>
</tr>
<tr class="even">
<td><p>Exchange HD Photo Get latenza (MS)</p></td>
<td><p>Questo contatore indica il tempo medio (in millisecondi) per il recupero di una foto da Exchange</p></td>
</tr>
<tr class="odd">
<td><p>Risposte 4xx HTTP/secondo</p></td>
<td><p>La percentuale di risposte al secondo con il codice 4xx HTTP</p></td>
</tr>
<tr class="even">
<td><p>Risposte 5xx HTTP/secondo</p></td>
<td><p>La percentuale di risposte al secondo con il codice 5xx HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Errori di join di MCU IM</p></td>
<td><p>Il numero di errori di join di MCU di messaggistica istantanea</p></td>
</tr>
<tr class="even">
<td><p>Numero di errori della foto di Active Directory</p></td>
<td><p>Il numero totale di errori per il recupero delle foto da Active Directory</p></td>
</tr>
<tr class="odd">
<td><p>Numero di errori di ricerca dei contatti</p></td>
<td><p>Il numero totale di errori per la ricerca dei contatti in Exchange</p></td>
</tr>
<tr class="even">
<td><p>Numero di errori di deserializzazione</p></td>
<td><p>Il numero totale di errori di deserializzazione</p></td>
</tr>
<tr class="odd">
<td><p>Numero di errori di ricezione foto HD</p></td>
<td><p>Il numero totale di errori per il recupero delle foto HD da Exchange</p></td>
</tr>
<tr class="even">
<td><p>Oltre il numero massimo di abbonamenti per applicazione</p></td>
<td><p>Il numero di richieste di sottoscrizione sul massimo consentito per applicazione</p></td>
</tr>
<tr class="odd">
<td><p>Oltre il numero massimo di sottoscrizioni per batch</p></td>
<td><p>Il numero di richieste di sottoscrizione sul massimo consentito per ogni batch</p></td>
</tr>
<tr class="even">
<td><p>Errori di sottoscrizione alla presenza</p></td>
<td><p>Il numero di errori da sottoscrivere la presenza</p></td>
</tr>
<tr class="odd">
<td><p>Registrazione degli errori degli endpoint</p></td>
<td><p>Il numero di errori di registrazione degli endpoint</p></td>
</tr>
<tr class="even">
<td><p>Richieste ricevute/secondo</p></td>
<td><p>La percentuale di richieste ricevute al secondo</p></td>
</tr>
<tr class="odd">
<td><p>Richieste con esito positivo/secondo</p></td>
<td><p>Il tasso al secondo delle richieste riuscite (HTTP 2xx/3xx Response codes)</p></td>
</tr>
<tr class="even">
<td><p>Esito positivo della creazione delle richieste di applicazione/secondo</p></td>
<td><p>La velocità al secondo delle richieste di creazione di applicazioni riuscite</p></td>
</tr>
<tr class="odd">
<td><p>Conteggio scaduto in sospeso</p></td>
<td><p>Il numero di in sospeso viene superato</p></td>
</tr>
<tr class="even">
<td><p>Totale richieste di creazione di applicazioni ricevute</p></td>
<td><p>Il numero totale di richieste di creazione di applicazioni ricevute dopo l'avvio del servizio</p></td>
</tr>
<tr class="odd">
<td><p>Totale risposte 4xx HTTP</p></td>
<td><p>Il numero totale di risposte 4xx HTTP</p></td>
</tr>
<tr class="even">
<td><p>Totale risposte 5xx HTTP</p></td>
<td><p>Il numero totale di risposte 5xx HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Totale richieste ricevute nel canale di comando</p></td>
<td><p>Il numero totale di richieste ricevute nel canale di comando</p></td>
</tr>
<tr class="even">
<td><p>Totale richieste riuscite</p></td>
<td><p>Il numero totale di richieste che hanno avuto esito positivo</p></td>
</tr>
<tr class="odd">
<td><p>Totale sessioni avviate</p></td>
<td><p>Il numero totale di sessioni avviate dopo l'avvio del servizio</p></td>
</tr>
<tr class="even">
<td><p>Totale sessioni interrotte a causa del timeout di inattività</p></td>
<td><p>Il numero totale di sessioni terminate a causa del timeout di inattività dell'utente</p></td>
</tr>
<tr class="odd">
<td><p>Totale applicazioni limitate</p></td>
<td><p>Il numero di applicazioni limitate</p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a>Contatori delle prestazioni per il servizio per dispositivi mobili MCX

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
<td><p>Durata media di una sessione in millisecondi</p></td>
<td><p>Durata media di una sessione in millisecondi</p></td>
</tr>
<tr class="even">
<td><p>Abbonamenti alle notifiche push correnti</p></td>
<td><p>Numero corrente di sottoscrizioni di notifica push. Questo numero, insieme al conteggio sessioni attivo, rappresenta il sottoinsieme delle sessioni attualmente attive registrate per i dispositivi Windows Mobile o iPhone.</p></td>
</tr>
<tr class="odd">
<td><p>Conteggio del sondaggio del timeout di rete corrente attivo</p></td>
<td><p>Il numero di polli di rete scaduti</p></td>
</tr>
<tr class="even">
<td><p>Conteggio di poll corrente attivo</p></td>
<td><p>Il numero di poll attualmente attivi (connessioni di lunga durata al server)</p></td>
</tr>
<tr class="odd">
<td><p>Numero di sessione corrente attivo</p></td>
<td><p>Numero corrente di endpoint registrati nel servizio per dispositivi mobili</p></td>
</tr>
<tr class="even">
<td><p>Conteggio delle sessioni attivo con gli abbonamenti a presenza attiva</p></td>
<td><p>Il numero di sessioni attive con sottoscrizioni di presenza attiva</p></td>
</tr>
<tr class="odd">
<td><p>Richieste di notifica push non riuscite al secondo</p></td>
<td><p>La percentuale di notifiche di push non riuscite al secondo</p></td>
</tr>
<tr class="even">
<td><p>Richieste di notifica push con esito positivo/secondo</p></td>
<td><p>La velocità al secondo delle notifiche push con esito positivo</p></td>
</tr>
<tr class="odd">
<td><p>Richieste di notifica push limitate al secondo</p></td>
<td><p>La velocità al secondo delle notifiche push limitate</p></td>
</tr>
<tr class="even">
<td><p>Richieste di notifica push/secondo</p></td>
<td><p>La velocità al secondo delle notifiche push inviate</p></td>
</tr>
<tr class="odd">
<td><p>Richieste non riuscite al secondo</p></td>
<td><p>La percentuale di richieste non riuscite al secondo</p></td>
</tr>
<tr class="even">
<td><p>Richieste ricevute/secondo</p></td>
<td><p>La percentuale di richieste ricevute al secondo</p></td>
</tr>
<tr class="odd">
<td><p>Richieste rifiutate/secondo</p></td>
<td><p>La percentuale di richieste rifiutate al secondo</p></td>
</tr>
<tr class="even">
<td><p>Richieste con esito positivo/secondo</p></td>
<td><p>Il tasso al secondo delle richieste riuscite</p></td>
</tr>
<tr class="odd">
<td><p>Esito positivo delle sessioni di avvio/secondo</p></td>
<td><p>La velocità al secondo delle richieste di posizione di ottenere riuscite. Le richieste di avvio di una sessione utilizzano la maggior parte della CPU sul server. Il carico supportato di picco è 12/sec. La sostenibilità dipende da altri carichi sul server. L'avvio di una sessione in genere indica un accesso per un utente che è stato disconnesso per un periodo di tempo prolungato.</p></td>
</tr>
<tr class="even">
<td><p>Totale chiamate vocali in ingresso rifiutate</p></td>
<td><p>Il numero totale di chiamate vocali in ingresso rifiutate</p></td>
</tr>
<tr class="odd">
<td><p>Totale chiamate vocali in ingresso non riuscite</p></td>
<td><p>Numero totale di chiamate vocali in ingresso non riuscite</p></td>
</tr>
<tr class="even">
<td><p>Totale chiamate vocali in uscita non riuscite</p></td>
<td><p>Il numero totale di chiamate vocali in uscita non riuscite</p></td>
</tr>
<tr class="odd">
<td><p>Numero totale di sessioni terminate dall'utente</p></td>
<td><p>Il numero totale di sessioni terminate dagli utenti</p></td>
</tr>
<tr class="even">
<td><p>Totale richieste di notifica push</p></td>
<td><p>Il numero totale di richieste di notifica push</p></td>
</tr>
<tr class="odd">
<td><p>Totale richieste di notifica push non riuscite</p></td>
<td><p>Il numero totale di richieste di notifica push non riuscite</p></td>
</tr>
<tr class="even">
<td><p>Totale richieste di notifica push con esito positivo</p></td>
<td><p>Il numero totale di richieste di notifica push che hanno avuto esito positivo</p></td>
</tr>
<tr class="odd">
<td><p>Totale richieste di notifica push limitate</p></td>
<td><p>Il numero totale di richieste di notifica push che sono state limitate</p></td>
</tr>
<tr class="even">
<td><p>Totale richieste non riuscite</p></td>
<td><p>Il numero totale di richieste non riuscite</p></td>
</tr>
<tr class="odd">
<td><p>Totale richieste ricevute nel canale di comando</p></td>
<td><p>Il numero totale di richieste ricevute nel canale di comando</p></td>
</tr>
<tr class="even">
<td><p>Totale richieste respinte</p></td>
<td><p>Il numero totale di richieste che sono state respinte</p></td>
</tr>
<tr class="odd">
<td><p>Totale richieste riuscite</p></td>
<td><p>Il numero totale di richieste apportate al servizio per dispositivi mobili che hanno avuto esito positivo</p></td>
</tr>
<tr class="even">
<td><p>Numero totale di sessioni avviate</p></td>
<td><p>Il numero totale di sessioni avviate dopo l'avvio del servizio per dispositivi mobili</p></td>
</tr>
<tr class="odd">
<td><p>Totale sessioni interrotte a causa del timeout di inattività dell'utente</p></td>
<td><p>Il numero totale di sessioni terminate a causa del timeout di inattività dell'utente</p></td>
</tr>
<tr class="even">
<td><p>Totale successo delle chiamate vocali in ingresso</p></td>
<td><p>Il numero totale di chiamate vocali in ingresso che hanno avuto esito positivo</p></td>
</tr>
<tr class="odd">
<td><p>Numero totale di chiamate vocali in uscita</p></td>
<td><p>Il numero totale di chiamate vocali in uscita che hanno avuto esito positivo</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

