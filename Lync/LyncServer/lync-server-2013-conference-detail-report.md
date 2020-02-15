---
title: 'Lync Server 2013: rapporto Dettagli conferenza'
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
ms.openlocfilehash: dce868d90d2811b36a4f11c159b4e7d9d29b5ffa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="7c1bc-102">Rapporto Dettagli conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c1bc-102">Conference Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c1bc-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="7c1bc-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="7c1bc-p101">Il Rapporto Dettagli conferenza offre informazioni dettagliate su tutti gli utenti che hanno partecipato a una conferenza. È ad esempio possibile conoscere la data e l'ora in cui un utente si è unito alla conferenza o in cui l'ha abbandonata e l'agente utente dell'endpoint utilizzato per connettere tale utente alla conferenza. È anche possibile visualizzare informazioni sul ruolo dell'utente in ciascuna conferenza (relatore o partecipante). E ancora più importante, è possibile sapere rapidamente quali utenti si sono uniti alla conferenza e l'hanno completata e quali non ci sono riusciti.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="7c1bc-108">Accesso al Rapporto Dettagli conferenza</span><span class="sxs-lookup"><span data-stu-id="7c1bc-108">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="7c1bc-109">Il Rapporto Dettagli conferenza è accessibile dai rapporti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c1bc-109">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="7c1bc-110">Il [rapporto di controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (facendo clic sulla metrica Dettagli per una conferenza)</span><span class="sxs-lookup"><span data-stu-id="7c1bc-110">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="7c1bc-111">Il [rapporto Elenco errori in Lync Server 2013](lync-server-2013-failure-list-report.md) (facendo clic sulla metrica conferenza)</span><span class="sxs-lookup"><span data-stu-id="7c1bc-111">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="7c1bc-112">Il [rapporto attività utente in Lync Server 2013](lync-server-2013-user-activity-report.md) (facendo clic sulla metrica URI conferenza)</span><span class="sxs-lookup"><span data-stu-id="7c1bc-112">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="7c1bc-113">Dal rapporto Dettagli conferenza è possibile accedere al [rapporto di diagnostica in Lync Server 2013](lync-server-2013-diagnostic-report.md) facendo clic sulla metrica del rapporto di diagnostica (dettaglio).</span><span class="sxs-lookup"><span data-stu-id="7c1bc-113">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7c1bc-114">Filtri</span><span class="sxs-lookup"><span data-stu-id="7c1bc-114">Filters</span></span>

<span data-ttu-id="7c1bc-p102">Nessuno. Non è possibile applicare filtri al Rapporto Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-p102">None. You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7c1bc-117">Metriche</span><span class="sxs-lookup"><span data-stu-id="7c1bc-117">Metrics</span></span>

<span data-ttu-id="7c1bc-118">La tabella seguente elenca le informazioni contenute nella sezione Informazioni conferenza del Rapporto Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-118">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="7c1bc-119">Metriche Informazioni conferenza</span><span class="sxs-lookup"><span data-stu-id="7c1bc-119">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c1bc-120">Nome</span><span class="sxs-lookup"><span data-stu-id="7c1bc-120">Name</span></span></th>
<th><span data-ttu-id="7c1bc-121">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="7c1bc-121">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7c1bc-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c1bc-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c1bc-123"><strong>URI conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="7c1bc-123"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-p103">URI assegnato alla conferenza, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7c1bc-p103">URI assigned to the conference. For example:</span></span></p>
<p><span data-ttu-id="7c1bc-126">SIP: kmyer@litwareinc. com; GRUU; opaque = app: conf: Focus: ID: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="7c1bc-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c1bc-127"><strong>FQDN pool</strong></span><span class="sxs-lookup"><span data-stu-id="7c1bc-127"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-128">Nome di dominio completo del pool di registrazione o del server perimetrale operativo in una sessione.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c1bc-129"><strong>Ora di inizio</strong></span><span class="sxs-lookup"><span data-stu-id="7c1bc-129"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-130">Data e ora di inizio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-130">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c1bc-131"><strong>Organizzatore</strong></span><span class="sxs-lookup"><span data-stu-id="7c1bc-131"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-132">Indirizzo SIP dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-132">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c1bc-133"><strong>Ora di fine</strong></span><span class="sxs-lookup"><span data-stu-id="7c1bc-133"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-134">Data e ora di fine della conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-134">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7c1bc-135">La tabella seguente elenca le informazioni fornite nella sezione Partecipazione conferenza del Rapporto Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="7c1bc-136">Metriche di Partecipazione conferenza</span><span class="sxs-lookup"><span data-stu-id="7c1bc-136">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c1bc-137">Nome</span><span class="sxs-lookup"><span data-stu-id="7c1bc-137">Name</span></span></th>
<th><span data-ttu-id="7c1bc-138">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="7c1bc-138">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7c1bc-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c1bc-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c1bc-140"><strong>Utente</strong></span><span class="sxs-lookup"><span data-stu-id="7c1bc-140"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-141">Indirizzo SIP dell'utente che ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-141">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c1bc-142"><strong>Ruolo</strong></span><span class="sxs-lookup"><span data-stu-id="7c1bc-142"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-143">Ruolo, ad esempio Relatore, ricoperto dal partecipante alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-143">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c1bc-144"><strong>Connettività</strong></span><span class="sxs-lookup"><span data-stu-id="7c1bc-144"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-145">Connettività di rete, solitamente Dall'interno o Dall'esterno, per il partecipante.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-145">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c1bc-146">Ora partecipazione</span><span class="sxs-lookup"><span data-stu-id="7c1bc-146">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-147">Data e ora in cui il partecipante si è unito alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-147">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c1bc-148"><strong>Ora uscita</strong></span><span class="sxs-lookup"><span data-stu-id="7c1bc-148"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-149">Data e ora in cui il partecipante è uscito dalla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-149">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c1bc-150"><strong>Agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="7c1bc-150"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-151">Identificatore del software utilizzato dall'endpoint del partecipante.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-151">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c1bc-152"><strong>Rapporti di diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="7c1bc-152"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-p104">Contiene informazioni relative alla diagnostica e alla risoluzione dei problemi, tra cui codici di risposta SIP, intestazioni di diagnostica, ore di partecipazione alla conferenza e ID diagnostica per le sessioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7c1bc-155">Nella tabella seguente sono elencate le informazioni fornite nella sezione modalità conferenza del rapporto Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-155">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="7c1bc-156">Metriche di Modalità conferenza</span><span class="sxs-lookup"><span data-stu-id="7c1bc-156">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c1bc-157">Nome</span><span class="sxs-lookup"><span data-stu-id="7c1bc-157">Name</span></span></th>
<th><span data-ttu-id="7c1bc-158">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="7c1bc-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7c1bc-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c1bc-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c1bc-160"><strong>Utente</strong></span><span class="sxs-lookup"><span data-stu-id="7c1bc-160"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-161">Indirizzo SIP dell'utente che ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-161">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c1bc-162"><strong>Ora partecipazione</strong></span><span class="sxs-lookup"><span data-stu-id="7c1bc-162"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-163">Data e ora in cui il partecipante si è unito alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-163">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c1bc-164"><strong>Ora uscita</strong></span><span class="sxs-lookup"><span data-stu-id="7c1bc-164"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-165">Data e ora in cui un partecipante è uscito dalla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-165">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c1bc-166"><strong>URI server per conferenze</strong></span><span class="sxs-lookup"><span data-stu-id="7c1bc-166"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-167">URI per il server per conferenze utilizzato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-167">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c1bc-168"><strong>Rapporti di diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="7c1bc-168"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c1bc-p105">Contiene informazioni relative alla diagnostica e alla risoluzione dei problemi, tra cui codici di risposta SIP, intestazioni di diagnostica, ore di partecipazione alla conferenza e ID diagnostica per le sessioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="7c1bc-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

