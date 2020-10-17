---
title: 'Lync Server 2013: elenco delle visualizzazioni CDR'
description: 'Lync Server 2013: elenco delle visualizzazioni CDR.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f1c29560851c0e4466dbf4316bf0b1335906d4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550082"
---
# <a name="list-of-cdr-views-in-lync-server-2013"></a>Elenco delle visualizzazioni CDR in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Le visualizzazioni consentono di accedere facilmente alle informazioni sugli scenari più comuni usati per restituire dati dal database CDR. È consigliabile utilizzare le visualizzazioni per la creazione di report personalizzati anziché utilizzare le tabelle di database CDR effettive. Ciò è dovuto al fatto che le visualizzazioni di database hanno maggiori probabilità di mantenere la compatibilità con le versioni precedenti di Lync Server.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome visualizzazione</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-view.md">Visualizzazione ClientVersions in Lync Server 2013</a></p></td>
<td><p>Restituisce informazioni sul software/dispositivi client usati in una sessione di comunicazione.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencemessagecount-view.md">Visualizzazione ConferenceMessageCount in Lync Server 2013</a></p></td>
<td><p>Restituisce informazioni sul numero di messaggi inviati dagli utenti durante una conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-view.md">Visualizzazione conferenze in Lync Server 2013</a></p></td>
<td><p>Restituisce informazioni sulla conferenza, inclusa l'ora di inizio e di fine, e sull'organizzatore della conferenza.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-view.md">Visualizzazione ConferenceSessionDetails in Lync Server 2013</a></p></td>
<td><p>Restituisce dettagli su tutte le sessioni di conferenza, tra cui ora di inizio e di fine, ID utente, codici di risposta e ID diagnostica.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferenceuris-view.md">Visualizzazione ConferenceUris in Lync Server 2013</a></p></td>
<td><p>Restituisce informazioni sugli URI di conferenza usati in una conferenza</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errorreport-view.md">Visualizzazione ErrorReport in Lync Server 2013</a></p></td>
<td><p>Restituisce informazioni sugli errori che si sono verificati durante una sessione.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-filetransfers-view.md">Visualizzazione FileTransfers in Lync Server 2013</a></p></td>
<td><p>Restituisce informazioni sulle sessioni di trasferimento file, incluso il nome file, e indica se il trasferimento è stato accettato, rifiutato o annullato.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-focusjoinsandleaves-view.md">Visualizzazione FocusJoinsAndLeaves in Lync Server 2013</a></p></td>
<td><p>Restituisce informazioni sulle attività di partecipazione alla conferenza e di abbandono della stessa.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mcujoinsandleaves-view.md">Visualizzazione McuJoinsAndLeaves in Lync Server 2013</a></p></td>
<td><p>Restituisce informazioni combinate sulle attività di partecipazione alla conferenza e di abbandono della stessa (ogni partecipazione a una conferenza è accoppiata al corrispondente abbandono della conferenza).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-view.md">Visualizzazione MCU in Lync Server 2013</a></p></td>
<td><p>Restituisce informazioni sui server per conferenze.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-view.md">Visualizzazione multimediale in Lync Server 2013</a></p></td>
<td><p>Restituisce informazioni sui tipi di supporti usati nelle sessioni di comunicazione peer-to-peer.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-view.md">Visualizzazione ProgressReport in Lync Server 2013</a></p></td>
<td><p>Restituisce informazioni sulle sessioni completate.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-registration-view.md">Visualizzazione registrazione in Lync Server 2013</a></p></td>
<td><p>Restituisce informazioni sulle registrazioni con Lync Server.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessiondetails-view.md">Visualizzazione SessionDetails in Lync Server 2013</a></p></td>
<td><p>Restituisce informazioni sulle sessioni peer-to-peer, incluse le chiamate telefoniche VoIP-VoIP, le sessioni di messaggistica istantanea a due parti o altre sessioni di comunicazione peer-to-peer.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-user-view.md">Visualizzazione utente in Lync Server 2013</a></p></td>
<td><p>Restituisce informazioni sugli utenti che hanno partecipato alle sessioni di comunicazione.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-voipdetails-view.md">Visualizzazione VoIPDetails in Lync Server 2013</a></p></td>
<td><p>Restituisce informazioni per le sessioni peer-to-peer che coinvolgono almeno un utente VoIP (Voice over IP).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

