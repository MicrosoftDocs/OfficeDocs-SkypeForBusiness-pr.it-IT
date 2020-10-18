---
title: 'Lync Server 2013: rapporto Dettagli conferenza'
description: 'Lync Server 2013: rapporto Dettagli conferenza.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07c50b545f4a9ee3308a840fc2aa5a15e617a5bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577632"
---
# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="0cb17-103">Rapporto Dettagli conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0cb17-103">Conference Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cb17-104">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="0cb17-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="0cb17-p101">Il Rapporto Dettagli conferenza offre informazioni dettagliate su tutti gli utenti che hanno partecipato a una conferenza. È ad esempio possibile conoscere la data e l'ora in cui un utente si è unito alla conferenza o in cui l'ha abbandonata e l'agente utente dell'endpoint utilizzato per connettere tale utente alla conferenza. È anche possibile visualizzare informazioni sul ruolo dell'utente in ciascuna conferenza (relatore o partecipante). E ancora più importante, è possibile sapere rapidamente quali utenti si sono uniti alla conferenza e l'hanno completata e quali non ci sono riusciti.</span><span class="sxs-lookup"><span data-stu-id="0cb17-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="0cb17-109">Accesso al Rapporto Dettagli conferenza</span><span class="sxs-lookup"><span data-stu-id="0cb17-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="0cb17-110">Il Rapporto Dettagli conferenza è accessibile dai rapporti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cb17-110">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="0cb17-111">Il [rapporto di controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (facendo clic sulla metrica Dettagli per una conferenza)</span><span class="sxs-lookup"><span data-stu-id="0cb17-111">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="0cb17-112">Il [rapporto Elenco errori in Lync Server 2013](lync-server-2013-failure-list-report.md) (facendo clic sulla metrica conferenza)</span><span class="sxs-lookup"><span data-stu-id="0cb17-112">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="0cb17-113">Il [rapporto attività utente in Lync Server 2013](lync-server-2013-user-activity-report.md) (facendo clic sulla metrica URI conferenza)</span><span class="sxs-lookup"><span data-stu-id="0cb17-113">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="0cb17-114">Dal rapporto Dettagli conferenza è possibile accedere al [rapporto di diagnostica in Lync Server 2013](lync-server-2013-diagnostic-report.md) facendo clic sulla metrica del rapporto di diagnostica (dettaglio).</span><span class="sxs-lookup"><span data-stu-id="0cb17-114">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0cb17-115">Filtri</span><span class="sxs-lookup"><span data-stu-id="0cb17-115">Filters</span></span>

<span data-ttu-id="0cb17-p102">Nessuno. Non è possibile applicare filtri al Rapporto Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="0cb17-p102">None. You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="0cb17-118">Metriche</span><span class="sxs-lookup"><span data-stu-id="0cb17-118">Metrics</span></span>

<span data-ttu-id="0cb17-119">La tabella seguente elenca le informazioni contenute nella sezione Informazioni conferenza del Rapporto Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="0cb17-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="0cb17-120">Metriche Informazioni conferenza</span><span class="sxs-lookup"><span data-stu-id="0cb17-120">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0cb17-121">Nome</span><span class="sxs-lookup"><span data-stu-id="0cb17-121">Name</span></span></th>
<th><span data-ttu-id="0cb17-122">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="0cb17-122">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0cb17-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0cb17-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0cb17-124"><strong>URI conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="0cb17-124"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-p103">URI assegnato alla conferenza, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0cb17-p103">URI assigned to the conference. For example:</span></span></p>
<p><span data-ttu-id="0cb17-127">SIP: kmyer@litwareinc. com; GRUU; opaque = app: conf: Focus: ID: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="0cb17-127">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb17-128"><strong>FQDN pool</strong></span><span class="sxs-lookup"><span data-stu-id="0cb17-128"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-129">Nome di dominio completo del pool di registrazione o del server perimetrale operativo in una sessione.</span><span class="sxs-lookup"><span data-stu-id="0cb17-129">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cb17-130"><strong>Ora di inizio</strong></span><span class="sxs-lookup"><span data-stu-id="0cb17-130"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-131">Data e ora di inizio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="0cb17-131">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb17-132"><strong>Organizzatore</strong></span><span class="sxs-lookup"><span data-stu-id="0cb17-132"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-133">Indirizzo SIP dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="0cb17-133">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cb17-134"><strong>Ora di fine</strong></span><span class="sxs-lookup"><span data-stu-id="0cb17-134"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-135">Data e ora di fine della conferenza.</span><span class="sxs-lookup"><span data-stu-id="0cb17-135">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0cb17-136">La tabella seguente elenca le informazioni fornite nella sezione Partecipazione conferenza del Rapporto Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="0cb17-136">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="0cb17-137">Metriche di Partecipazione conferenza</span><span class="sxs-lookup"><span data-stu-id="0cb17-137">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0cb17-138">Nome</span><span class="sxs-lookup"><span data-stu-id="0cb17-138">Name</span></span></th>
<th><span data-ttu-id="0cb17-139">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="0cb17-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0cb17-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0cb17-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0cb17-141"><strong>Utente</strong></span><span class="sxs-lookup"><span data-stu-id="0cb17-141"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-142">Indirizzo SIP dell'utente che ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="0cb17-142">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb17-143"><strong>Ruolo</strong></span><span class="sxs-lookup"><span data-stu-id="0cb17-143"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-144">Ruolo, ad esempio Relatore, ricoperto dal partecipante alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="0cb17-144">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cb17-145"><strong>Connettività</strong></span><span class="sxs-lookup"><span data-stu-id="0cb17-145"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-146">Connettività di rete, solitamente Dall'interno o Dall'esterno, per il partecipante.</span><span class="sxs-lookup"><span data-stu-id="0cb17-146">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb17-147">Ora partecipazione</span><span class="sxs-lookup"><span data-stu-id="0cb17-147">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-148">Data e ora in cui il partecipante si è unito alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="0cb17-148">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cb17-149"><strong>Ora uscita</strong></span><span class="sxs-lookup"><span data-stu-id="0cb17-149"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-150">Data e ora in cui il partecipante è uscito dalla conferenza.</span><span class="sxs-lookup"><span data-stu-id="0cb17-150">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb17-151"><strong>Agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="0cb17-151"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-152">Identificatore del software utilizzato dall'endpoint del partecipante.</span><span class="sxs-lookup"><span data-stu-id="0cb17-152">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cb17-153"><strong>Rapporti di diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="0cb17-153"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-p104">Contiene informazioni relative alla diagnostica e alla risoluzione dei problemi, tra cui codici di risposta SIP, intestazioni di diagnostica, ore di partecipazione alla conferenza e ID diagnostica per le sessioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="0cb17-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0cb17-156">Nella tabella seguente sono elencate le informazioni fornite nella sezione modalità conferenza del rapporto Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="0cb17-156">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="0cb17-157">Metriche di Modalità conferenza</span><span class="sxs-lookup"><span data-stu-id="0cb17-157">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0cb17-158">Nome</span><span class="sxs-lookup"><span data-stu-id="0cb17-158">Name</span></span></th>
<th><span data-ttu-id="0cb17-159">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="0cb17-159">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0cb17-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0cb17-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0cb17-161"><strong>Utente</strong></span><span class="sxs-lookup"><span data-stu-id="0cb17-161"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-162">Indirizzo SIP dell'utente che ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="0cb17-162">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb17-163"><strong>Ora partecipazione</strong></span><span class="sxs-lookup"><span data-stu-id="0cb17-163"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-164">Data e ora in cui il partecipante si è unito alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="0cb17-164">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cb17-165"><strong>Ora uscita</strong></span><span class="sxs-lookup"><span data-stu-id="0cb17-165"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-166">Data e ora in cui un partecipante è uscito dalla conferenza.</span><span class="sxs-lookup"><span data-stu-id="0cb17-166">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb17-167"><strong>URI server per conferenze</strong></span><span class="sxs-lookup"><span data-stu-id="0cb17-167"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-168">URI per il server per conferenze utilizzato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="0cb17-168">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cb17-169"><strong>Rapporti di diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="0cb17-169"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cb17-p105">Contiene informazioni relative alla diagnostica e alla risoluzione dei problemi, tra cui codici di risposta SIP, intestazioni di diagnostica, ore di partecipazione alla conferenza e ID diagnostica per le sessioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="0cb17-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

