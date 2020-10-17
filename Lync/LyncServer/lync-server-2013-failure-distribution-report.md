---
title: 'Lync Server 2013: rapporto distribuzione errori'
description: 'Lync Server 2013: rapporto distribuzione errori.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5a87f779f87d6b7002fa108f1969c33739eed9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564732"
---
# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="837d6-103">Rapporto distribuzione errori in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="837d6-103">Failure Distribution Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="837d6-104">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="837d6-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="837d6-105">Il Rapporto distribuzione errori classifica le sessioni non riuscite nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="837d6-105">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="837d6-106">Motivi diagnostica principali</span><span class="sxs-lookup"><span data-stu-id="837d6-106">Top diagnostic reasons</span></span>

  - <span data-ttu-id="837d6-107">Modalità principali</span><span class="sxs-lookup"><span data-stu-id="837d6-107">Top modalities</span></span>

  - <span data-ttu-id="837d6-108">Pool principali</span><span class="sxs-lookup"><span data-stu-id="837d6-108">Top pools</span></span>

  - <span data-ttu-id="837d6-109">Origini principali</span><span class="sxs-lookup"><span data-stu-id="837d6-109">Top sources</span></span>

  - <span data-ttu-id="837d6-110">Componenti principali</span><span class="sxs-lookup"><span data-stu-id="837d6-110">Top components</span></span>

  - <span data-ttu-id="837d6-111">Utenti di origine principali</span><span class="sxs-lookup"><span data-stu-id="837d6-111">Top from users</span></span>

  - <span data-ttu-id="837d6-112">Utenti di destinazione principali</span><span class="sxs-lookup"><span data-stu-id="837d6-112">Top to users</span></span>

  - <span data-ttu-id="837d6-113">Agenti utenti di origine principali</span><span class="sxs-lookup"><span data-stu-id="837d6-113">Top from user agents</span></span>

<span data-ttu-id="837d6-p101">Queste categorie possono essere utilizzate per localizzare con precisione il problema e, in alcuni casi, stabilirne la causa. Si supponga ad esempio di aver registrato 242 sessioni audio/video non riuscite in un giorno specifico. Analizzando il Rapporto distribuzione errori, si può riscontrare che 237 di queste sessioni non riuscite hanno avuto luogo nel pool Dublin. Questa informazione rappresenta un punto di partenza valido nell'individuazione e nella diagnosi delle cause che sono alla base degli errori. Facendo clic sul pool Dublin nella categoria **Pool principali**, verrà visualizzato un Rapporto distribuzione errori per il pool specifico. A questo punto è possibile iniziare ad analizzare le cause dei problemi che hanno interessato il pool Dublin.</span><span class="sxs-lookup"><span data-stu-id="837d6-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="837d6-120">Visualizzazione del Rapporto distribuzione errori</span><span class="sxs-lookup"><span data-stu-id="837d6-120">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="837d6-121">È possibile accedere al Rapporto distribuzione errori da uno qualsiasi dei rapporti seguenti facendo clic sulla metrica **Errore previsto** o **Errore imprevisto**:</span><span class="sxs-lookup"><span data-stu-id="837d6-121">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="837d6-122">Rapporto errori principali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="837d6-122">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="837d6-123">Rapporto di diagnostica conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="837d6-123">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="837d6-124">Rapporto di diagnostica attività peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="837d6-124">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="837d6-125">Nel rapporto distribuzione errori, è possibile fare clic su una delle metriche seguenti per visualizzare il [rapporto Elenco errori in Lync Server 2013](lync-server-2013-failure-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="837d6-125">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="837d6-126">Motivi diagnostica principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="837d6-126">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="837d6-127">Modalità principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="837d6-127">Top modalities (sessions)</span></span>

  - <span data-ttu-id="837d6-128">Pool principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="837d6-128">Top pools (sessions)</span></span>

  - <span data-ttu-id="837d6-129">Origini principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="837d6-129">Top sources (sessions)</span></span>

  - <span data-ttu-id="837d6-130">Componenti principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="837d6-130">Top components (sessions)</span></span>

  - <span data-ttu-id="837d6-131">Utenti di origine principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="837d6-131">Top from users (sessions)</span></span>

  - <span data-ttu-id="837d6-132">Utenti di destinazione principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="837d6-132">Top to users (sessions)</span></span>

  - <span data-ttu-id="837d6-133">Agenti utenti di origine principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="837d6-133">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="837d6-134">Uso del Rapporto distribuzione errori</span><span class="sxs-lookup"><span data-stu-id="837d6-134">Using the Failure Distribution Report</span></span>

<span data-ttu-id="837d6-p102">A seconda delle dimensioni del monitor e della risoluzione dello schermo, è possibile che alcuni dei dati mostrati nel Rapporto distribuzione errori vengano troncati quando vengono visualizzati. Ciò accade soprattutto nel caso di metriche come gli agenti utente che possono avere etichette particolarmente lunghe. Ad esempio un agente utente con un nome come "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" può essere visualizzato solo parzialmente:</span><span class="sxs-lookup"><span data-stu-id="837d6-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="837d6-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="837d6-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="837d6-139">Fortunatamente, è possibile visualizzare l'intera etichetta semplicemente posizionando il mouse sul valore troncato.</span><span class="sxs-lookup"><span data-stu-id="837d6-139">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="837d6-p103">Una metrica interessante in base alla quale è possibile filtrare usando il Rapporto distribuzione errori è ID diagnostica. Se lo stesso valore di ID diagnostica viene fuori in altri rapporti, è possibile applicare il filtro in base all'ID nel Rapporto distribuzione errori e ottenere informazioni estremamente dettagliate su dove e con che frequenza l'ID è stato segnalato durante una sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="837d6-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="837d6-142">Filtri</span><span class="sxs-lookup"><span data-stu-id="837d6-142">Filters</span></span>

<span data-ttu-id="837d6-p104">I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Il Rapporto distribuzione errori ad esempio consente di applicare filtri in base a elementi come il tipo di attività (sessione peer-to-peer o di conferenza) o l'ID diagnostica associato a ogni sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="837d6-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="837d6-145">Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto distribuzione errori.</span><span class="sxs-lookup"><span data-stu-id="837d6-145">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="837d6-146">Filtri del Rapporto distribuzione errori</span><span class="sxs-lookup"><span data-stu-id="837d6-146">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="837d6-147">Nome</span><span class="sxs-lookup"><span data-stu-id="837d6-147">Name</span></span></th>
<th><span data-ttu-id="837d6-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="837d6-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="837d6-149"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-p105">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="837d6-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="837d6-152">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="837d6-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="837d6-p106">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="837d6-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="837d6-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="837d6-155">7/7/2012</span></span></p>
<p><span data-ttu-id="837d6-156">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="837d6-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="837d6-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="837d6-157">7/3/2012</span></span></p>
<p><span data-ttu-id="837d6-158">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="837d6-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="837d6-159"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-p107">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="837d6-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="837d6-162">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="837d6-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="837d6-p108">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="837d6-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="837d6-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="837d6-165">7/7/2012</span></span></p>
<p><span data-ttu-id="837d6-166">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="837d6-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="837d6-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="837d6-167">7/3/2012</span></span></p>
<p><span data-ttu-id="837d6-168">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="837d6-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="837d6-169"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-169"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-p109">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su <strong>[Tutti]</strong> per visualizzare dati per tutti i pool. Questo elenco a discesa viene popolato automaticamente in base ai record del database.</span><span class="sxs-lookup"><span data-stu-id="837d6-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="837d6-173"><strong>Tipo di attività</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-173"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-p110">Tipo di attività in base al quale applicare il filtro. Selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="837d6-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="837d6-176">Tutti</span><span class="sxs-lookup"><span data-stu-id="837d6-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="837d6-177">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="837d6-177">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="837d6-178">Conferenza</span><span class="sxs-lookup"><span data-stu-id="837d6-178">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="837d6-179"><strong>Categoria sessione</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-179"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-p111">Indica l'esito dell'attività in questione. Selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="837d6-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="837d6-182">Tutti</span><span class="sxs-lookup"><span data-stu-id="837d6-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="837d6-183">Completato</span><span class="sxs-lookup"><span data-stu-id="837d6-183">Success</span></span></p></li>
<li><p><span data-ttu-id="837d6-184">Errore previsto</span><span class="sxs-lookup"><span data-stu-id="837d6-184">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="837d6-185">Errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="837d6-185">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="837d6-186">Un &quot; errore previsto &quot; è un errore che dovrebbe verificarsi.</span><span class="sxs-lookup"><span data-stu-id="837d6-186">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="837d6-187">Se ad esempio un utente ha impostato il proprio stato su Non disturbare, è previsto che le chiamate effettuate per tale utente abbiano esito negativo.</span><span class="sxs-lookup"><span data-stu-id="837d6-187">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="837d6-188">Un &quot; errore imprevisto &quot; è un errore che si verifica in un sistema altrimenti integro.</span><span class="sxs-lookup"><span data-stu-id="837d6-188">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="837d6-189">Una chiamata ad esempio non dovrebbe interrompersi quando il chiamante viene messo in attesa.</span><span class="sxs-lookup"><span data-stu-id="837d6-189">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="837d6-190">Se la chiamata si interrompe, l'evento verrà contrassegnato come errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="837d6-190">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="837d6-191"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-p113">Identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi. Le intestazioni di diagnostica sono facoltative (è possibile che in alcune sessioni SIP non siano incluse queste intestazioni) e gli ID diagnostica sono spesso indicati solo per sessioni in cui si sono verificati problemi di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="837d6-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="837d6-194">Metrica dei motivi di diagnostica principali</span><span class="sxs-lookup"><span data-stu-id="837d6-194">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="837d6-195">Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base all'ID diagnostica segnalato con maggiore frequenza.</span><span class="sxs-lookup"><span data-stu-id="837d6-195">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="837d6-196">Metrica dei motivi di diagnostica principali</span><span class="sxs-lookup"><span data-stu-id="837d6-196">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="837d6-197">Nome</span><span class="sxs-lookup"><span data-stu-id="837d6-197">Name</span></span></th>
<th><span data-ttu-id="837d6-198">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="837d6-198">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="837d6-199">Descrizione</span><span class="sxs-lookup"><span data-stu-id="837d6-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="837d6-200"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-200"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-201">No</span><span class="sxs-lookup"><span data-stu-id="837d6-201">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-p114">Classificazione relativa di sessioni non riuscite in base agli ID diagnostica. L'ID diagnostica è un identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="837d6-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="837d6-204"><strong>Motivi diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-204"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-205">No</span><span class="sxs-lookup"><span data-stu-id="837d6-205">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-206">ID diagnostica generato in una sessione.</span><span class="sxs-lookup"><span data-stu-id="837d6-206">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="837d6-207"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-207"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-208">No</span><span class="sxs-lookup"><span data-stu-id="837d6-208">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-209">Numero totale di sessioni non riuscite in cui è stato generato l'ID diagnostica specificato.</span><span class="sxs-lookup"><span data-stu-id="837d6-209">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="837d6-210">Metrica delle modalità principali</span><span class="sxs-lookup"><span data-stu-id="837d6-210">Metrics for Top Modalities</span></span>

<span data-ttu-id="837d6-211">Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base alle modalità di sessione in cui si sono verificati più errori.</span><span class="sxs-lookup"><span data-stu-id="837d6-211">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="837d6-212">Metrica delle modalità principali</span><span class="sxs-lookup"><span data-stu-id="837d6-212">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="837d6-213">Nome</span><span class="sxs-lookup"><span data-stu-id="837d6-213">Name</span></span></th>
<th><span data-ttu-id="837d6-214">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="837d6-214">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="837d6-215">Descrizione</span><span class="sxs-lookup"><span data-stu-id="837d6-215">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="837d6-216"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-216"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-217">No</span><span class="sxs-lookup"><span data-stu-id="837d6-217">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-218">Classificazione relativa di sessioni non riuscite in base al tipo di sessione, ad esempio un trasferimento file peer-to-peer o di conferenza audio/video.</span><span class="sxs-lookup"><span data-stu-id="837d6-218">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="837d6-219"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-219"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-220">No</span><span class="sxs-lookup"><span data-stu-id="837d6-220">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-221">Tipo di sessione.</span><span class="sxs-lookup"><span data-stu-id="837d6-221">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="837d6-222"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-222"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-223">No</span><span class="sxs-lookup"><span data-stu-id="837d6-223">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-224">Numero totale di sessioni non riuscite con la modalità specificata.</span><span class="sxs-lookup"><span data-stu-id="837d6-224">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="837d6-225">Metrica dei pool principali</span><span class="sxs-lookup"><span data-stu-id="837d6-225">Metrics for Top Pools</span></span>

<span data-ttu-id="837d6-226">Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base ai pool in cui si sono verificati più errori.</span><span class="sxs-lookup"><span data-stu-id="837d6-226">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="837d6-227">Metrica dei pool principali</span><span class="sxs-lookup"><span data-stu-id="837d6-227">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="837d6-228">Nome</span><span class="sxs-lookup"><span data-stu-id="837d6-228">Name</span></span></th>
<th><span data-ttu-id="837d6-229">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="837d6-229">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="837d6-230">Descrizione</span><span class="sxs-lookup"><span data-stu-id="837d6-230">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="837d6-231"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-231"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-232">No</span><span class="sxs-lookup"><span data-stu-id="837d6-232">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-233">Classificazione relativa di sessioni non riuscite in base al pool di registrazione o al server perimetrale in cui è stata eseguita la sessione.</span><span class="sxs-lookup"><span data-stu-id="837d6-233">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="837d6-234"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-234"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-235">No</span><span class="sxs-lookup"><span data-stu-id="837d6-235">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-236">Nome del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="837d6-236">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="837d6-237"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-237"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-238">No</span><span class="sxs-lookup"><span data-stu-id="837d6-238">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-239">Numero totale di sessioni non riuscite per pool di registrazione o server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="837d6-239">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="837d6-240">Metrica delle origini principali</span><span class="sxs-lookup"><span data-stu-id="837d6-240">Metrics for Top Sources</span></span>

<span data-ttu-id="837d6-241">Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base ai computer in cui si sono verificati più errori.</span><span class="sxs-lookup"><span data-stu-id="837d6-241">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="837d6-242">Metrica delle origini principali</span><span class="sxs-lookup"><span data-stu-id="837d6-242">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="837d6-243">Nome</span><span class="sxs-lookup"><span data-stu-id="837d6-243">Name</span></span></th>
<th><span data-ttu-id="837d6-244">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="837d6-244">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="837d6-245">Descrizione</span><span class="sxs-lookup"><span data-stu-id="837d6-245">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="837d6-246"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-246"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-247">No</span><span class="sxs-lookup"><span data-stu-id="837d6-247">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-248">Classificazione relativa di sessioni non riuscite per computer.</span><span class="sxs-lookup"><span data-stu-id="837d6-248">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="837d6-249"><strong>Origini</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-249"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-250">No</span><span class="sxs-lookup"><span data-stu-id="837d6-250">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-251">Nome del computer associato alla sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="837d6-251">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="837d6-252"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-252"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-253">No</span><span class="sxs-lookup"><span data-stu-id="837d6-253">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-254">Numero totale di sessioni non riuscite per computer.</span><span class="sxs-lookup"><span data-stu-id="837d6-254">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="837d6-255">Metrica dei componenti principali</span><span class="sxs-lookup"><span data-stu-id="837d6-255">Metrics for Top Components</span></span>

<span data-ttu-id="837d6-256">Nella tabella seguente sono elencate le informazioni fornite nel rapporto distribuzione errori in base ai componenti di Microsoft Lync Server 2010 che hanno riscontrato la maggior parte dei guasti.</span><span class="sxs-lookup"><span data-stu-id="837d6-256">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="837d6-257">Metrica dei componenti principali</span><span class="sxs-lookup"><span data-stu-id="837d6-257">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="837d6-258">Nome</span><span class="sxs-lookup"><span data-stu-id="837d6-258">Name</span></span></th>
<th><span data-ttu-id="837d6-259">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="837d6-259">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="837d6-260">Descrizione</span><span class="sxs-lookup"><span data-stu-id="837d6-260">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="837d6-261"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-261"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-262">No</span><span class="sxs-lookup"><span data-stu-id="837d6-262">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-263">Classificazione relativa di sessioni non riuscite in base al componente di Lync Server 2010 (ad esempio, ExumRouting, GroupChat o MediationServer).</span><span class="sxs-lookup"><span data-stu-id="837d6-263">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="837d6-264"><strong>Componenti</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-264"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-265">No</span><span class="sxs-lookup"><span data-stu-id="837d6-265">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-266">Nome del componente associato alla sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="837d6-266">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="837d6-267"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-267"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-268">No</span><span class="sxs-lookup"><span data-stu-id="837d6-268">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-269">Numero totale di sessioni non riuscite per componente.</span><span class="sxs-lookup"><span data-stu-id="837d6-269">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="837d6-270">Metrica degli utenti di origine delle chiamate</span><span class="sxs-lookup"><span data-stu-id="837d6-270">Metrics for Top From Users</span></span>

<span data-ttu-id="837d6-271">Nella tabella seguente vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base agli utenti per cui si sono verificati più errori quando hanno tentato di chiamare un altro utente (utenti "Da").</span><span class="sxs-lookup"><span data-stu-id="837d6-271">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="837d6-272">Metrica degli utenti di origine delle chiamate</span><span class="sxs-lookup"><span data-stu-id="837d6-272">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="837d6-273">Nome</span><span class="sxs-lookup"><span data-stu-id="837d6-273">Name</span></span></th>
<th><span data-ttu-id="837d6-274">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="837d6-274">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="837d6-275">Descrizione</span><span class="sxs-lookup"><span data-stu-id="837d6-275">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="837d6-276"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-276"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-277">No</span><span class="sxs-lookup"><span data-stu-id="837d6-277">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-278">Classificazione relativa di sessioni non riuscite in base all'utente invitato a partecipare alla sessione.</span><span class="sxs-lookup"><span data-stu-id="837d6-278">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="837d6-279"><strong>Da utenti</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-279"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-280">No</span><span class="sxs-lookup"><span data-stu-id="837d6-280">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-281">Indirizzo SIP dell'utente invitato a partecipare alla sessione.</span><span class="sxs-lookup"><span data-stu-id="837d6-281">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="837d6-282"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-282"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-283">No</span><span class="sxs-lookup"><span data-stu-id="837d6-283">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-284">Numero totale di sessioni non riuscite per utente.</span><span class="sxs-lookup"><span data-stu-id="837d6-284">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="837d6-285">Metrica degli utenti destinatari delle chiamate</span><span class="sxs-lookup"><span data-stu-id="837d6-285">Metrics for Top To Users</span></span>

<span data-ttu-id="837d6-286">Nella tabella seguente vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base agli utenti per cui si sono verificati più errori quando un altro utente ha tentato di chiamarli (utenti "A").</span><span class="sxs-lookup"><span data-stu-id="837d6-286">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="837d6-287">Nome</span><span class="sxs-lookup"><span data-stu-id="837d6-287">Name</span></span></th>
<th><span data-ttu-id="837d6-288">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="837d6-288">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="837d6-289">Descrizione</span><span class="sxs-lookup"><span data-stu-id="837d6-289">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="837d6-290"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-290"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-291">No</span><span class="sxs-lookup"><span data-stu-id="837d6-291">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-292">Classificazione relativa di sessioni non riuscite in base all'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="837d6-292">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="837d6-293"><strong>A utenti</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-293"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-294">No</span><span class="sxs-lookup"><span data-stu-id="837d6-294">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-295">Indirizzo SIP dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="837d6-295">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="837d6-296"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-296"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-297">No</span><span class="sxs-lookup"><span data-stu-id="837d6-297">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-298">Numero totale di sessioni non riuscite per utente.</span><span class="sxs-lookup"><span data-stu-id="837d6-298">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="837d6-299">Metrica degli agenti utente</span><span class="sxs-lookup"><span data-stu-id="837d6-299">Metrics for Top User Agents</span></span>

<span data-ttu-id="837d6-300">Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base al software endpoint in cui si sono verificati più errori.</span><span class="sxs-lookup"><span data-stu-id="837d6-300">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="837d6-301">Metrica degli agenti utente</span><span class="sxs-lookup"><span data-stu-id="837d6-301">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="837d6-302">Nome</span><span class="sxs-lookup"><span data-stu-id="837d6-302">Name</span></span></th>
<th><span data-ttu-id="837d6-303">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="837d6-303">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="837d6-304">Descrizione</span><span class="sxs-lookup"><span data-stu-id="837d6-304">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="837d6-305"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-305"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-306">No</span><span class="sxs-lookup"><span data-stu-id="837d6-306">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-p115">Classificazione relativa di sessioni non riuscite in base all'agente utente (software) associato alla sessione, ad esempio RTCC/4.0.0.0 Routing in ingresso/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="837d6-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="837d6-309"><strong>Da agenti utente</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-309"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-310">No</span><span class="sxs-lookup"><span data-stu-id="837d6-310">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-311">Nome dell'agente utente coinvolto nella sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="837d6-311">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="837d6-312"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="837d6-312"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="837d6-313">No</span><span class="sxs-lookup"><span data-stu-id="837d6-313">No</span></span></p></td>
<td><p><span data-ttu-id="837d6-314">Numero totale di sessioni non riuscite per agente.</span><span class="sxs-lookup"><span data-stu-id="837d6-314">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

