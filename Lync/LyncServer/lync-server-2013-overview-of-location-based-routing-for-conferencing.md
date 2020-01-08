---
title: 'Lync Server 2013: Panoramica del routing basato sulla posizione per i servizi di conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895a89ee59edaf973ae5194658c4cdf12564542e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Panoramica del routing basato sulla posizione per i servizi di conferenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-19_

L'applicazione per i servizi di conferenza di routing basato sulla posizione offre alle conferenze di Lync un meccanismo per la prevenzione del bypass a pedaggio PSTN. L'applicazione monitora le conferenze attive e applica le restrizioni di routing basate sulla posizione in base alla posizione degli utenti di Lync partecipanti.

L'applicazione per i servizi di conferenza di routing basata sulla posizione determina se il routing basato sulla posizione deve essere applicato a una riunione Lync se vengono soddisfatti i criteri seguenti:

  - L'organizzatore della riunione è abilitato per il routing basato sulla posizione. Le restrizioni di routing basate sul percorso verranno applicate solo alle conferenze organizzate dagli utenti abilitati per il routing basato sulla posizione.

  - Almeno un partecipante alla riunione è un endpoint PSTN. Le restrizioni di routing basate sulla posizione sono applicabili solo per le conferenze che includono endpoint PSTN.

  - Sito di rete in cui si trova il gateway PSTN usato per il Bridge della conferenza alla rete PSTN, nonché i siti di Network in cui gli organizzatori e i partecipanti sono connessi.

L'applicazione di conferenza di routing basata sulla posizione impedisce la partecipazione degli utenti di Lync e degli endpoint PSTN da siti di rete diversi alla stessa conferenza. Se l'organizzatore di una riunione è abilitato per il routing basato sulla posizione, l'applicazione di conferenza applica le restrizioni seguenti:

  - Gli endpoint che possono partecipare a una riunione Lync dipendono dagli endpoint che hanno già partecipato alla conferenza e questa restrizione viene regolata quando gli endpoint Uniti vengono abbandonati e i nuovi endpoint partecipano alla conferenza. Se gli organizzatori e i partecipanti partecipano a una riunione Lync dallo stesso sito di rete, viene consentito un endpoint PSTN, un altro partecipante dello stesso sito di rete, un altro partecipante da un sito di rete diverso o da un partecipante di un sito di rete sconosciuto partecipare a.

  - Se gli organizzatori e i partecipanti partecipano alla riunione da siti di rete diversi o sconosciuti, non è consentito l'accesso alla riunione da parte di un endpoint PSTN se la chiamata PSTN entra da un trunk SIP abilitato per il routing basato sulla posizione.

  - Se gli organizzatori e i partecipanti partecipano alla riunione dallo stesso sito di rete e i partecipanti partecipano alla stessa riunione da PSTN, non è consentito partecipare alla riunione a un endpoint di Lync proveniente da un sito di rete diverso.

Queste restrizioni di routing basate sulla posizione dei servizi di conferenza sono riepilogate nella tabella seguente.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Utenti in una conferenza in un dato punto</p></td>
<td><p>Utenti autorizzati a partecipare alla conferenza</p></td>
<td><p>Utenti non autorizzati a partecipare alla conferenza</p></td>
</tr>
<tr class="even">
<td><p>Utenti del client VoIP di Lync da un singolo sito di rete</p></td>
<td><p>Utente client VoIP di Lync dello stesso sito di rete</p>
<p>Utente client VoIP di Lync da un sito di rete diverso</p>
<p>Utente client VoIP di Lync da un sito di rete sconosciuto</p>
<p>Utenti client VoIP di Lync federati</p>
<p>Aggiunta di un utente da un endpoint PSTN</p></td>
<td><p>Nessuno</p></td>
</tr>
<tr class="odd">
<td><p>Utenti del client VoIP di Lync da un sito di rete sconosciuto</p></td>
<td><p>Utente client VoIP di Lync da qualsiasi sito</p>
<p>Utente client VoIP di Lync da un sito sconosciuto</p>
<p>Utenti client VoIP di Lync federati</p></td>
<td><p>L'aggiunta di un utente tramite un endpoint PSTN</p></td>
</tr>
<tr class="even">
<td><p>Utenti client VoIP di Lync provenienti da siti di rete diversi</p></td>
<td><p>Utente client VoIP di Lync da qualsiasi sito di rete</p>
<p>Utente client VoIP di Lync da un sito di rete sconosciuto</p>
<p>Utenti client VoIP di Lync federati</p></td>
<td><p>L'aggiunta di un utente tramite un endpoint PSTN</p></td>
</tr>
<tr class="odd">
<td><p>Utenti del client VoIP di Lync da un singolo sito di rete e utenti che partecipano da un endpoint PSTN</p></td>
<td><p>Utente client VoIP di Lync dello stesso sito di rete</p></td>
<td><p>Utente client VoIP di Lync da un sito di rete diverso</p>
<p>Utente client VoIP di Lync da un sito di rete sconosciuto</p>
<p>Utenti client VoIP di Lync federati</p></td>
</tr>
</tbody>
</table>


Di seguito sono riportate le caratteristiche aggiuntive dell'applicazione di conferenza di routing basata sulla posizione:

  - Quando un utente non è autorizzato a partecipare a una conferenza con restrizioni di routing basate sulla posizione, la chiamata degli utenti alla conferenza verrà rifiutata e il client Lync riferirà che la chiamata non è stata completata o è terminata.

  - Un endpoint PSTN che partecipa a una conferenza con le imposte di routing basate sul percorso non sarà limitato per partecipare alla conferenza indipendentemente dallo stato, se l'endpoint si unisce tramite un trunk non abilitato per il routing basato sulla posizione.

  - Un sistema PBX connesso a un server di mediazione su un trunk SIP che non esegue l'uscita dalle chiamate alla rete PSTN avrà le stesse imposte degli utenti di Lync nello stesso sito di rete in cui è definito il trunk SIP. Ad esempio, un endpoint PSTN sarà in grado di partecipare a una conferenza con un utente PBX e un utente di Lync se si trovano nello stesso sito di rete; in caso contrario, l'endpoint PSTN non sarà autorizzato a partecipare alla conferenza se l'utente PBX si trova in un sito di rete diverso da quello dell'utente di Lync.

</div>

<span> </span>

</div>

</div>

</div>

