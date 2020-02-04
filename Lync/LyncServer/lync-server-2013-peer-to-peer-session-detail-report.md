---
title: 'Lync Server 2013: report Dettagli sessione peer-to-peer'
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
ms.openlocfilehash: bff140db52a98e0b442ca65bbbb8b148282c5755
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="a794e-102">Report Dettagli sessione peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a794e-102">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a794e-103">_**Argomento Ultima modifica:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="a794e-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="a794e-104">Il report Dettagli sessione peer-to-peer restituisce informazioni dettagliate su una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="a794e-104">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session.</span></span> <span data-ttu-id="a794e-105">Ad esempio, se selezioni una sessione di messaggistica istantanea, il report indica il numero di messaggi inviati da ognuno dei due utenti della sessione.</span><span class="sxs-lookup"><span data-stu-id="a794e-105">For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="a794e-106">Accesso al report Dettagli sessione peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="a794e-106">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="a794e-107">È possibile accedere al report Dettagli sessione peer-to-peer da uno dei report seguenti (a cui è possibile accedere tutti dalla Home page dei report di monitoraggio):</span><span class="sxs-lookup"><span data-stu-id="a794e-107">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="a794e-108">Rapporto inventario telefoni IP</span><span class="sxs-lookup"><span data-stu-id="a794e-108">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="a794e-109">Rapporto attività utente</span><span class="sxs-lookup"><span data-stu-id="a794e-109">User Activity Report</span></span>

  - <span data-ttu-id="a794e-110">Rapporto controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="a794e-110">Call Admission Control Report</span></span>

  - <span data-ttu-id="a794e-111">Rapporto Elenco errori</span><span class="sxs-lookup"><span data-stu-id="a794e-111">Failure List Report</span></span>

<span data-ttu-id="a794e-112">Dal report Dettagli sessione peer-to-peer è possibile accedere al report di [diagnostica in Lync Server 2013](lync-server-2013-diagnostic-report.md) facendo clic sulla metrica rapporto di diagnostica (Dettagli).</span><span class="sxs-lookup"><span data-stu-id="a794e-112">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="a794e-113">Per accedere al report errori principali, è anche possibile fare clic su una delle due metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="a794e-113">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="a794e-114">Risposta</span><span class="sxs-lookup"><span data-stu-id="a794e-114">Response</span></span>

  - <span data-ttu-id="a794e-115">ID diagnostica</span><span class="sxs-lookup"><span data-stu-id="a794e-115">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="a794e-116">Sfruttare al meglio il report Dettagli sessione peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="a794e-116">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="a794e-117">Il report Dettagli sessione peer-to-peer include un numero elevato di metriche, molte delle quali potrebbero non essere familiari con gli amministratori di sistema.</span><span class="sxs-lookup"><span data-stu-id="a794e-117">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators.</span></span> <span data-ttu-id="a794e-118">Spesso, tuttavia, è possibile visualizzare una descrizione comando che offre una breve descrizione di tale metrica semplicemente tenendo il mouse sopra l'etichetta metrica.</span><span class="sxs-lookup"><span data-stu-id="a794e-118">Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="a794e-119">Tieni presente che le metriche effettive visualizzate in un determinato report dipendono dal tipo di sessione peer-to-peer selezionata.</span><span class="sxs-lookup"><span data-stu-id="a794e-119">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected.</span></span> <span data-ttu-id="a794e-120">Una sessione audio/video segnalerà un set di metriche diverso rispetto a una sessione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="a794e-120">An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="a794e-121">È anche possibile tenere il mouse sopra il codice di risposta e le metriche degli ID diagnostici per ottenere una descrizione dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a794e-121">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="a794e-122">Filtri</span><span class="sxs-lookup"><span data-stu-id="a794e-122">Filters</span></span>

<span data-ttu-id="a794e-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a794e-123">None.</span></span> <span data-ttu-id="a794e-124">Non è possibile filtrare il report del dettaglio della sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="a794e-124">You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="a794e-125">Metriche delle informazioni sulla sessione</span><span class="sxs-lookup"><span data-stu-id="a794e-125">Session Information Metrics</span></span>

<span data-ttu-id="a794e-126">Nella tabella seguente sono elencate le informazioni fornite nel report Dettagli sessione peer-to-peer per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="a794e-126">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="a794e-127">Metriche delle informazioni sulla sessione</span><span class="sxs-lookup"><span data-stu-id="a794e-127">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a794e-128">Nome</span><span class="sxs-lookup"><span data-stu-id="a794e-128">Name</span></span></th>
<th><span data-ttu-id="a794e-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a794e-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a794e-130"><strong>FQDN del pool</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-130"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-131">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale coinvolto nella sessione.</span><span class="sxs-lookup"><span data-stu-id="a794e-131">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a794e-132"><strong>Invitare il tempo</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-132"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-133">Data e ora in cui l'invito alla sessione è stato inviato in origine.</span><span class="sxs-lookup"><span data-stu-id="a794e-133">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a794e-134"><strong>Tempo di risposta</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-134"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-135">Data e ora in cui è stata ricevuta l'accettazione dell'invito.</span><span class="sxs-lookup"><span data-stu-id="a794e-135">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a794e-136"><strong>Dall'utente</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-136"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-137">Indirizzo SIP dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="a794e-137">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a794e-138"><strong>Dall'agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-138"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-139">Software usato dall'endpoint dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="a794e-139">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a794e-140"><strong>È da utente interno</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-140"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-141">Indica se l'utente che ha avviato la sessione è stato connesso alla rete interna.</span><span class="sxs-lookup"><span data-stu-id="a794e-141">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a794e-142"><strong>Viene dall'utente integrato con il telefono da tavolo</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-142"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-143">Indica se l'endpoint usato dall'utente che ha avviato la sessione è integrato con il telefono desktop.</span><span class="sxs-lookup"><span data-stu-id="a794e-143">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a794e-144"><strong>Priorità della sessione</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-144"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-145">Priorità assegnata alla sessione.</span><span class="sxs-lookup"><span data-stu-id="a794e-145">Priority assigned to the session.</span></span> <span data-ttu-id="a794e-146">Le priorità valide sono: sconosciuto; Non urgente; Normale Urgente e di emergenza.</span><span class="sxs-lookup"><span data-stu-id="a794e-146">Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a794e-147"><strong>Codice di risposta</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-147"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-148">Codice di risposta SIP inviato quando la sessione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="a794e-148">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a794e-149"><strong>Front-end</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-149"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-150">Nome del server front-end usato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="a794e-150">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a794e-151"><strong>Tempo di acquisizione</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-151"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-152">Data e ora in cui sono state registrate le informazioni sulla sessione.</span><span class="sxs-lookup"><span data-stu-id="a794e-152">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a794e-153"><strong>Ora di fine</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-153"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-154">Data e ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="a794e-154">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a794e-155"><strong>All'utente</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-155"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-156">Indirizzo SIP dell'utente invitato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="a794e-156">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a794e-157"><strong>All'agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-157"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-158">Software usato dall'endpoint dell'utente invitato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="a794e-158">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a794e-159"><strong>È l'utente interno</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-159"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-160">Indica se l'utente invitato alla sessione è stato connesso alla rete interna.</span><span class="sxs-lookup"><span data-stu-id="a794e-160">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a794e-161"><strong>È l'utente integrato con il telefono da tavolo</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-161"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-162">Indica se l'endpoint usato dall'utente invitato alla sessione è integrato con il telefono desktop.</span><span class="sxs-lookup"><span data-stu-id="a794e-162">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a794e-163"><strong>Viene riprovata la sessione</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-163"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-164">Indica se la sessione è un tentativo di riprovare una sessione che non è riuscita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a794e-164">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a794e-165"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-165"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-166">Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</span><span class="sxs-lookup"><span data-stu-id="a794e-166">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="a794e-167">Posizionare il puntatore del mouse sul numero di ID per visualizzare informazioni aggiuntive su tale ID.</span><span class="sxs-lookup"><span data-stu-id="a794e-167">Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="a794e-168">Metriche per le modalità</span><span class="sxs-lookup"><span data-stu-id="a794e-168">Metrics for Modalities</span></span>

<span data-ttu-id="a794e-169">Nella tabella seguente sono elencate le informazioni fornite nel report Dettagli sessione peer-to-peer per ogni modalità di sessione.</span><span class="sxs-lookup"><span data-stu-id="a794e-169">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="a794e-170">Metriche per le modalità</span><span class="sxs-lookup"><span data-stu-id="a794e-170">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a794e-171">Nome</span><span class="sxs-lookup"><span data-stu-id="a794e-171">Name</span></span></th>
<th><span data-ttu-id="a794e-172">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="a794e-172">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a794e-173">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a794e-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a794e-174"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-174"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-175">No</span><span class="sxs-lookup"><span data-stu-id="a794e-175">No</span></span></p></td>
<td><p><span data-ttu-id="a794e-176">Modalità usate nella sessione.</span><span class="sxs-lookup"><span data-stu-id="a794e-176">Modalities used in the session.</span></span> <span data-ttu-id="a794e-177">Ad esempio, messaggistica istantanea (IM) o trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="a794e-177">For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a794e-178"><strong>Da messaggi utente</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-178"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-179">No</span><span class="sxs-lookup"><span data-stu-id="a794e-179">No</span></span></p></td>
<td><p><span data-ttu-id="a794e-180">Numero di messaggi inviati dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="a794e-180">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a794e-181"><strong>Per i messaggi degli utenti</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-181"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-182">No</span><span class="sxs-lookup"><span data-stu-id="a794e-182">No</span></span></p></td>
<td><p><span data-ttu-id="a794e-183">Numero di messaggi inviati dall'utente che è stato invitato a partecipare alla sessione.</span><span class="sxs-lookup"><span data-stu-id="a794e-183">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="a794e-184">Metriche per i report di diagnostica</span><span class="sxs-lookup"><span data-stu-id="a794e-184">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="a794e-185">Nella tabella seguente sono elencate le informazioni fornite nel report Dettagli sessione peer-to-peer per ogni report di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="a794e-185">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="a794e-186">Metriche per i report di diagnostica</span><span class="sxs-lookup"><span data-stu-id="a794e-186">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a794e-187">Nome</span><span class="sxs-lookup"><span data-stu-id="a794e-187">Name</span></span></th>
<th><span data-ttu-id="a794e-188">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="a794e-188">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a794e-189">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a794e-189">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a794e-190"><strong>Dettaglio</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-190"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-191">No</span><span class="sxs-lookup"><span data-stu-id="a794e-191">No</span></span></p></td>
<td><p><span data-ttu-id="a794e-192">Quando si fa clic su questo elemento, il report Mostra il rapporto di diagnostica per la sessione.</span><span class="sxs-lookup"><span data-stu-id="a794e-192">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a794e-193"><strong>Tempo di report</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-193"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-194">No</span><span class="sxs-lookup"><span data-stu-id="a794e-194">No</span></span></p></td>
<td><p><span data-ttu-id="a794e-195">Data e ora in cui il report è stato registrato.</span><span class="sxs-lookup"><span data-stu-id="a794e-195">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a794e-196"><strong>Richiesta</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-196"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-197">No</span><span class="sxs-lookup"><span data-stu-id="a794e-197">No</span></span></p></td>
<td><p><span data-ttu-id="a794e-198">Tipo di richiesta SIP.</span><span class="sxs-lookup"><span data-stu-id="a794e-198">SIP request type.</span></span> <span data-ttu-id="a794e-199">Ad esempio, invita o BYE.</span><span class="sxs-lookup"><span data-stu-id="a794e-199">For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a794e-200"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-200"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-201">No</span><span class="sxs-lookup"><span data-stu-id="a794e-201">No</span></span></p></td>
<td><p><span data-ttu-id="a794e-202">Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</span><span class="sxs-lookup"><span data-stu-id="a794e-202">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a794e-203"><strong>Tipo di contenuto</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-203"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-204">No</span><span class="sxs-lookup"><span data-stu-id="a794e-204">No</span></span></p></td>
<td><p><span data-ttu-id="a794e-205">Tipo di contenuto multimediale usato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="a794e-205">Type of media content used in the conference.</span></span> <span data-ttu-id="a794e-206">Ad esempio, un tipo di contenuto comune è Application/sdp.</span><span class="sxs-lookup"><span data-stu-id="a794e-206">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="a794e-207">Il protocollo SDP (Session Description Protocol) è un protocollo Internet standard usato per gli annunci di sessione, gli inviti alla sessione e altre forme di avvio delle sessioni multimediali.</span><span class="sxs-lookup"><span data-stu-id="a794e-207">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a794e-208"><strong>Segnalato da</strong></span><span class="sxs-lookup"><span data-stu-id="a794e-208"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="a794e-209">No</span><span class="sxs-lookup"><span data-stu-id="a794e-209">No</span></span></p></td>
<td><p><span data-ttu-id="a794e-210">Computer (ovvero client o server) che ha segnalato il problema.</span><span class="sxs-lookup"><span data-stu-id="a794e-210">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

