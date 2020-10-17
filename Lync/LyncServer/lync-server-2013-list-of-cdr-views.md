---
title: 'Lync Server 2013: elenco delle visualizzazioni CDR'
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
ms.openlocfilehash: 37f41be7781f3cdce6b458b1eeaeb5cb8431b8d0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513963"
---
# <a name="list-of-cdr-views-in-lync-server-2013"></a><span data-ttu-id="95b7d-102">Elenco delle visualizzazioni CDR in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95b7d-102">List of CDR views in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95b7d-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="95b7d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="95b7d-104">Le visualizzazioni consentono di accedere facilmente alle informazioni sugli scenari più comuni usati per restituire dati dal database CDR.</span><span class="sxs-lookup"><span data-stu-id="95b7d-104">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="95b7d-105">È consigliabile utilizzare le visualizzazioni per la creazione di report personalizzati anziché utilizzare le tabelle di database CDR effettive. Ciò è dovuto al fatto che le visualizzazioni di database hanno maggiori probabilità di mantenere la compatibilità con le versioni precedenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="95b7d-105">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that’s because the database views are more likely to maintain backwards compatibility with future releases of Lync Server.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95b7d-106">Nome visualizzazione</span><span class="sxs-lookup"><span data-stu-id="95b7d-106">View Name</span></span></th>
<th><span data-ttu-id="95b7d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95b7d-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95b7d-108"><a href="lync-server-2013-clientversions-view.md">Visualizzazione ClientVersions in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="95b7d-108"><a href="lync-server-2013-clientversions-view.md">ClientVersions view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95b7d-109">Restituisce informazioni sul software/dispositivi client usati in una sessione di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="95b7d-109">Returns information about the client software/devices used in a communication session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95b7d-110"><a href="lync-server-2013-conferencemessagecount-view.md">Visualizzazione ConferenceMessageCount in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="95b7d-110"><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95b7d-111">Restituisce informazioni sul numero di messaggi inviati dagli utenti durante una conferenza.</span><span class="sxs-lookup"><span data-stu-id="95b7d-111">Returns information about the number of messages sent by users in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95b7d-112"><a href="lync-server-2013-conferences-view.md">Visualizzazione conferenze in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="95b7d-112"><a href="lync-server-2013-conferences-view.md">Conferences view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95b7d-113">Restituisce informazioni sulla conferenza, inclusa l'ora di inizio e di fine, e sull'organizzatore della conferenza.</span><span class="sxs-lookup"><span data-stu-id="95b7d-113">Returns conference information, including start time, end time, and conference organizer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95b7d-114"><a href="lync-server-2013-conferencesessiondetails-view.md">Visualizzazione ConferenceSessionDetails in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="95b7d-114"><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95b7d-115">Restituisce dettagli su tutte le sessioni di conferenza, tra cui ora di inizio e di fine, ID utente, codici di risposta e ID diagnostica.</span><span class="sxs-lookup"><span data-stu-id="95b7d-115">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95b7d-116"><a href="lync-server-2013-conferenceuris-view.md">Visualizzazione ConferenceUris in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="95b7d-116"><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95b7d-117">Restituisce informazioni sugli URI di conferenza usati in una conferenza</span><span class="sxs-lookup"><span data-stu-id="95b7d-117">Returns information about conference URIs used in a conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95b7d-118"><a href="lync-server-2013-errorreport-view.md">Visualizzazione ErrorReport in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="95b7d-118"><a href="lync-server-2013-errorreport-view.md">ErrorReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95b7d-119">Restituisce informazioni sugli errori che si sono verificati durante una sessione.</span><span class="sxs-lookup"><span data-stu-id="95b7d-119">Returns information about errors that occurred during a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95b7d-120"><a href="lync-server-2013-filetransfers-view.md">Visualizzazione FileTransfers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="95b7d-120"><a href="lync-server-2013-filetransfers-view.md">FileTransfers view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95b7d-121">Restituisce informazioni sulle sessioni di trasferimento file, incluso il nome file, e indica se il trasferimento è stato accettato, rifiutato o annullato.</span><span class="sxs-lookup"><span data-stu-id="95b7d-121">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95b7d-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">Visualizzazione FocusJoinsAndLeaves in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="95b7d-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95b7d-123">Restituisce informazioni sulle attività di partecipazione alla conferenza e di abbandono della stessa.</span><span class="sxs-lookup"><span data-stu-id="95b7d-123">Returns information about conference join and leave activities.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95b7d-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">Visualizzazione McuJoinsAndLeaves in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="95b7d-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95b7d-125">Restituisce informazioni combinate sulle attività di partecipazione alla conferenza e di abbandono della stessa (ogni partecipazione a una conferenza è accoppiata al corrispondente abbandono della conferenza).</span><span class="sxs-lookup"><span data-stu-id="95b7d-125">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95b7d-126"><a href="lync-server-2013-mcus-view.md">Visualizzazione MCU in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="95b7d-126"><a href="lync-server-2013-mcus-view.md">Mcus view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95b7d-127">Restituisce informazioni sui server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="95b7d-127">Returns information about Conferencing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95b7d-128"><a href="lync-server-2013-media-view.md">Visualizzazione multimediale in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="95b7d-128"><a href="lync-server-2013-media-view.md">Media view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95b7d-129">Restituisce informazioni sui tipi di supporti usati nelle sessioni di comunicazione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="95b7d-129">Returns information about the types of media used in peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95b7d-130"><a href="lync-server-2013-progressreport-view.md">Visualizzazione ProgressReport in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="95b7d-130"><a href="lync-server-2013-progressreport-view.md">ProgressReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95b7d-131">Restituisce informazioni sulle sessioni completate.</span><span class="sxs-lookup"><span data-stu-id="95b7d-131">Returns information about completed sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95b7d-132"><a href="lync-server-2013-registration-view.md">Visualizzazione registrazione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="95b7d-132"><a href="lync-server-2013-registration-view.md">Registration view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95b7d-133">Restituisce informazioni sulle registrazioni con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="95b7d-133">Returns information about registrations with Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95b7d-134"><a href="lync-server-2013-sessiondetails-view.md">Visualizzazione SessionDetails in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="95b7d-134"><a href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95b7d-135">Restituisce informazioni sulle sessioni peer-to-peer, incluse le chiamate telefoniche VoIP-VoIP, le sessioni di messaggistica istantanea a due parti o altre sessioni di comunicazione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="95b7d-135">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95b7d-136"><a href="lync-server-2013-user-view.md">Visualizzazione utente in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="95b7d-136"><a href="lync-server-2013-user-view.md">User view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95b7d-137">Restituisce informazioni sugli utenti che hanno partecipato alle sessioni di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="95b7d-137">Returns information about the users who have participated in communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95b7d-138"><a href="lync-server-2013-voipdetails-view.md">Visualizzazione VoIPDetails in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="95b7d-138"><a href="lync-server-2013-voipdetails-view.md">VoIPDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95b7d-139">Restituisce informazioni per le sessioni peer-to-peer che coinvolgono almeno un utente VoIP (Voice over IP).</span><span class="sxs-lookup"><span data-stu-id="95b7d-139">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

