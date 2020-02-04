---
title: 'Lync Server 2013: report Dettagli conferenza'
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
ms.openlocfilehash: 7e8e2cd992e83adb29c43935d4b4c7f223580d53
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="71c55-102">Report Dettagli conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71c55-102">Conference Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71c55-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="71c55-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="71c55-104">Il report Dettagli conferenza offre informazioni dettagliate su tutti gli utenti che hanno partecipato a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-104">The Conference Detail Report provides detailed information about all the users who participated in a conference.</span></span> <span data-ttu-id="71c55-105">Ad esempio, puoi visualizzare informazioni come la data e l'ora in cui un utente ha partecipato alla conferenza, la data e l'ora in cui l'utente ha lasciato la conferenza e l'agente utente dell'endpoint usato per connettere l'utente alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-105">For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference.</span></span> <span data-ttu-id="71c55-106">È anche possibile visualizzare le informazioni sul ruolo dell'utente in ogni conferenza, ad esempio relatore o partecipante.</span><span class="sxs-lookup"><span data-stu-id="71c55-106">You can also see information the user's role in each conference (for example, Presenter or Attendee).</span></span> <span data-ttu-id="71c55-107">Forse la cosa più importante è vedere rapidamente gli utenti che partecipano e completano la conferenza e che gli utenti non sono stati in grado di partecipare e completare la conferenza con successo.</span><span class="sxs-lookup"><span data-stu-id="71c55-107">Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="71c55-108">Accesso al report Dettagli conferenza</span><span class="sxs-lookup"><span data-stu-id="71c55-108">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="71c55-109">È possibile accedere al report Dettagli conferenza dai report seguenti:</span><span class="sxs-lookup"><span data-stu-id="71c55-109">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="71c55-110">[Report di controllo ammissione chiamata in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (facendo clic sulla metrica di dettaglio per una conferenza)</span><span class="sxs-lookup"><span data-stu-id="71c55-110">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="71c55-111">[Report elenco errori in Lync Server 2013](lync-server-2013-failure-list-report.md) (facendo clic sulla metrica conferenza)</span><span class="sxs-lookup"><span data-stu-id="71c55-111">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="71c55-112">[Report attività utente in Lync Server 2013](lync-server-2013-user-activity-report.md) (facendo clic sulla metrica URI conferenza)</span><span class="sxs-lookup"><span data-stu-id="71c55-112">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="71c55-113">Dal report Dettagli conferenza è possibile accedere al [report di diagnostica in Lync Server 2013](lync-server-2013-diagnostic-report.md) facendo clic sulla metrica rapporto di diagnostica (dettaglio).</span><span class="sxs-lookup"><span data-stu-id="71c55-113">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="71c55-114">Filtri</span><span class="sxs-lookup"><span data-stu-id="71c55-114">Filters</span></span>

<span data-ttu-id="71c55-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="71c55-115">None.</span></span> <span data-ttu-id="71c55-116">Non è possibile filtrare il report Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-116">You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="71c55-117">Metriche</span><span class="sxs-lookup"><span data-stu-id="71c55-117">Metrics</span></span>

<span data-ttu-id="71c55-118">Nella tabella seguente sono elencate le informazioni fornite nella sezione informazioni conferenza del report Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-118">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="71c55-119">Metriche delle informazioni sulla conferenza</span><span class="sxs-lookup"><span data-stu-id="71c55-119">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71c55-120">Nome</span><span class="sxs-lookup"><span data-stu-id="71c55-120">Name</span></span></th>
<th><span data-ttu-id="71c55-121">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="71c55-121">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="71c55-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71c55-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71c55-123"><strong>URI conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="71c55-123"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-124">URI assegnato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-124">URI assigned to the conference.</span></span> <span data-ttu-id="71c55-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="71c55-125">For example:</span></span></p>
<p><span data-ttu-id="71c55-126">SIP: kmyer@litwareinc. com; GRUU; opaque = app: conf: stato attiva: ID: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="71c55-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c55-127"><strong>FQDN del pool</strong></span><span class="sxs-lookup"><span data-stu-id="71c55-127"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-128">Nome di dominio completo del pool di registrazione o del server perimetrale coinvolto in una sessione.</span><span class="sxs-lookup"><span data-stu-id="71c55-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71c55-129"><strong>Ora di inizio</strong></span><span class="sxs-lookup"><span data-stu-id="71c55-129"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-130">Data e ora in cui è stata avviata la conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-130">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c55-131"><strong>Organizzatore</strong></span><span class="sxs-lookup"><span data-stu-id="71c55-131"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-132">Indirizzo SIP dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-132">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71c55-133"><strong>Ora di fine</strong></span><span class="sxs-lookup"><span data-stu-id="71c55-133"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-134">Data e ora di fine della conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-134">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="71c55-135">Nella tabella seguente sono elencate le informazioni fornite nella sezione partecipazione alla conferenza del report Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="71c55-136">Metriche per la partecipazione alla conferenza</span><span class="sxs-lookup"><span data-stu-id="71c55-136">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71c55-137">Nome</span><span class="sxs-lookup"><span data-stu-id="71c55-137">Name</span></span></th>
<th><span data-ttu-id="71c55-138">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="71c55-138">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="71c55-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71c55-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71c55-140"><strong>Utente</strong></span><span class="sxs-lookup"><span data-stu-id="71c55-140"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-141">Indirizzo SIP dell'utente che ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-141">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c55-142"><strong>Ruolo</strong></span><span class="sxs-lookup"><span data-stu-id="71c55-142"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-143">Ruolo (ad esempio, relatore) riprodotto dal partecipante alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-143">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71c55-144"><strong>Connettività</strong></span><span class="sxs-lookup"><span data-stu-id="71c55-144"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-145">Connettività di rete (in genere da interno o da esterno) per il partecipante.</span><span class="sxs-lookup"><span data-stu-id="71c55-145">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c55-146">Tempo di partecipazione</span><span class="sxs-lookup"><span data-stu-id="71c55-146">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-147">Data e ora in cui il partecipante ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-147">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71c55-148"><strong>Ora di uscita</strong></span><span class="sxs-lookup"><span data-stu-id="71c55-148"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-149">Data e ora in cui il partecipante ha lasciato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-149">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c55-150"><strong>Agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="71c55-150"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-151">Identificatore per il software usato dall'endpoint del partecipante.</span><span class="sxs-lookup"><span data-stu-id="71c55-151">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71c55-152"><strong>Report di diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="71c55-152"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-153">Fornisce informazioni di diagnostica e risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="71c55-153">Provides diagnostic and troubleshooting information.</span></span> <span data-ttu-id="71c55-154">Inclusi i codici di risposta SIP, le intestazioni di diagnostica, le ore di conferenza e gli ID di diagnostica per le sessioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="71c55-154">Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="71c55-155">Nella tabella seguente sono elencate le informazioni fornite nella sezione modalità conferenza del report Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-155">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="71c55-156">Metriche delle modalità conferenza</span><span class="sxs-lookup"><span data-stu-id="71c55-156">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71c55-157">Nome</span><span class="sxs-lookup"><span data-stu-id="71c55-157">Name</span></span></th>
<th><span data-ttu-id="71c55-158">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="71c55-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="71c55-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71c55-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71c55-160"><strong>Utente</strong></span><span class="sxs-lookup"><span data-stu-id="71c55-160"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-161">Indirizzo SIP dell'utente che ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-161">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c55-162"><strong>Tempo di partecipazione</strong></span><span class="sxs-lookup"><span data-stu-id="71c55-162"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-163">Data e ora in cui il partecipante ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-163">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71c55-164"><strong>Ora di uscita</strong></span><span class="sxs-lookup"><span data-stu-id="71c55-164"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-165">Data e ora in cui un partecipante ha lasciato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-165">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c55-166"><strong>URI di conferenza server</strong></span><span class="sxs-lookup"><span data-stu-id="71c55-166"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-167">URI per il server delle conferenze usato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="71c55-167">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71c55-168"><strong>Report di diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="71c55-168"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c55-169">Fornisce informazioni di diagnostica e risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="71c55-169">Provides diagnostic and troubleshooting information.</span></span> <span data-ttu-id="71c55-170">Inclusi i codici di risposta SIP, le intestazioni di diagnostica, le ore di conferenza e gli ID di diagnostica per le sessioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="71c55-170">Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

