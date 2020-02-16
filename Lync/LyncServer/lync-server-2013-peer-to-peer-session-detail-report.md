---
title: 'Lync Server 2013: rapporto Dettagli sessione peer-to-peer'
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
ms.openlocfilehash: c977b2f9f9a6248ab7ba5d5391397d4cd4326a18
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="13e75-102">Rapporto Dettagli sessione peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13e75-102">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13e75-103">_**Ultimo argomento modificato:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="13e75-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="13e75-p101">Nel rapporto Dettagli sessione peer-to-peer vengono fornite informazioni dettagliate sulle sessioni peer-to-peer. Ad esempio, se si seleziona una sessione di messaggistica istantanea, nel rapporto sarà indicato il numero di messaggi inviato da ciascuno dei due utenti della sessione.</span><span class="sxs-lookup"><span data-stu-id="13e75-p101">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session. For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="13e75-106">Accedere al Rapporto Dettagli sessione peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="13e75-106">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="13e75-107">È possibile accedere al rapporto Dettagli sessione peer-to-peer da uno dei seguenti rapporti (ai quali è possibile accedere dalla pagina principale dei rapporti di monitoraggio):</span><span class="sxs-lookup"><span data-stu-id="13e75-107">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="13e75-108">Rapporto inventario telefoni IP</span><span class="sxs-lookup"><span data-stu-id="13e75-108">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="13e75-109">Rapporto attività utente</span><span class="sxs-lookup"><span data-stu-id="13e75-109">User Activity Report</span></span>

  - <span data-ttu-id="13e75-110">Rapporto controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="13e75-110">Call Admission Control Report</span></span>

  - <span data-ttu-id="13e75-111">Rapporto Elenco errori</span><span class="sxs-lookup"><span data-stu-id="13e75-111">Failure List Report</span></span>

<span data-ttu-id="13e75-112">Dall'interno del rapporto Dettagli sessione peer-to-peer è possibile accedere al [rapporto di diagnostica in Lync Server 2013](lync-server-2013-diagnostic-report.md) facendo clic sulla metrica del rapporto di diagnostica (Dettagli).</span><span class="sxs-lookup"><span data-stu-id="13e75-112">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="13e75-113">Facendo clic su una delle seguenti due metriche, è inoltre possibile accedere al Rapporto errori principali:</span><span class="sxs-lookup"><span data-stu-id="13e75-113">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="13e75-114">Risposta</span><span class="sxs-lookup"><span data-stu-id="13e75-114">Response</span></span>

  - <span data-ttu-id="13e75-115">ID diagnostica</span><span class="sxs-lookup"><span data-stu-id="13e75-115">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="13e75-116">Utilizzare al meglio il Rapporto Dettagli sessione peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="13e75-116">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="13e75-p103">Il Rapporto Dettagli sessione peer-to-peer include molte metriche, alcune delle quali potrebbero essere sconosciute agli amministratori di sistema. Spesso, tuttavia, è possibile visualizzare un tooltip contenente la descrizione della metrica, semplicemente passando il mouse sull'etichetta della metrica.</span><span class="sxs-lookup"><span data-stu-id="13e75-p103">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators. Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="13e75-p104">Tenere sempre presente che le metriche reali mostrate in un rapporto dipendono dal tipo di sessione peer-to-peer selezionato. Una sessione audio/video riporta un set di metriche diverso rispetto a quello di una sessione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="13e75-p104">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected. An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="13e75-121">Passando il mouse sulle metriche Codice di risposta e ID diagnostica, è possibile ottenere una descrizione dei valori:</span><span class="sxs-lookup"><span data-stu-id="13e75-121">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="13e75-122">Filtri</span><span class="sxs-lookup"><span data-stu-id="13e75-122">Filters</span></span>

<span data-ttu-id="13e75-p105">Nessuno. Non è possibile filtrare il rapporto Dettagli sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="13e75-p105">None. You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="13e75-125">Metriche di informazioni sulla sessione</span><span class="sxs-lookup"><span data-stu-id="13e75-125">Session Information Metrics</span></span>

<span data-ttu-id="13e75-126">Nella tabella seguente sono elencate le informazioni disponibili nel rapporto Dettagli sessione peer-to-peer per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="13e75-126">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="13e75-127">Metriche di informazioni sulla sessione</span><span class="sxs-lookup"><span data-stu-id="13e75-127">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="13e75-128">Name</span><span class="sxs-lookup"><span data-stu-id="13e75-128">Name</span></span></th>
<th><span data-ttu-id="13e75-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13e75-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13e75-130"><strong>FQDN pool</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-130"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-131">Nome di dominio completo (FQDN) del pool di registrazione o server perimetrale interessato dalla sessione.</span><span class="sxs-lookup"><span data-stu-id="13e75-131">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e75-132"><strong>Ora invito</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-132"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-133">Data e ora in cui è stato inviato in origine l'invito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="13e75-133">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13e75-134"><strong>Ora risposta</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-134"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-135">Data e ora in cui è stata ricevuta l'accettazione dell'invito.</span><span class="sxs-lookup"><span data-stu-id="13e75-135">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e75-136"><strong>Da utente</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-136"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-137">Indirizzo SIP dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="13e75-137">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13e75-138"><strong>Da agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-138"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-139">Software utilizzato dall'endpoint dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="13e75-139">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e75-140"><strong>Da utente interno</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-140"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-141">Indica se l'utente che ha avviato la sessione ha effettuato l'accesso alla rete interna.</span><span class="sxs-lookup"><span data-stu-id="13e75-141">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13e75-142"><strong>Da utente integrato con telefono da tavolo</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-142"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-143">Indica se l'endpoint utilizzato dall'utente che ha avviato la sessione è integrato con il telefono desktop dell'utente stesso.</span><span class="sxs-lookup"><span data-stu-id="13e75-143">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e75-144"><strong>Priorità sessione</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-144"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-p106">Priorità assegnata alla sessione. Le priorità valide sono: Sconosciuto, Non urgente, Normale, Urgente ed Emergenza.</span><span class="sxs-lookup"><span data-stu-id="13e75-p106">Priority assigned to the session. Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13e75-147"><strong>Codice di risposta</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-147"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-148">Codice di risposta SIP inviato quando la sessione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="13e75-148">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e75-149"><strong>Front End</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-149"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-150">Nome del server Front End Server utilizzato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="13e75-150">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13e75-151"><strong>Ora di acquisizione</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-151"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-152">Data e ora in cui sono state registrate le informazioni sulla sessione.</span><span class="sxs-lookup"><span data-stu-id="13e75-152">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e75-153"><strong>Ora fine</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-153"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-154">Data e ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="13e75-154">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13e75-155"><strong>A utente</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-155"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-156">Indirizzo SIP dell'utente invitato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="13e75-156">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e75-157"><strong>Ad agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-157"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-158">Software utilizzato dall'endpoint dell'utente invitato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="13e75-158">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13e75-159"><strong>A utente interno</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-159"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-160">Indica se l'utente invitato alla sessione ha effettuato l'accesso alla rete interna.</span><span class="sxs-lookup"><span data-stu-id="13e75-160">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e75-161"><strong>A utente integrato con telefono da tavolo</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-161"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-162">Indica se l'endpoint utilizzato dall'utente invitato alla sessione è integrato con il telefono desktop dell'utente stesso.</span><span class="sxs-lookup"><span data-stu-id="13e75-162">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13e75-163"><strong>Sessione ripetuta</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-163"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-164">Indica se la sessione è un tentativo di ripetizione di una sessione non riuscita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="13e75-164">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e75-165"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-165"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-p107">Identificatore univoco, sotto forma di intestazione ms-diagnostics, allegato a un messaggio SIP che include spesso informazioni utili per la risoluzione degli errori. Posizionare il puntatore del mouse sull'ID per visualizzare informazioni aggiuntive sull'ID stesso.</span><span class="sxs-lookup"><span data-stu-id="13e75-p107">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="13e75-168">Metriche per le modalità</span><span class="sxs-lookup"><span data-stu-id="13e75-168">Metrics for Modalities</span></span>

<span data-ttu-id="13e75-169">Nella tabella seguente sono elencate le informazioni disponibili nel rapporto Dettagli sessione peer-to-peer per ogni modalità di sessione.</span><span class="sxs-lookup"><span data-stu-id="13e75-169">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="13e75-170">Metriche per le modalità</span><span class="sxs-lookup"><span data-stu-id="13e75-170">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="13e75-171">Name</span><span class="sxs-lookup"><span data-stu-id="13e75-171">Name</span></span></th>
<th><span data-ttu-id="13e75-172">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="13e75-172">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="13e75-173">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13e75-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13e75-174"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-174"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-175">No</span><span class="sxs-lookup"><span data-stu-id="13e75-175">No</span></span></p></td>
<td><p><span data-ttu-id="13e75-p108">Modalità utilizzate nella sessione, ad esempio messaggistica istantanea o trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="13e75-p108">Modalities used in the session. For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e75-178"><strong>Messaggi da utente</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-178"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-179">No</span><span class="sxs-lookup"><span data-stu-id="13e75-179">No</span></span></p></td>
<td><p><span data-ttu-id="13e75-180">Numero di messaggi inviati dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="13e75-180">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13e75-181"><strong>Messaggi a utente</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-181"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-182">No</span><span class="sxs-lookup"><span data-stu-id="13e75-182">No</span></span></p></td>
<td><p><span data-ttu-id="13e75-183">Numero di messaggi inviati dall'utente invitato a partecipare alla sessione.</span><span class="sxs-lookup"><span data-stu-id="13e75-183">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="13e75-184">Metriche per i rapporti di diagnostica</span><span class="sxs-lookup"><span data-stu-id="13e75-184">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="13e75-185">Nella tabella seguente sono elencate le informazioni disponibili nel rapporto Dettagli sessione peer-to-peer per ogni rapporto di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="13e75-185">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="13e75-186">Metriche per i rapporti di diagnostica</span><span class="sxs-lookup"><span data-stu-id="13e75-186">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="13e75-187">Name</span><span class="sxs-lookup"><span data-stu-id="13e75-187">Name</span></span></th>
<th><span data-ttu-id="13e75-188">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="13e75-188">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="13e75-189">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13e75-189">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13e75-190"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-190"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-191">No</span><span class="sxs-lookup"><span data-stu-id="13e75-191">No</span></span></p></td>
<td><p><span data-ttu-id="13e75-192">Quando si fa clic su questo elemento, nel rapporto viene visualizzato il rapporto di diagnostica per la sessione.</span><span class="sxs-lookup"><span data-stu-id="13e75-192">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e75-193"><strong>Ora rapporto</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-193"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-194">No</span><span class="sxs-lookup"><span data-stu-id="13e75-194">No</span></span></p></td>
<td><p><span data-ttu-id="13e75-195">Data e ora di registrazione del rapporto.</span><span class="sxs-lookup"><span data-stu-id="13e75-195">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13e75-196"><strong>Richiesta</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-196"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-197">No</span><span class="sxs-lookup"><span data-stu-id="13e75-197">No</span></span></p></td>
<td><p><span data-ttu-id="13e75-p109">Tipo di richiesta SIP, ad esempio INVITE o BYE.</span><span class="sxs-lookup"><span data-stu-id="13e75-p109">SIP request type. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e75-200"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-200"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-201">No</span><span class="sxs-lookup"><span data-stu-id="13e75-201">No</span></span></p></td>
<td><p><span data-ttu-id="13e75-202">Identificatore univoco (in forma di intestazione ms-diagnostics) associato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione dei problemi e degli errori.</span><span class="sxs-lookup"><span data-stu-id="13e75-202">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13e75-203"><strong>Tipo di contenuto</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-203"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-204">No</span><span class="sxs-lookup"><span data-stu-id="13e75-204">No</span></span></p></td>
<td><p><span data-ttu-id="13e75-p110">Tipo di contenuto multimediale utilizzato nella conferenza. Un tipo di contenuto comune, ad esempio, è Application/sdp. SDP (Session Description Protocol) è un protocollo Internet standard utilizzato per annunci di sessioni, inviti a sessioni e altre forme di avvio di sessioni multimediali.</span><span class="sxs-lookup"><span data-stu-id="13e75-p110">Type of media content used in the conference. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e75-208"><strong>Segnalato da</strong></span><span class="sxs-lookup"><span data-stu-id="13e75-208"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="13e75-209">No</span><span class="sxs-lookup"><span data-stu-id="13e75-209">No</span></span></p></td>
<td><p><span data-ttu-id="13e75-210">Computer, ovvero client o server, che ha segnalato il problema.</span><span class="sxs-lookup"><span data-stu-id="13e75-210">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

