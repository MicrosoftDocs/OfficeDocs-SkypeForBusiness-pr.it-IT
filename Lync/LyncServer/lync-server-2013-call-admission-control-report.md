---
title: 'Lync Server 2013: rapporto di controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46d61e01574945fe090d3fd9425133f9569bd111
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="c0bdf-102">Report di controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0bdf-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0bdf-103">_**Ultimo argomento modificato:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="c0bdf-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="c0bdf-104">Il Rapporto controllo di ammissione di chiamata fornisce informazioni sulle sessioni peer-to-peer e di conferenza sottoposte alle limitazioni imposte dal servizio Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="c0bdf-105">Il controllo di ammissione di chiamata, introdotto in Microsoft Lync Server 2010, consente agli amministratori di consentire (o non consentire) sessioni di comunicazione basate su vincoli di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="c0bdf-106">Gli amministratori possono ad esempio creare criteri che limitano la larghezza di banda disponibile per le chiamate vocali e video.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="c0bdf-107">Se il limite di larghezza di banda viene raggiunto, non è possibile avviare ulteriori chiamate vocali o video se prima non termina una delle chiamate in corso liberando le risorse di rete necessarie.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="c0bdf-108">Accesso al Rapporto controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="c0bdf-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="c0bdf-p102">È possibile accedere al Rapporto controllo di ammissione di chiamata dalla home page di Relazioni monitoraggio. Dal Rapporto controllo di ammissione di chiamata è possibile eseguire il drill-down nei report seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0bdf-p102">The Call Admission Control Report is accessed from the Monitoring Reports home page. From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="c0bdf-111">Rapporto Dettagli conferenza - Per accedere a questo rapporto, fare clic sulla metrica Dettagli in una sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="c0bdf-112">Rapporto Dettagli sessione peer-to-peer - Per accedere a questo rapporto, fare clic sulla metrica Dettagli in una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="c0bdf-113">Utilizzare al meglio il Rapporto controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="c0bdf-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="c0bdf-p103">Per visualizzare un elenco delle chiamate non riuscite per larghezza di banda insufficiente, selezionare Chiamate rifiutate a causa del controllo di ammissione di chiamata dall'elenco a discesa Categoria chiamata. La maggior parte delle chiamate restituite avrà probabilmente l'ID diagnostica 5:</span><span class="sxs-lookup"><span data-stu-id="c0bdf-p103">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list. Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="c0bdf-p104">Larghezza di banda insufficiente per stabilire la sessione. Tentare il reindirizzamento PSTN.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-p104">Insufficient bandwidth to establish session. Attempt PSTN re-route.</span></span>

<span data-ttu-id="c0bdf-118">Questo indica che le limitazioni imposte dal servizio Controllo di ammissione di chiamata hanno impedito l'esecuzione della chiamata nella rete VoIP.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c0bdf-119">Filtri</span><span class="sxs-lookup"><span data-stu-id="c0bdf-119">Filters</span></span>

<span data-ttu-id="c0bdf-p105">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il Rapporto controllo di ammissione di chiamata consente di filtrare le chiamate in base all'utente che le ha avviate o all'utente chiamato. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso le chiamate sono raggruppabili per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="c0bdf-124">Nella tabella seguente sono elencati i filtri applicabili al Rapporto controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="c0bdf-125">Filtri del Rapporto controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="c0bdf-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0bdf-126">Name</span><span class="sxs-lookup"><span data-stu-id="c0bdf-126">Name</span></span></th>
<th><span data-ttu-id="c0bdf-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0bdf-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0bdf-128"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-p106">Data/ora di inizio dell'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c0bdf-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c0bdf-131">17/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="c0bdf-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="c0bdf-p107">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="c0bdf-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c0bdf-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="c0bdf-134">7/17/12012</span></span></p>
<p><span data-ttu-id="c0bdf-135">Per visualizzare i dati in base alla settimana o al mese, immettere una data che rientra nella settimana o nel mese in base a cui deve essere effettuata la visualizzazione. Non è necessario immettere il primo giorno della settimana o del mese:</span><span class="sxs-lookup"><span data-stu-id="c0bdf-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c0bdf-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="c0bdf-136">7/13/2012</span></span></p>
<p><span data-ttu-id="c0bdf-137">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bdf-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-p108">Data/ora di fine dell'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c0bdf-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c0bdf-141">17/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="c0bdf-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="c0bdf-p109">Se non si specifica l'ora di fine, il rapporto termina automaticamente alla mezzanotte del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="c0bdf-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c0bdf-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="c0bdf-144">7/17/12012</span></span></p>
<p><span data-ttu-id="c0bdf-145">Per visualizzare i dati in base alla settimana o al mese, immettere una data che rientra nella settimana o nel mese in base a cui deve essere effettuata la visualizzazione. Non è necessario immettere il primo giorno della settimana o del mese:</span><span class="sxs-lookup"><span data-stu-id="c0bdf-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c0bdf-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="c0bdf-146">7/13/2012</span></span></p>
<p><span data-ttu-id="c0bdf-147">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bdf-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-p110">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su <strong>[Tutti]</strong> per visualizzare dati per tutti i pool. Questo elenco a discesa viene popolato automaticamente in base ai record del database.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bdf-152"><strong>Tipo di attività</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-p111">Selezionare una delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0bdf-p111">Type of activity. Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="c0bdf-155">Tutti</span><span class="sxs-lookup"><span data-stu-id="c0bdf-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="c0bdf-156">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="c0bdf-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="c0bdf-157">Conferenza</span><span class="sxs-lookup"><span data-stu-id="c0bdf-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bdf-158"><strong>Categoria chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-p112">Indica il motivo per cui è stato utilizzato il controllo di ammissione chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0bdf-p112">Indicates the reason that CAC was used for the call. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c0bdf-161">Tutti</span><span class="sxs-lookup"><span data-stu-id="c0bdf-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="c0bdf-162">Chiamate rifiutate a causa del controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="c0bdf-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="c0bdf-163">Chiamate reinstradate tramite PSTN a causa del controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="c0bdf-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="c0bdf-164">Metriche per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="c0bdf-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="c0bdf-165">Nella tabella seguente sono elencate le informazioni riportate nel Rapporto controllo di ammissione di chiamata per le sessioni peer-to-peer, ovvero che coinvolgono solo due partecipanti.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="c0bdf-166">Metriche per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="c0bdf-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0bdf-167">Name</span><span class="sxs-lookup"><span data-stu-id="c0bdf-167">Name</span></span></th>
<th><span data-ttu-id="c0bdf-168">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="c0bdf-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c0bdf-169">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0bdf-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0bdf-170"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-171">No</span><span class="sxs-lookup"><span data-stu-id="c0bdf-171">No</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-172">Se si fa clic su questa opzione, nel rapporto viene visualizzato un rapporto dettagliato sulla sessione peer-to-peer specificata.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bdf-173"><strong>Da utente</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-174">Sì</span><span class="sxs-lookup"><span data-stu-id="c0bdf-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-175">Indirizzo SIP dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bdf-176"><strong>A utente</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-177">Sì</span><span class="sxs-lookup"><span data-stu-id="c0bdf-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-178">Indirizzo SIP dell'utente che è stato invitato a partecipare alla sessione.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bdf-179"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-180">Sì</span><span class="sxs-lookup"><span data-stu-id="c0bdf-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-181">Modalità di comunicazione, ad esempio audio e video, utilizzate durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bdf-182"><strong>Ora invito</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-183">Sì</span><span class="sxs-lookup"><span data-stu-id="c0bdf-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-184">Date e ora in cui è stato inviato l'invito iniziale alla sessione alla persona indicata in Da utente.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bdf-185"><strong>Ora risposta</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-186">Sì</span><span class="sxs-lookup"><span data-stu-id="c0bdf-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-187">Data e ora in cui è stata ricevuta l'informazione che l'invito è stato accettato.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bdf-188"><strong>Ora fine</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-189">Sì</span><span class="sxs-lookup"><span data-stu-id="c0bdf-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-190">Data e ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bdf-191"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-192">Sì</span><span class="sxs-lookup"><span data-stu-id="c0bdf-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-p113">Identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi. Le intestazioni di diagnostica sono facoltative (è possibile che in alcune sessioni SIP non siano incluse queste intestazioni) e gli ID diagnostica sono spesso indicati solo per sessioni in cui si sono verificati problemi di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="c0bdf-195">Metriche per le sessioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="c0bdf-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="c0bdf-196">Nella tabella seguente sono elencate le informazioni riportate nel Rapporto di controllo di ammissione di chiamata per le sessioni di conferenza, ovvero che coinvolgono almeno tre partecipanti.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="c0bdf-197">Metriche per le sessioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="c0bdf-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0bdf-198">Name</span><span class="sxs-lookup"><span data-stu-id="c0bdf-198">Name</span></span></th>
<th><span data-ttu-id="c0bdf-199">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="c0bdf-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c0bdf-200">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0bdf-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0bdf-201"><strong>URI conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-202">Sì</span><span class="sxs-lookup"><span data-stu-id="c0bdf-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-p114">Identificatore univoco della conferenza. Se si fa clic su questa opzione, nel rapporto vengono visualizzati i singoli partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-p114">Unique identifier for the conference. When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bdf-205"><strong>Organizzatore</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-206">Sì</span><span class="sxs-lookup"><span data-stu-id="c0bdf-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-207">Indirizzo SIP dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bdf-208"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-209">Sì</span><span class="sxs-lookup"><span data-stu-id="c0bdf-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-210">Server perimetrale utilizzato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bdf-211"><strong>Ora inizio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-212">Sì</span><span class="sxs-lookup"><span data-stu-id="c0bdf-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-213">Data e ora di inizio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bdf-214"><strong>Ora fine</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-215">Sì</span><span class="sxs-lookup"><span data-stu-id="c0bdf-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-216">Data e ora di fine della conferenza.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="c0bdf-217">Metriche per i singoli partecipanti alla conferenza</span><span class="sxs-lookup"><span data-stu-id="c0bdf-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="c0bdf-218">Nella tabella seguente sono elencate le informazioni riportate nel Rapporto di controllo di ammissione di chiamata per i singoli partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="c0bdf-219">Metriche per i singoli partecipanti alla conferenza</span><span class="sxs-lookup"><span data-stu-id="c0bdf-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0bdf-220">Name</span><span class="sxs-lookup"><span data-stu-id="c0bdf-220">Name</span></span></th>
<th><span data-ttu-id="c0bdf-221">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="c0bdf-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c0bdf-222">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0bdf-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0bdf-223"><strong>Ruolo</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-224">No</span><span class="sxs-lookup"><span data-stu-id="c0bdf-224">No</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-225">Ruolo, ad esempio Relatore, ricoperto dal partecipante alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bdf-226"><strong>Partecipante</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-227">No</span><span class="sxs-lookup"><span data-stu-id="c0bdf-227">No</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-228">Indirizzo SIP del partecipante alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bdf-229"><strong>Connettività</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-230">No</span><span class="sxs-lookup"><span data-stu-id="c0bdf-230">No</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-231">Connettività di rete, solitamente Dall'interno o Dall'esterno, per il partecipante.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bdf-232"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-233">No</span><span class="sxs-lookup"><span data-stu-id="c0bdf-233">No</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-234">Tipo di conferenza, ad esempio audio/video.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bdf-235"><strong>Ora partecipazione</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-236">No</span><span class="sxs-lookup"><span data-stu-id="c0bdf-236">No</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-237">Data e ora in cui il partecipante si è unito alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bdf-238"><strong>Ora uscita</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-239">No</span><span class="sxs-lookup"><span data-stu-id="c0bdf-239">No</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-240">Data e ora in cui il partecipante è uscito dalla conferenza.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bdf-241"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="c0bdf-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bdf-242">No</span><span class="sxs-lookup"><span data-stu-id="c0bdf-242">No</span></span></p></td>
<td><p><span data-ttu-id="c0bdf-p115">Identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi. Le intestazioni di diagnostica sono facoltative (è possibile che in alcune sessioni SIP non siano incluse queste intestazioni) e gli ID diagnostica sono spesso indicati solo per sessioni in cui si sono verificati problemi di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="c0bdf-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

