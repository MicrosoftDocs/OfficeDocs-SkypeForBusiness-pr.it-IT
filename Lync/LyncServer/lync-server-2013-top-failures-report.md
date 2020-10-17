---
title: 'Lync Server 2013: rapporto errori principali'
description: 'Lync Server 2013: rapporto errori principali.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 768c9a99916dece9eb76877b0cd65b057697ff95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561272"
---
# <a name="top-failures-report-in-lync-server-2013"></a><span data-ttu-id="648b5-103">Rapporto errori principali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="648b5-103">Top Failures Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="648b5-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="648b5-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="648b5-p101">Nel Rapporto errori principali vengono esaminati gli errori rilevati più di frequente con la relativa tendenza nel tempo. Gli errori sono basati su una combinazione delle due metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="648b5-p101">The Top Failures Report provides a look at the most-commonly reported failures and their trends over time. Failures are based on a combination of the following two metrics:</span></span>

  - <span data-ttu-id="648b5-p102">**ID diagnostica**. Identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi relativi alle chiamate.</span><span class="sxs-lookup"><span data-stu-id="648b5-p102">**Diagnostic ID**. Unique identifier (in the form of an ms-diagnostics header) that is attached to a SIP message. Diagnostic IDs provide information useful in troubleshooting call-related problems.</span></span>

  - <span data-ttu-id="648b5-110">**Codice di risposta**.</span><span class="sxs-lookup"><span data-stu-id="648b5-110">**Response code**.</span></span> <span data-ttu-id="648b5-111">I codici di risposta vengono utilizzati nelle sessioni di comunicazione SIP per rispondere alle richieste SIP.</span><span class="sxs-lookup"><span data-stu-id="648b5-111">Response codes are used in SIP communication sessions to respond to SIP requests.</span></span> <span data-ttu-id="648b5-112">Ad esempio, si supponga che Ken invii la richiesta di invito a Pilar Ackerman (ovvero, supponiamo che Ken remario chiami Pilar Ackerman).</span><span class="sxs-lookup"><span data-stu-id="648b5-112">For example, suppose Ken sends the INVITE request to Pilar Ackerman (that is, suppose Ken Myer calls Pilar Ackerman).</span></span> <span data-ttu-id="648b5-113">Se le risposte di Pilar, il suo telefono invierà il codice di risposta 200 (OK), lasciando che il telefono di Ken sappia che Pilar ha risposto.</span><span class="sxs-lookup"><span data-stu-id="648b5-113">If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered.</span></span> <span data-ttu-id="648b5-114">Il rapporto errori principali include solo codici di risposta inviati in risposta a un errore di chiamata; Lync Server non tiene conto di tutti i codici di risposta rilasciati durante il corso di una chiamata.</span><span class="sxs-lookup"><span data-stu-id="648b5-114">The Top Failures Report only includes response codes that were sent in response to a call failure; Lync Server does not keep track of all the response codes issued during the course of a call.</span></span>

<span data-ttu-id="648b5-115">Le informazioni vengono registrate nel rapporto non solo per il numero totale di sessioni in cui si è verificato un errore, ma anche per il numero totale di utenti che hanno subito l'errore.</span><span class="sxs-lookup"><span data-stu-id="648b5-115">Information is reported not only for the total number of sessions where a failure occurred but also for the total number of users who were impacted by the failure.</span></span>

<div>

## <a name="accessing-the-top-failures-report"></a><span data-ttu-id="648b5-116">Accesso al Rapporto errori principali</span><span class="sxs-lookup"><span data-stu-id="648b5-116">Accessing the Top Failures Report</span></span>

<span data-ttu-id="648b5-117">È possibile accedere al Rapporto errori principali dalla home page Relazioni monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="648b5-117">The Top Failures Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="648b5-118">Se si fa clic sulla metrica sessioni segnalate, verrà visualizzato il [rapporto distribuzione errori in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span><span class="sxs-lookup"><span data-stu-id="648b5-118">Clicking the Reported sessions metric will take you to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a><span data-ttu-id="648b5-119">Utilizzo ottimale del Rapporto errori principali</span><span class="sxs-lookup"><span data-stu-id="648b5-119">Making the Best Use of the Top Failures Report</span></span>

<span data-ttu-id="648b5-p105">Il Rapporto errori principali è insolito per un aspetto: consente di applicare un filtro che può includere fino a 5 ID diagnostica alla volta, laddove in genere può includere un solo elemento, ad esempio un indirizzo SIP utente alla volta. Per applicare un filtro in base a più ID diagnostica, è sufficiente immettere i singoli ID nella casella apposita separandoli tramite virgole. Se si vuole, è possibile lasciare uno spazio bianco dopo ogni virgola, come nell'esempio:</span><span class="sxs-lookup"><span data-stu-id="648b5-p105">The Top Failures Report is unusual in one regard: it allows you to filter on as many as 5 diagnostic IDs at once. (Typically you can only filter on one item – such as one user SIP address – at a time.) To filter on multiple diagnostic IDs, simply enter each ID in the Diagnostic IDs box, separating the IDs by using commas. (If you want to, you can leave a blank space after each comma.) For example:</span></span>

<span data-ttu-id="648b5-123">1011, 2412, 1033, 52116, 1008</span><span class="sxs-lookup"><span data-stu-id="648b5-123">1011, 2412, 1033, 52116, 1008</span></span>

<span data-ttu-id="648b5-124">Così facendo verranno visualizzate solo le chiamate non riuscite che hanno riportato almeno uno dei cinque ID diagnostica indicati.</span><span class="sxs-lookup"><span data-stu-id="648b5-124">Do that, and only failed calls that reported at least one of those five diagnostic IDs will be displayed.</span></span>

<span data-ttu-id="648b5-p106">Se si tiene il mouse posizionato su un codice di risposta, viene visualizzata una descrizione comando che ne spiega il significato. Se ad esempio si tiene il mouse posizionato sul codice di risposta 486, verrà visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="648b5-p106">If you hold your mouse over a Response code you'll see a tooltip that tells you what the Response code in question means. For example, if you hold the mouse over the Response code 486 you'll see this message:</span></span>

<span data-ttu-id="648b5-127">Non disponibile qui.</span><span class="sxs-lookup"><span data-stu-id="648b5-127">Busy Here.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="648b5-128">Filtri</span><span class="sxs-lookup"><span data-stu-id="648b5-128">Filters</span></span>

<span data-ttu-id="648b5-p107">I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Il Rapporto errori principali ad esempio consente di filtrare i dati restituiti in base a fattori come il tipo di attività, ovvero sessione peer-to-peer o di conferenza, oppure in base al codice di risposta SIP associato alla sessione in cui si è verificato l'errore. È inoltre possibile scegliere come raggruppare i dati. In questo caso, gli utilizzi vengono raggruppati per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="648b5-p107">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Top Failures Report enables you to filter the returned data based on such things as the activity type (peer-to-peer session or conferencing session) or by the SIP response code that accompanied the failed session. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="648b5-133">Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto errori principali.</span><span class="sxs-lookup"><span data-stu-id="648b5-133">The following table lists the filters that you can use with the Top Failures Report.</span></span>

### <a name="top-failures-report-filters"></a><span data-ttu-id="648b5-134">Filtri del Rapporto errori principali</span><span class="sxs-lookup"><span data-stu-id="648b5-134">Top Failures Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="648b5-135">Nome</span><span class="sxs-lookup"><span data-stu-id="648b5-135">Name</span></span></th>
<th><span data-ttu-id="648b5-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="648b5-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="648b5-137"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="648b5-137"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="648b5-p108">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="648b5-p108">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="648b5-140">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="648b5-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="648b5-p109">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="648b5-p109">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="648b5-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="648b5-143">7/7/2012</span></span></p>
<p><span data-ttu-id="648b5-144">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="648b5-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="648b5-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="648b5-145">7/3/2012</span></span></p>
<p><span data-ttu-id="648b5-146">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="648b5-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648b5-147"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="648b5-147"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="648b5-p110">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="648b5-p110">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="648b5-150">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="648b5-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="648b5-p111">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="648b5-p111">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="648b5-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="648b5-153">7/7/2012</span></span></p>
<p><span data-ttu-id="648b5-154">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="648b5-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="648b5-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="648b5-155">7/3/2012</span></span></p>
<p><span data-ttu-id="648b5-156">Le settimane vengono calcolate sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="648b5-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648b5-157"><strong>Tipo di attività</strong></span><span class="sxs-lookup"><span data-stu-id="648b5-157"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="648b5-p112">Tipo di attività. Selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="648b5-p112">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="648b5-160">Tutti</span><span class="sxs-lookup"><span data-stu-id="648b5-160">[All]</span></span></p></li>
<li><p><span data-ttu-id="648b5-161">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="648b5-161">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="648b5-162">Conferenza</span><span class="sxs-lookup"><span data-stu-id="648b5-162">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648b5-163"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="648b5-163"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="648b5-164">L'unica opzione disponibile attualmente è <strong>[Tutto]</strong>.</span><span class="sxs-lookup"><span data-stu-id="648b5-164">At this time the only option available is <strong>[All]</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648b5-165"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="648b5-165"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="648b5-p113">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su <strong>[Tutto]</strong> per visualizzare i dati relativi a tutti i pool. Questo elenco a discesa viene popolato automaticamente in base ai record del database.</span><span class="sxs-lookup"><span data-stu-id="648b5-p113">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648b5-169"><strong>Categoria</strong></span><span class="sxs-lookup"><span data-stu-id="648b5-169"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="648b5-p114">Tipo di errore. Selezionare uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="648b5-p114">Type of failure experienced. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="648b5-172">Errore sia previsto che imprevisto</span><span class="sxs-lookup"><span data-stu-id="648b5-172">Both expected and unexpected failure</span></span></p></li>
<li><p><span data-ttu-id="648b5-173">Errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="648b5-173">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="648b5-174">Un &quot; errore previsto &quot; è un errore che dovrebbe verificarsi.</span><span class="sxs-lookup"><span data-stu-id="648b5-174">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="648b5-175">Se ad esempio un utente ha impostato il proprio stato su Non disturbare, è previsto che le chiamate effettuate per tale utente abbiano esito negativo.</span><span class="sxs-lookup"><span data-stu-id="648b5-175">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="648b5-176">Un &quot; errore imprevisto &quot; è un errore che si verifica in un sistema altrimenti integro.</span><span class="sxs-lookup"><span data-stu-id="648b5-176">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="648b5-177">Una chiamata ad esempio non dovrebbe interrompersi quando il chiamante viene messo in attesa.</span><span class="sxs-lookup"><span data-stu-id="648b5-177">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="648b5-178">Se la chiamata si interrompe, l'evento verrà contrassegnato come errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="648b5-178">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648b5-179"><strong>Codice di risposta</strong></span><span class="sxs-lookup"><span data-stu-id="648b5-179"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="648b5-p116">Codice di risposta SIP inviato quando si è verificato l'errore di conferenza. Immettere l'intero codice di risposta, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="648b5-p116">SIP response code sent when the conference failed. Enter the entire response code For example:</span></span></p>
<p><span data-ttu-id="648b5-182">400</span><span class="sxs-lookup"><span data-stu-id="648b5-182">400</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648b5-183"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="648b5-183"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="648b5-p117">Identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi. Le intestazioni di diagnostica sono facoltative (è possibile che in alcune sessioni SIP non siano incluse queste intestazioni) e gli ID diagnostica sono spesso indicati solo per sessioni in cui si sono verificati problemi di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="648b5-p117">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="648b5-186">Metriche</span><span class="sxs-lookup"><span data-stu-id="648b5-186">Metrics</span></span>

<span data-ttu-id="648b5-187">Nella tabella seguente vengono elencate le informazioni fornite nel Rapporto errori principali.</span><span class="sxs-lookup"><span data-stu-id="648b5-187">The following table lists the information provided in the Top Failures Report.</span></span>

### <a name="top-failures-report-metrics"></a><span data-ttu-id="648b5-188">Metrica del Rapporto errori principali</span><span class="sxs-lookup"><span data-stu-id="648b5-188">Top Failures Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="648b5-189">Nome</span><span class="sxs-lookup"><span data-stu-id="648b5-189">Name</span></span></th>
<th><span data-ttu-id="648b5-190">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="648b5-190">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="648b5-191">Descrizione</span><span class="sxs-lookup"><span data-stu-id="648b5-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="648b5-192"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="648b5-192"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="648b5-193">Sì</span><span class="sxs-lookup"><span data-stu-id="648b5-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="648b5-194">Classificazione relativa basata sul numero di sessioni segnalate.</span><span class="sxs-lookup"><span data-stu-id="648b5-194">Relative rank based on the number of reported sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648b5-195"><strong>Sessioni segnalate</strong></span><span class="sxs-lookup"><span data-stu-id="648b5-195"><strong>Reported sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="648b5-196">Sì</span><span class="sxs-lookup"><span data-stu-id="648b5-196">Yes</span></span></p></td>
<td><p><span data-ttu-id="648b5-197">Numero totale di sessioni non riuscite in base all'ID diagnostica e al codice di risposta SIP.</span><span class="sxs-lookup"><span data-stu-id="648b5-197">Total number of failed sessions based on diagnostic ID and SIP response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648b5-198"><strong>Utenti interessati</strong></span><span class="sxs-lookup"><span data-stu-id="648b5-198"><strong>Users impacted</strong></span></span></p></td>
<td><p><span data-ttu-id="648b5-199">Sì</span><span class="sxs-lookup"><span data-stu-id="648b5-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="648b5-200">Numero totale di utenti interessati dalla sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="648b5-200">Total number of users affected by the failed session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648b5-201"><strong>Informazioni sull'errore</strong></span><span class="sxs-lookup"><span data-stu-id="648b5-201"><strong>Failure information</strong></span></span></p></td>
<td><p><span data-ttu-id="648b5-202">No</span><span class="sxs-lookup"><span data-stu-id="648b5-202">No</span></span></p></td>
<td><p><span data-ttu-id="648b5-203">Informazioni dettagliate sull'errore, tra cui l'ID diagnostica, il codice di risposta SIP e la descrizione del motivo per cui la sessione ha avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="648b5-203">Detailed information about the failure, including diagnostic ID, SIP response code, and description of why the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648b5-204"><strong>Tendenza passato</strong></span><span class="sxs-lookup"><span data-stu-id="648b5-204"><strong>Trend in the past</strong></span></span></p></td>
<td><p><span data-ttu-id="648b5-205">No</span><span class="sxs-lookup"><span data-stu-id="648b5-205">No</span></span></p></td>
<td><p><span data-ttu-id="648b5-206">Rappresentazione grafica delle sessioni non riuscite nel tempo.</span><span class="sxs-lookup"><span data-stu-id="648b5-206">Graphs failed sessions over time.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

