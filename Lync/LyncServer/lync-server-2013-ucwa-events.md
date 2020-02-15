---
title: 'Lync Server 2013: Eventi UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d42dbd967f90b6e2a905b92558c88fe52ef62d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a>Eventi UCWA in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-15_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 utilizza Unified Communications Web API (UCWA) per una serie di scopi, dall'accesso a Microsoft Exchange per le ricerche dei contatti per l'aggiornamento della presenza per i client mobili.

UCWA scriverà i record del comportamento operativo come tipi di evento informativi, di avviso e di errore. Nella tabella seguente vengono descritti gli eventi che possono essere scritti dai componenti di UCWA.


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
<th>Tipo evento</th>
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
<p>Esaminare i dettagli dell'eccezione nella voce del registro eventi associata per determinare la causa possibile</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>Errore</p></td>
<td><p>UCWA ha rilevato un'eccezione non gestita</p></td>
<td><p>Si è verificata un'eccezione non gestita</p>
<p>Riavviare il server. Se il problema persiste, contattare il supporto del prodotto</p></td>
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
<td><p>Recuperato dalla mancata accesso a Exchange per la foto HD</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>Errore</p></td>
<td><p>Non è possibile accedere a Exchange per la ricerca dei contatti</p></td>
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
<td><p>Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per applicazione</p></td>
<td><p>Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per applicazione</p>
<p>Controllare i client per le sottoscrizioni non necessarie</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>Avviso</p></td>
<td><p>Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per batch</p></td>
<td><p>Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per batch</p>
<p>Controllare i client per le sottoscrizioni non necessarie</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>Errore</p></td>
<td><p>Non è in grado di recuperare i dati inband</p></td>
<td><p>Non è in grado di recuperare i dati inband</p>
<p>Se il problema persiste, contattare il supporto del prodotto</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>Errore</p></td>
<td><p>Non è possibile sottoscrivere la presenza</p></td>
<td><p>Non è possibile sottoscrivere la presenza</p>
<p>Se il problema persiste, contattare il supporto del prodotto</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>Errore</p></td>
<td><p>Impossibile registrare l'endpoint</p></td>
<td><p>Impossibile registrare l'endpoint</p>
<p>Se il problema persiste, contattare il supporto del prodotto</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>Errore</p></td>
<td><p>La MCU di messaggistica istantanea non è disponibile</p></td>
<td><p>La MCU di messaggistica istantanea non è disponibile</p>
<p>Vedere se è in esecuzione MCU di messaggistica istantanea</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>Informativo</p></td>
<td><p>Recuperato dalla mancata connessione a MCU IM</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>Errore</p></td>
<td><p>MCU AV non disponibile</p></td>
<td><p>MCU AV non disponibile</p>
<p>Vedere se è in esecuzione MCU AV</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>Informativo</p></td>
<td><p>Recuperato dalla mancata connessione a MCU AV</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>Errore</p></td>
<td><p>Poiché MCU non è disponibile</p></td>
<td><p>Poiché MCU non è disponibile</p>
<p>Vedere se è in esecuzione MCU</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>Informativo</p></td>
<td><p>Recuperato dalla mancata connessione a come MCU</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>Errore</p></td>
<td><p>MCU dei dati non disponibile</p></td>
<td><p>MCU dei dati non disponibile</p>
<p>Controllare se è in esecuzione MCU dati</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>Informativo</p></td>
<td><p>Ripristino dalla mancata connessione a MCU dei dati</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>Errore</p></td>
<td><p>Non è possibile aggiungere MCU IM</p></td>
<td><p>Non è possibile aggiungere MCU IM</p>
<p>Vedere se è in esecuzione MCU di messaggistica istantanea</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>Errore</p></td>
<td><p>Non è possibile aggiungere MCU AV</p></td>
<td><p>Non è possibile aggiungere MCU AV</p>
<p>Vedere se è in esecuzione MCU AV</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>Errore</p></td>
<td><p>Non è possibile partecipare come MCU</p></td>
<td><p>Non è possibile partecipare come MCU</p>
<p>Vedere se è in esecuzione MCU</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>Errore</p></td>
<td><p>Non è possibile aggiungere MCU dati</p></td>
<td><p>Non è possibile aggiungere MCU dati</p>
<p>Controllare se è in esecuzione MCU dati</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>Errore</p></td>
<td><p>Non è possibile accedere ad Active Directory per la foto</p></td>
<td><p>La connessione a Active Directory non è disponibile</p>
<p>Verificare che la connessione ad Active Directory sia disponibile</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>Informativo</p></td>
<td><p>Recuperato dalla mancata accesso ad Active Directory per la foto</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>Avviso</p></td>
<td><p>Non può deserializzare</p></td>
<td><p>Non può deserializzare</p>
<p>Se il problema persiste, contattare il supporto del prodotto</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

