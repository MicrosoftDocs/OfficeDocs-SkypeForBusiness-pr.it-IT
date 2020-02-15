---
title: 'Lync Server 2013: Panoramica del routing in base alla posizione per le conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28ca4ea233f783271c91490aa0550bc2344bdaad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Panoramica del routing in base alla posizione per le conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-19_

L'applicazione per le conferenze di routing basata sulla posizione fornisce a Lync conferences un meccanismo per la prevenzione del bypass a pedaggio PSTN. L'applicazione monitora le conferenze attive e applica restrizioni di routing in base alla posizione in base alla posizione degli utenti di Lync che partecipano.

L'applicazione per le conferenze di routing basata sulla posizione determina se il routing basato sulla posizione deve essere applicato a una riunione di Lync se vengono soddisfatti i seguenti criteri:

  - L'organizzatore della riunione è abilitato per il routing in base alla posizione. Le restrizioni di routing in base alla posizione verranno applicate solo alle conferenze organizzate dagli utenti abilitati per il routing basato sulla posizione.

  - Almeno un partecipante alla riunione è un endpoint PSTN. Le restrizioni di routing in base alla posizione sono applicabili solo per le conferenze che includono endpoint PSTN.

  - Il sito di rete in cui si trova il gateway PSTN utilizzato per colmare la conferenza PSTN e i siti di rete in cui si connettono gli organizzatori e i partecipanti.

L'applicazione per le conferenze di routing basata sulla posizione impedisce la partecipazione degli utenti di Lync e degli endpoint PSTN da siti di rete diversi alla stessa conferenza. Se l'organizzatore di una riunione è abilitato per il routing in base alla posizione, l'applicazione per le conferenze impone le restrizioni seguenti:

  - Gli endpoint che possono partecipare a una riunione di Lync dipendono dagli endpoint che hanno già partecipato alla conferenza e questa restrizione viene modificata in base all'uscita degli endpoint Uniti e ai nuovi endpoint che partecipano alla conferenza. Se gli organizzatori e i partecipanti partecipano a una riunione di Lync dallo stesso sito di rete, un endpoint PSTN, un altro partecipante proveniente dallo stesso sito di rete, un altro partecipante proveniente da un sito di rete diverso o da un partecipante di un sito di rete sconosciuto può Join.

  - Se gli organizzatori e i partecipanti accedono alla riunione da siti di rete diversi o sconosciuti, non è consentito che un endpoint PSTN partecipi alla riunione se la chiamata PSTN accede da un trunk SIP abilitato per il routing in base alla posizione.

  - Se gli organizzatori e i partecipanti sono tutti Uniti alla riunione dallo stesso sito di rete e vi sono partecipanti che partecipano alla stessa riunione dalla PSTN, un endpoint di Lync proveniente da un sito di rete diverso non è autorizzato a partecipare alla riunione.

Queste restrizioni di routing in base alla posizione per le conferenze sono riepilogate nella tabella seguente.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Utente/i in una conferenza in un determinato punto</p></td>
<td><p>Utenti autorizzati a partecipare alla conferenza</p></td>
<td><p>Utenti non autorizzati a partecipare alla conferenza</p></td>
</tr>
<tr class="even">
<td><p>Utenti di Lync VoIP client da un singolo sito di rete</p></td>
<td><p>Utente client di Lync VoIP dallo stesso sito di rete</p>
<p>Utente client di Lync VoIP da un sito di rete diverso</p>
<p>Utente client di Lync VoIP da un sito di rete sconosciuto</p>
<p>Utente federato di Lync VoIP client</p>
<p>Aggiunta di un utente da un endpoint PSTN</p></td>
<td><p>Nessuno</p></td>
</tr>
<tr class="odd">
<td><p>Utenti del client VoIP di Lync provenienti da un sito di rete sconosciuto</p></td>
<td><p>Utente client di Lync VoIP da qualsiasi sito</p>
<p>Utente client di Lync VoIP da un sito sconosciuto</p>
<p>Utente federato di Lync VoIP client</p></td>
<td><p>Aggiunta di un utente tramite un endpoint PSTN</p></td>
</tr>
<tr class="even">
<td><p>Utenti di Lync VoIP client provenienti da siti di rete diversi</p></td>
<td><p>Utente client di Lync VoIP da qualsiasi sito di rete</p>
<p>Utente client di Lync VoIP da un sito di rete sconosciuto</p>
<p>Utente federato di Lync VoIP client</p></td>
<td><p>Aggiunta di un utente tramite un endpoint PSTN</p></td>
</tr>
<tr class="odd">
<td><p>Utenti del client VoIP di Lync provenienti da un singolo sito di rete e utenti che si congiungono da un endpoint PSTN</p></td>
<td><p>Utente client di Lync VoIP dallo stesso sito di rete</p></td>
<td><p>Utente client di Lync VoIP da un sito di rete diverso</p>
<p>Utente client di Lync VoIP da un sito di rete sconosciuto</p>
<p>Utente federato di Lync VoIP client</p></td>
</tr>
</tbody>
</table>


Di seguito sono riportate altre caratteristiche dell'applicazione per le conferenze di routing in base alla posizione:

  - Quando a un utente non è consentito partecipare a una conferenza con restrizioni di routing basate sul percorso, la chiamata degli utenti alla conferenza verrà rifiutata e il client Lync riporterà che la chiamata non è stata completata o è terminata.

  - Un endpoint PSTN che partecipa a una conferenza con l'applicazione del routing in base alla posizione non sarà limitato a partecipare alla conferenza indipendentemente dallo stato, se l'endpoint si unisce tramite un trunk che non è abilitato per il routing basato sulla posizione.

  - Un sistema PBX connesso a un server di Mediation tramite un trunk SIP che non esegue le chiamate alla rete PSTN avrà le stesse imposte degli utenti di Lync presenti nello stesso sito di rete in cui è definito il trunk SIP. Ad esempio, un endpoint PSTN sarà in grado di partecipare a una conferenza con un utente PBX e un utente di Lync se si trovano nello stesso sito di rete. in caso contrario, l'endpoint PSTN non sarà autorizzato a partecipare alla conferenza se l'utente PBX si trova in un sito di rete diverso da quello dell'utente Lync.

</div>

<span> </span>

</div>

</div>

</div>

