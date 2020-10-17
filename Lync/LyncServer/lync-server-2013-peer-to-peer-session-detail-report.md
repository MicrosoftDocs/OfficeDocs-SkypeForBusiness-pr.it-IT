---
title: 'Lync Server 2013: rapporto Dettagli sessione peer-to-peer'
description: 'Lync Server 2013: rapporto Dettagli sessione peer-to-peer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e712225fddabb646cc3b862f59601857a7df8eff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557282"
---
# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="78cc2-103">Rapporto Dettagli sessione peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78cc2-103">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78cc2-104">_**Ultimo argomento modificato:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="78cc2-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="78cc2-p101">Nel rapporto Dettagli sessione peer-to-peer vengono fornite informazioni dettagliate sulle sessioni peer-to-peer. Ad esempio, se si seleziona una sessione di messaggistica istantanea, nel rapporto sarà indicato il numero di messaggi inviato da ciascuno dei due utenti della sessione.</span><span class="sxs-lookup"><span data-stu-id="78cc2-p101">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session. For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="78cc2-107">Accedere al Rapporto Dettagli sessione peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="78cc2-107">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="78cc2-108">È possibile accedere al rapporto Dettagli sessione peer-to-peer da uno dei seguenti rapporti (ai quali è possibile accedere dalla pagina principale dei rapporti di monitoraggio):</span><span class="sxs-lookup"><span data-stu-id="78cc2-108">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="78cc2-109">Rapporto inventario telefoni IP</span><span class="sxs-lookup"><span data-stu-id="78cc2-109">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="78cc2-110">Rapporto attività utente</span><span class="sxs-lookup"><span data-stu-id="78cc2-110">User Activity Report</span></span>

  - <span data-ttu-id="78cc2-111">Rapporto controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="78cc2-111">Call Admission Control Report</span></span>

  - <span data-ttu-id="78cc2-112">Rapporto Elenco errori</span><span class="sxs-lookup"><span data-stu-id="78cc2-112">Failure List Report</span></span>

<span data-ttu-id="78cc2-113">Dall'interno del rapporto Dettagli sessione peer-to-peer è possibile accedere al [rapporto di diagnostica in Lync Server 2013](lync-server-2013-diagnostic-report.md) facendo clic sulla metrica del rapporto di diagnostica (Dettagli).</span><span class="sxs-lookup"><span data-stu-id="78cc2-113">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="78cc2-114">Facendo clic su una delle seguenti due metriche, è inoltre possibile accedere al Rapporto errori principali:</span><span class="sxs-lookup"><span data-stu-id="78cc2-114">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="78cc2-115">Risposta</span><span class="sxs-lookup"><span data-stu-id="78cc2-115">Response</span></span>

  - <span data-ttu-id="78cc2-116">ID diagnostica</span><span class="sxs-lookup"><span data-stu-id="78cc2-116">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="78cc2-117">Utilizzare al meglio il Rapporto Dettagli sessione peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="78cc2-117">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="78cc2-p103">Il Rapporto Dettagli sessione peer-to-peer include molte metriche, alcune delle quali potrebbero essere sconosciute agli amministratori di sistema. Spesso, tuttavia, è possibile visualizzare un tooltip contenente la descrizione della metrica, semplicemente passando il mouse sull'etichetta della metrica.</span><span class="sxs-lookup"><span data-stu-id="78cc2-p103">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators. Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="78cc2-p104">Tenere sempre presente che le metriche reali mostrate in un rapporto dipendono dal tipo di sessione peer-to-peer selezionato. Una sessione audio/video riporta un set di metriche diverso rispetto a quello di una sessione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="78cc2-p104">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected. An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="78cc2-122">Passando il mouse sulle metriche Codice di risposta e ID diagnostica, è possibile ottenere una descrizione dei valori:</span><span class="sxs-lookup"><span data-stu-id="78cc2-122">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="78cc2-123">Filtri</span><span class="sxs-lookup"><span data-stu-id="78cc2-123">Filters</span></span>

<span data-ttu-id="78cc2-p105">Nessuno. Non è possibile filtrare il rapporto Dettagli sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="78cc2-p105">None. You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="78cc2-126">Metriche di informazioni sulla sessione</span><span class="sxs-lookup"><span data-stu-id="78cc2-126">Session Information Metrics</span></span>

<span data-ttu-id="78cc2-127">Nella tabella seguente sono elencate le informazioni disponibili nel rapporto Dettagli sessione peer-to-peer per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="78cc2-127">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="78cc2-128">Metriche di informazioni sulla sessione</span><span class="sxs-lookup"><span data-stu-id="78cc2-128">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78cc2-129">Nome</span><span class="sxs-lookup"><span data-stu-id="78cc2-129">Name</span></span></th>
<th><span data-ttu-id="78cc2-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78cc2-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78cc2-131"><strong>FQDN pool</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-131"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-132">Nome di dominio completo (FQDN) del pool di registrazione o server perimetrale interessato dalla sessione.</span><span class="sxs-lookup"><span data-stu-id="78cc2-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78cc2-133"><strong>Ora invito</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-133"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-134">Data e ora in cui è stato inviato in origine l'invito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="78cc2-134">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78cc2-135"><strong>Ora risposta</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-135"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-136">Data e ora in cui è stata ricevuta l'accettazione dell'invito.</span><span class="sxs-lookup"><span data-stu-id="78cc2-136">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78cc2-137"><strong>Da utente</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-137"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-138">Indirizzo SIP dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="78cc2-138">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78cc2-139"><strong>Da agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-139"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-140">Software utilizzato dall'endpoint dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="78cc2-140">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78cc2-141"><strong>Da utente interno</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-141"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-142">Indica se l'utente che ha avviato la sessione ha effettuato l'accesso alla rete interna.</span><span class="sxs-lookup"><span data-stu-id="78cc2-142">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78cc2-143"><strong>Da utente integrato con telefono da tavolo</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-143"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-144">Indica se l'endpoint utilizzato dall'utente che ha avviato la sessione è integrato con il telefono desktop dell'utente stesso.</span><span class="sxs-lookup"><span data-stu-id="78cc2-144">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78cc2-145"><strong>Priorità sessione</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-145"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-p106">Priorità assegnata alla sessione. Le priorità valide sono: Sconosciuto, Non urgente, Normale, Urgente ed Emergenza.</span><span class="sxs-lookup"><span data-stu-id="78cc2-p106">Priority assigned to the session. Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78cc2-148"><strong>Codice di risposta</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-148"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-149">Codice di risposta SIP inviato quando la sessione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="78cc2-149">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78cc2-150"><strong>Front End</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-150"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-151">Nome del server Front End Server utilizzato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="78cc2-151">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78cc2-152"><strong>Ora di acquisizione</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-152"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-153">Data e ora in cui sono state registrate le informazioni sulla sessione.</span><span class="sxs-lookup"><span data-stu-id="78cc2-153">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78cc2-154"><strong>Ora fine</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-154"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-155">Data e ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="78cc2-155">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78cc2-156"><strong>A utente</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-156"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-157">Indirizzo SIP dell'utente invitato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="78cc2-157">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78cc2-158"><strong>Ad agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-158"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-159">Software utilizzato dall'endpoint dell'utente invitato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="78cc2-159">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78cc2-160"><strong>A utente interno</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-160"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-161">Indica se l'utente invitato alla sessione ha effettuato l'accesso alla rete interna.</span><span class="sxs-lookup"><span data-stu-id="78cc2-161">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78cc2-162"><strong>A utente integrato con telefono da tavolo</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-162"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-163">Indica se l'endpoint utilizzato dall'utente invitato alla sessione è integrato con il telefono desktop dell'utente stesso.</span><span class="sxs-lookup"><span data-stu-id="78cc2-163">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78cc2-164"><strong>Sessione ripetuta</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-164"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-165">Indica se la sessione è un tentativo di ripetizione di una sessione non riuscita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="78cc2-165">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78cc2-166"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-166"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-p107">Identificatore univoco, sotto forma di intestazione ms-diagnostics, allegato a un messaggio SIP che include spesso informazioni utili per la risoluzione degli errori. Posizionare il puntatore del mouse sull'ID per visualizzare informazioni aggiuntive sull'ID stesso.</span><span class="sxs-lookup"><span data-stu-id="78cc2-p107">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="78cc2-169">Metriche per le modalità</span><span class="sxs-lookup"><span data-stu-id="78cc2-169">Metrics for Modalities</span></span>

<span data-ttu-id="78cc2-170">Nella tabella seguente sono elencate le informazioni disponibili nel rapporto Dettagli sessione peer-to-peer per ogni modalità di sessione.</span><span class="sxs-lookup"><span data-stu-id="78cc2-170">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="78cc2-171">Metriche per le modalità</span><span class="sxs-lookup"><span data-stu-id="78cc2-171">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78cc2-172">Nome</span><span class="sxs-lookup"><span data-stu-id="78cc2-172">Name</span></span></th>
<th><span data-ttu-id="78cc2-173">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="78cc2-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="78cc2-174">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78cc2-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78cc2-175"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-175"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-176">No</span><span class="sxs-lookup"><span data-stu-id="78cc2-176">No</span></span></p></td>
<td><p><span data-ttu-id="78cc2-p108">Modalità utilizzate nella sessione, ad esempio messaggistica istantanea o trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="78cc2-p108">Modalities used in the session. For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78cc2-179"><strong>Messaggi da utente</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-179"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-180">No</span><span class="sxs-lookup"><span data-stu-id="78cc2-180">No</span></span></p></td>
<td><p><span data-ttu-id="78cc2-181">Numero di messaggi inviati dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="78cc2-181">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78cc2-182"><strong>Messaggi a utente</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-182"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-183">No</span><span class="sxs-lookup"><span data-stu-id="78cc2-183">No</span></span></p></td>
<td><p><span data-ttu-id="78cc2-184">Numero di messaggi inviati dall'utente invitato a partecipare alla sessione.</span><span class="sxs-lookup"><span data-stu-id="78cc2-184">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="78cc2-185">Metriche per i rapporti di diagnostica</span><span class="sxs-lookup"><span data-stu-id="78cc2-185">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="78cc2-186">Nella tabella seguente sono elencate le informazioni disponibili nel rapporto Dettagli sessione peer-to-peer per ogni rapporto di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="78cc2-186">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="78cc2-187">Metriche per i rapporti di diagnostica</span><span class="sxs-lookup"><span data-stu-id="78cc2-187">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78cc2-188">Nome</span><span class="sxs-lookup"><span data-stu-id="78cc2-188">Name</span></span></th>
<th><span data-ttu-id="78cc2-189">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="78cc2-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="78cc2-190">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78cc2-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78cc2-191"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-191"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-192">No</span><span class="sxs-lookup"><span data-stu-id="78cc2-192">No</span></span></p></td>
<td><p><span data-ttu-id="78cc2-193">Quando si fa clic su questo elemento, nel rapporto viene visualizzato il rapporto di diagnostica per la sessione.</span><span class="sxs-lookup"><span data-stu-id="78cc2-193">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78cc2-194"><strong>Ora rapporto</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-194"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-195">No</span><span class="sxs-lookup"><span data-stu-id="78cc2-195">No</span></span></p></td>
<td><p><span data-ttu-id="78cc2-196">Data e ora di registrazione del rapporto.</span><span class="sxs-lookup"><span data-stu-id="78cc2-196">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78cc2-197"><strong>Richiesta</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-197"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-198">No</span><span class="sxs-lookup"><span data-stu-id="78cc2-198">No</span></span></p></td>
<td><p><span data-ttu-id="78cc2-p109">Tipo di richiesta SIP, ad esempio INVITE o BYE.</span><span class="sxs-lookup"><span data-stu-id="78cc2-p109">SIP request type. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78cc2-201"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-201"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-202">No</span><span class="sxs-lookup"><span data-stu-id="78cc2-202">No</span></span></p></td>
<td><p><span data-ttu-id="78cc2-203">Identificatore univoco (in forma di intestazione ms-diagnostics) associato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione dei problemi e degli errori.</span><span class="sxs-lookup"><span data-stu-id="78cc2-203">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78cc2-204"><strong>Tipo di contenuto</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-204"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-205">No</span><span class="sxs-lookup"><span data-stu-id="78cc2-205">No</span></span></p></td>
<td><p><span data-ttu-id="78cc2-p110">Tipo di contenuto multimediale utilizzato nella conferenza. Un tipo di contenuto comune, ad esempio, è Application/sdp. SDP (Session Description Protocol) è un protocollo Internet standard utilizzato per annunci di sessioni, inviti a sessioni e altre forme di avvio di sessioni multimediali.</span><span class="sxs-lookup"><span data-stu-id="78cc2-p110">Type of media content used in the conference. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78cc2-209"><strong>Segnalato da</strong></span><span class="sxs-lookup"><span data-stu-id="78cc2-209"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="78cc2-210">No</span><span class="sxs-lookup"><span data-stu-id="78cc2-210">No</span></span></p></td>
<td><p><span data-ttu-id="78cc2-211">Computer, ovvero client o server, che ha segnalato il problema.</span><span class="sxs-lookup"><span data-stu-id="78cc2-211">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

