---
title: 'Lync Server 2013: Eventi UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0671b51e5fbd4b5f072676855d9e8f5201b3e04
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a>Eventi UCWA in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-15_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 usa la Unified Communications Web API (UCWA) per diversi scopi, dall'accesso a Microsoft Exchange per la ricerca di contatti all'aggiornamento della presenza per i client mobili.

UCWA scriverà i record del comportamento operativo come tipi di evento informativo, di avviso e di errore. La tabella seguente descrive gli eventi che possono essere scritti dai componenti UCWA.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Tipo di evento</th>
<th>Riepilogo</th>
<th>Causa e risoluzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>Informativo</p></td>
<td><p>UCWA inizializzato</p></td>
<td><p>N/D</p>
<p>N/D</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>Errore</p></td>
<td><p>UCWA ha rilevato un'eccezione imprevista durante l'inizializzazione</p></td>
<td><p>Si è verificato un errore imprevisto durante l'inizializzazione</p>
<p>Esaminare i dettagli dell'eccezione nella voce del log eventi associata per determinare la causa possibile</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>Errore</p></td>
<td><p>UCWA ha rilevato un'eccezione non gestita</p></td>
<td><p>È stata generata un'eccezione non gestita</p>
<p>Riavviare il server. Se il problema persiste, contattare il supporto tecnico</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>Errore</p></td>
<td><p>Non è possibile accedere a Exchange per la foto HD</p></td>
<td><p>La connessione a Exchange non è disponibile</p>
<p>Verificare che la connessione a Exchange sia disponibile</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>Informativo</p></td>
<td><p>Recupero della mancata accesso a Exchange per la foto HD</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>Errore</p></td>
<td><p>Non è possibile accedere a Exchange per la ricerca di contatti</p></td>
<td><p>La connessione a Exchange non è disponibile</p>
<p>Verificare che la connessione a Exchange sia disponibile</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>Informativo</p></td>
<td><p>Recuperato dalla mancata ricerca del contatto in Exchange</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>Avviso</p></td>
<td><p>Tentativo di sottoscrizione di un numero maggiore di abbonamenti a presenza consentiti per applicazione</p></td>
<td><p>Tentativo di sottoscrizione di un numero maggiore di abbonamenti a presenza consentiti per applicazione</p>
<p>Controllare i client per gli abbonamenti non necessari</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>Avviso</p></td>
<td><p>Tentativo di sottoscrizione di un numero maggiore di abbonamenti di presenza consentiti per batch</p></td>
<td><p>Tentativo di sottoscrizione di un numero maggiore di abbonamenti di presenza consentiti per batch</p>
<p>Controllare i client per gli abbonamenti non necessari</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>Errore</p></td>
<td><p>Non è possibile recuperare i dati in banda</p></td>
<td><p>Non è possibile recuperare i dati in banda</p>
<p>Se il problema persiste, contattare il supporto tecnico</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>Errore</p></td>
<td><p>Non è possibile sottoscrivere la presenza</p></td>
<td><p>Non è possibile sottoscrivere la presenza</p>
<p>Se il problema persiste, contattare il supporto tecnico</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>Errore</p></td>
<td><p>Impossibile registrare l'endpoint</p></td>
<td><p>Impossibile registrare l'endpoint</p>
<p>Se il problema persiste, contattare il supporto tecnico</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>Errore</p></td>
<td><p>La MCU di messaggistica istantanea non è disponibile</p></td>
<td><p>La MCU di messaggistica istantanea non è disponibile</p>
<p>Verificare se è in corso una MCU di messaggistica istantanea</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>Informativo</p></td>
<td><p>Ripristino della mancata connessione alla MCU istantanea</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>Errore</p></td>
<td><p>MCU AV non disponibile</p></td>
<td><p>MCU AV non disponibile</p>
<p>Verificare se è in corso una MCU AV</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>Informativo</p></td>
<td><p>Recuperato dalla mancata connessione alla MCU AV</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>Errore</p></td>
<td><p>Poiché MCU non è disponibile</p></td>
<td><p>Poiché MCU non è disponibile</p>
<p>Verificare l'eventuale funzionamento di MCU</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>Informativo</p></td>
<td><p>Recuperata dalla mancata connessione a come MCU</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>Errore</p></td>
<td><p>MCU dati non disponibile</p></td>
<td><p>MCU dati non disponibile</p>
<p>Verificare se è in corso l'uso di MCU dati</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>Informativo</p></td>
<td><p>Recupero dalla mancata connessione a MCU dati</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>Errore</p></td>
<td><p>Non è possibile partecipare a una MCU istantanea</p></td>
<td><p>Non è possibile partecipare a una MCU istantanea</p>
<p>Verificare se è in corso una MCU di messaggistica istantanea</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>Errore</p></td>
<td><p>Non è possibile partecipare a MCU AV</p></td>
<td><p>Non è possibile partecipare a MCU AV</p>
<p>Verificare se è in corso una MCU AV</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>Errore</p></td>
<td><p>Non è possibile partecipare come MCU</p></td>
<td><p>Non è possibile partecipare come MCU</p>
<p>Verificare l'eventuale funzionamento di MCU</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>Errore</p></td>
<td><p>Non è possibile partecipare a MCU dati</p></td>
<td><p>Non è possibile partecipare a MCU dati</p>
<p>Verificare se è in corso l'uso di MCU dati</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>Errore</p></td>
<td><p>Non è possibile accedere a Active Directory per la foto</p></td>
<td><p>La connessione a Active Directory non è disponibile</p>
<p>Verificare che la connessione a Active Directory sia disponibile</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>Informativo</p></td>
<td><p>Recuperati dal mancato accesso a Active Directory per la foto</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>Avviso</p></td>
<td><p>Non è possibile deserializzare</p></td>
<td><p>Non è possibile deserializzare</p>
<p>Se il problema persiste, contattare il supporto tecnico</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

