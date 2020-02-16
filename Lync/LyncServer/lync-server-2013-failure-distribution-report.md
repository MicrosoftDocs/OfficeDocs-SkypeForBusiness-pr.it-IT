---
title: 'Lync Server 2013: rapporto distribuzione errori'
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
ms.openlocfilehash: 291097d645884d4c5146b48a69e5355db71e2193
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="e06a5-102">Rapporto distribuzione errori in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e06a5-102">Failure Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e06a5-103">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="e06a5-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="e06a5-104">Il Rapporto distribuzione errori classifica le sessioni non riuscite nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="e06a5-104">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="e06a5-105">Motivi diagnostica principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-105">Top diagnostic reasons</span></span>

  - <span data-ttu-id="e06a5-106">Modalità principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-106">Top modalities</span></span>

  - <span data-ttu-id="e06a5-107">Pool principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-107">Top pools</span></span>

  - <span data-ttu-id="e06a5-108">Origini principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-108">Top sources</span></span>

  - <span data-ttu-id="e06a5-109">Componenti principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-109">Top components</span></span>

  - <span data-ttu-id="e06a5-110">Utenti di origine principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-110">Top from users</span></span>

  - <span data-ttu-id="e06a5-111">Utenti di destinazione principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-111">Top to users</span></span>

  - <span data-ttu-id="e06a5-112">Agenti utenti di origine principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-112">Top from user agents</span></span>

<span data-ttu-id="e06a5-p101">Queste categorie possono essere utilizzate per localizzare con precisione il problema e, in alcuni casi, stabilirne la causa. Si supponga ad esempio di aver registrato 242 sessioni audio/video non riuscite in un giorno specifico. Analizzando il Rapporto distribuzione errori, si può riscontrare che 237 di queste sessioni non riuscite hanno avuto luogo nel pool Dublin. Questa informazione rappresenta un punto di partenza valido nell'individuazione e nella diagnosi delle cause che sono alla base degli errori. Facendo clic sul pool Dublin nella categoria **Pool principali**, verrà visualizzato un Rapporto distribuzione errori per il pool specifico. A questo punto è possibile iniziare ad analizzare le cause dei problemi che hanno interessato il pool Dublin.</span><span class="sxs-lookup"><span data-stu-id="e06a5-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="e06a5-119">Visualizzazione del Rapporto distribuzione errori</span><span class="sxs-lookup"><span data-stu-id="e06a5-119">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="e06a5-120">È possibile accedere al Rapporto distribuzione errori da uno qualsiasi dei rapporti seguenti facendo clic sulla metrica **Errore previsto** o **Errore imprevisto**:</span><span class="sxs-lookup"><span data-stu-id="e06a5-120">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="e06a5-121">Rapporto errori principali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e06a5-121">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="e06a5-122">Rapporto di diagnostica conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e06a5-122">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="e06a5-123">Rapporto di diagnostica attività peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e06a5-123">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="e06a5-124">Nel rapporto distribuzione errori, è possibile fare clic su una delle metriche seguenti per visualizzare il [rapporto Elenco errori in Lync Server 2013](lync-server-2013-failure-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="e06a5-124">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="e06a5-125">Motivi diagnostica principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="e06a5-125">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="e06a5-126">Modalità principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="e06a5-126">Top modalities (sessions)</span></span>

  - <span data-ttu-id="e06a5-127">Pool principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="e06a5-127">Top pools (sessions)</span></span>

  - <span data-ttu-id="e06a5-128">Origini principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="e06a5-128">Top sources (sessions)</span></span>

  - <span data-ttu-id="e06a5-129">Componenti principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="e06a5-129">Top components (sessions)</span></span>

  - <span data-ttu-id="e06a5-130">Utenti di origine principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="e06a5-130">Top from users (sessions)</span></span>

  - <span data-ttu-id="e06a5-131">Utenti di destinazione principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="e06a5-131">Top to users (sessions)</span></span>

  - <span data-ttu-id="e06a5-132">Agenti utenti di origine principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="e06a5-132">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="e06a5-133">Uso del Rapporto distribuzione errori</span><span class="sxs-lookup"><span data-stu-id="e06a5-133">Using the Failure Distribution Report</span></span>

<span data-ttu-id="e06a5-p102">A seconda delle dimensioni del monitor e della risoluzione dello schermo, è possibile che alcuni dei dati mostrati nel Rapporto distribuzione errori vengano troncati quando vengono visualizzati. Ciò accade soprattutto nel caso di metriche come gli agenti utente che possono avere etichette particolarmente lunghe. Ad esempio un agente utente con un nome come "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" può essere visualizzato solo parzialmente:</span><span class="sxs-lookup"><span data-stu-id="e06a5-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="e06a5-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="e06a5-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="e06a5-138">Fortunatamente, è possibile visualizzare l'intera etichetta semplicemente posizionando il mouse sul valore troncato.</span><span class="sxs-lookup"><span data-stu-id="e06a5-138">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="e06a5-p103">Una metrica interessante in base alla quale è possibile filtrare usando il Rapporto distribuzione errori è ID diagnostica. Se lo stesso valore di ID diagnostica viene fuori in altri rapporti, è possibile applicare il filtro in base all'ID nel Rapporto distribuzione errori e ottenere informazioni estremamente dettagliate su dove e con che frequenza l'ID è stato segnalato durante una sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="e06a5-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e06a5-141">Filtri</span><span class="sxs-lookup"><span data-stu-id="e06a5-141">Filters</span></span>

<span data-ttu-id="e06a5-p104">I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Il Rapporto distribuzione errori ad esempio consente di applicare filtri in base a elementi come il tipo di attività (sessione peer-to-peer o di conferenza) o l'ID diagnostica associato a ogni sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="e06a5-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="e06a5-144">Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto distribuzione errori.</span><span class="sxs-lookup"><span data-stu-id="e06a5-144">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="e06a5-145">Filtri del Rapporto distribuzione errori</span><span class="sxs-lookup"><span data-stu-id="e06a5-145">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e06a5-146">Name</span><span class="sxs-lookup"><span data-stu-id="e06a5-146">Name</span></span></th>
<th><span data-ttu-id="e06a5-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e06a5-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-148"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-p105">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="e06a5-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e06a5-151">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="e06a5-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e06a5-p106">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="e06a5-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e06a5-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e06a5-154">7/7/2012</span></span></p>
<p><span data-ttu-id="e06a5-155">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="e06a5-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e06a5-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e06a5-156">7/3/2012</span></span></p>
<p><span data-ttu-id="e06a5-157">Le settimane iniziano sempre con il lunedì e terminano con la domenica.</span><span class="sxs-lookup"><span data-stu-id="e06a5-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e06a5-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-p107">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="e06a5-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e06a5-161">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="e06a5-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e06a5-p108">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="e06a5-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e06a5-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e06a5-164">7/7/2012</span></span></p>
<p><span data-ttu-id="e06a5-165">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="e06a5-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e06a5-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e06a5-166">7/3/2012</span></span></p>
<p><span data-ttu-id="e06a5-167">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="e06a5-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-168"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-p109">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su <strong>[Tutti]</strong> per visualizzare dati per tutti i pool. Questo elenco a discesa viene popolato automaticamente in base ai record del database.</span><span class="sxs-lookup"><span data-stu-id="e06a5-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e06a5-172"><strong>Tipo di attività</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-172"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-p110">Tipo di attività in base al quale applicare il filtro. Selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e06a5-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e06a5-175">Tutti</span><span class="sxs-lookup"><span data-stu-id="e06a5-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="e06a5-176">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="e06a5-176">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="e06a5-177">Conferenza</span><span class="sxs-lookup"><span data-stu-id="e06a5-177">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-178"><strong>Categoria sessione</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-178"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-p111">Indica l'esito dell'attività in questione. Selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e06a5-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e06a5-181">Tutti</span><span class="sxs-lookup"><span data-stu-id="e06a5-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="e06a5-182">Success</span><span class="sxs-lookup"><span data-stu-id="e06a5-182">Success</span></span></p></li>
<li><p><span data-ttu-id="e06a5-183">Errore previsto</span><span class="sxs-lookup"><span data-stu-id="e06a5-183">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="e06a5-184">Errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="e06a5-184">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="e06a5-185">Un &quot;errore&quot; previsto è un errore che dovrebbe verificarsi.</span><span class="sxs-lookup"><span data-stu-id="e06a5-185">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="e06a5-186">Se ad esempio un utente ha impostato il proprio stato su Non disturbare, è previsto che le chiamate effettuate per tale utente abbiano esito negativo.</span><span class="sxs-lookup"><span data-stu-id="e06a5-186">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="e06a5-187">Un &quot;errore&quot; imprevisto è un errore che si verifica in un sistema altrimenti integro.</span><span class="sxs-lookup"><span data-stu-id="e06a5-187">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="e06a5-188">Una chiamata ad esempio non dovrebbe interrompersi quando il chiamante viene messo in attesa.</span><span class="sxs-lookup"><span data-stu-id="e06a5-188">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="e06a5-189">Se la chiamata si interrompe, l'evento verrà contrassegnato come errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="e06a5-189">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e06a5-190"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-190"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-p113">Identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi. Le intestazioni di diagnostica sono facoltative (è possibile che in alcune sessioni SIP non siano incluse queste intestazioni) e gli ID diagnostica sono spesso indicati solo per sessioni in cui si sono verificati problemi di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="e06a5-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="e06a5-193">Metrica dei motivi di diagnostica principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-193">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="e06a5-194">Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base all'ID diagnostica segnalato con maggiore frequenza.</span><span class="sxs-lookup"><span data-stu-id="e06a5-194">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="e06a5-195">Metrica dei motivi di diagnostica principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-195">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e06a5-196">Name</span><span class="sxs-lookup"><span data-stu-id="e06a5-196">Name</span></span></th>
<th><span data-ttu-id="e06a5-197">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="e06a5-197">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e06a5-198">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e06a5-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-199"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-199"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-200">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-200">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-p114">Classificazione relativa di sessioni non riuscite in base agli ID diagnostica. L'ID diagnostica è un identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="e06a5-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e06a5-203"><strong>Motivi diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-203"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-204">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-204">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-205">ID diagnostica generato in una sessione.</span><span class="sxs-lookup"><span data-stu-id="e06a5-205">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-206"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-206"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-207">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-207">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-208">Numero totale di sessioni non riuscite in cui è stato generato l'ID diagnostica specificato.</span><span class="sxs-lookup"><span data-stu-id="e06a5-208">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="e06a5-209">Metrica delle modalità principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-209">Metrics for Top Modalities</span></span>

<span data-ttu-id="e06a5-210">Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base alle modalità di sessione in cui si sono verificati più errori.</span><span class="sxs-lookup"><span data-stu-id="e06a5-210">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="e06a5-211">Metrica delle modalità principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-211">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e06a5-212">Name</span><span class="sxs-lookup"><span data-stu-id="e06a5-212">Name</span></span></th>
<th><span data-ttu-id="e06a5-213">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="e06a5-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e06a5-214">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e06a5-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-215"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-215"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-216">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-216">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-217">Classificazione relativa di sessioni non riuscite in base al tipo di sessione, ad esempio un trasferimento file peer-to-peer o di conferenza audio/video.</span><span class="sxs-lookup"><span data-stu-id="e06a5-217">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e06a5-218"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-218"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-219">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-219">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-220">Tipo di sessione.</span><span class="sxs-lookup"><span data-stu-id="e06a5-220">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-221"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-221"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-222">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-222">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-223">Numero totale di sessioni non riuscite con la modalità specificata.</span><span class="sxs-lookup"><span data-stu-id="e06a5-223">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="e06a5-224">Metrica dei pool principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-224">Metrics for Top Pools</span></span>

<span data-ttu-id="e06a5-225">Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base ai pool in cui si sono verificati più errori.</span><span class="sxs-lookup"><span data-stu-id="e06a5-225">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="e06a5-226">Metrica dei pool principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-226">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e06a5-227">Name</span><span class="sxs-lookup"><span data-stu-id="e06a5-227">Name</span></span></th>
<th><span data-ttu-id="e06a5-228">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="e06a5-228">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e06a5-229">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e06a5-229">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-230"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-230"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-231">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-231">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-232">Classificazione relativa di sessioni non riuscite in base al pool di registrazione o al server perimetrale in cui è stata eseguita la sessione.</span><span class="sxs-lookup"><span data-stu-id="e06a5-232">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e06a5-233"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-233"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-234">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-234">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-235">Nome del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="e06a5-235">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-236"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-236"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-237">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-237">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-238">Numero totale di sessioni non riuscite per pool di registrazione o server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="e06a5-238">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="e06a5-239">Metrica delle origini principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-239">Metrics for Top Sources</span></span>

<span data-ttu-id="e06a5-240">Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base ai computer in cui si sono verificati più errori.</span><span class="sxs-lookup"><span data-stu-id="e06a5-240">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="e06a5-241">Metrica delle origini principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-241">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e06a5-242">Name</span><span class="sxs-lookup"><span data-stu-id="e06a5-242">Name</span></span></th>
<th><span data-ttu-id="e06a5-243">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="e06a5-243">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e06a5-244">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e06a5-244">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-245"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-245"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-246">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-246">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-247">Classificazione relativa di sessioni non riuscite per computer.</span><span class="sxs-lookup"><span data-stu-id="e06a5-247">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e06a5-248"><strong>Origini</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-248"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-249">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-249">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-250">Nome del computer associato alla sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="e06a5-250">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-251"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-251"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-252">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-252">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-253">Numero totale di sessioni non riuscite per computer.</span><span class="sxs-lookup"><span data-stu-id="e06a5-253">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="e06a5-254">Metrica dei componenti principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-254">Metrics for Top Components</span></span>

<span data-ttu-id="e06a5-255">Nella tabella seguente sono elencate le informazioni fornite nel rapporto distribuzione errori in base ai componenti di Microsoft Lync Server 2010 che hanno riscontrato la maggior parte dei guasti.</span><span class="sxs-lookup"><span data-stu-id="e06a5-255">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="e06a5-256">Metrica dei componenti principali</span><span class="sxs-lookup"><span data-stu-id="e06a5-256">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e06a5-257">Name</span><span class="sxs-lookup"><span data-stu-id="e06a5-257">Name</span></span></th>
<th><span data-ttu-id="e06a5-258">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="e06a5-258">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e06a5-259">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e06a5-259">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-260"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-260"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-261">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-261">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-262">Classificazione relativa di sessioni non riuscite in base al componente di Lync Server 2010 (ad esempio, ExumRouting, GroupChat o MediationServer).</span><span class="sxs-lookup"><span data-stu-id="e06a5-262">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e06a5-263"><strong>Componenti</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-263"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-264">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-264">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-265">Nome del componente associato alla sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="e06a5-265">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-266"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-266"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-267">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-267">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-268">Numero totale di sessioni non riuscite per componente.</span><span class="sxs-lookup"><span data-stu-id="e06a5-268">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="e06a5-269">Metrica degli utenti di origine delle chiamate</span><span class="sxs-lookup"><span data-stu-id="e06a5-269">Metrics for Top From Users</span></span>

<span data-ttu-id="e06a5-270">Nella tabella seguente vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base agli utenti per cui si sono verificati più errori quando hanno tentato di chiamare un altro utente (utenti "Da").</span><span class="sxs-lookup"><span data-stu-id="e06a5-270">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="e06a5-271">Metrica degli utenti di origine delle chiamate</span><span class="sxs-lookup"><span data-stu-id="e06a5-271">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e06a5-272">Name</span><span class="sxs-lookup"><span data-stu-id="e06a5-272">Name</span></span></th>
<th><span data-ttu-id="e06a5-273">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="e06a5-273">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e06a5-274">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e06a5-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-275"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-275"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-276">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-276">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-277">Classificazione relativa di sessioni non riuscite in base all'utente invitato a partecipare alla sessione.</span><span class="sxs-lookup"><span data-stu-id="e06a5-277">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e06a5-278"><strong>Da utenti</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-278"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-279">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-279">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-280">Indirizzo SIP dell'utente invitato a partecipare alla sessione.</span><span class="sxs-lookup"><span data-stu-id="e06a5-280">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-281"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-281"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-282">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-282">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-283">Numero totale di sessioni non riuscite per utente.</span><span class="sxs-lookup"><span data-stu-id="e06a5-283">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="e06a5-284">Metrica degli utenti destinatari delle chiamate</span><span class="sxs-lookup"><span data-stu-id="e06a5-284">Metrics for Top To Users</span></span>

<span data-ttu-id="e06a5-285">Nella tabella seguente vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base agli utenti per cui si sono verificati più errori quando un altro utente ha tentato di chiamarli (utenti "A").</span><span class="sxs-lookup"><span data-stu-id="e06a5-285">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e06a5-286">Name</span><span class="sxs-lookup"><span data-stu-id="e06a5-286">Name</span></span></th>
<th><span data-ttu-id="e06a5-287">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="e06a5-287">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e06a5-288">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e06a5-288">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-289"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-289"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-290">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-290">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-291">Classificazione relativa di sessioni non riuscite in base all'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="e06a5-291">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e06a5-292"><strong>A utenti</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-292"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-293">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-293">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-294">Indirizzo SIP dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="e06a5-294">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-295"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-295"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-296">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-296">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-297">Numero totale di sessioni non riuscite per utente.</span><span class="sxs-lookup"><span data-stu-id="e06a5-297">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="e06a5-298">Metrica degli agenti utente</span><span class="sxs-lookup"><span data-stu-id="e06a5-298">Metrics for Top User Agents</span></span>

<span data-ttu-id="e06a5-299">Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base al software endpoint in cui si sono verificati più errori.</span><span class="sxs-lookup"><span data-stu-id="e06a5-299">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="e06a5-300">Metrica degli agenti utente</span><span class="sxs-lookup"><span data-stu-id="e06a5-300">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e06a5-301">Name</span><span class="sxs-lookup"><span data-stu-id="e06a5-301">Name</span></span></th>
<th><span data-ttu-id="e06a5-302">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="e06a5-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e06a5-303">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e06a5-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-304"><strong>Classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-304"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-305">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-305">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-p115">Classificazione relativa di sessioni non riuscite in base all'agente utente (software) associato alla sessione, ad esempio RTCC/4.0.0.0 Routing in ingresso/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="e06a5-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e06a5-308"><strong>Da agenti utente</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-308"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-309">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-309">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-310">Nome dell'agente utente coinvolto nella sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="e06a5-310">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e06a5-311"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="e06a5-311"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e06a5-312">No</span><span class="sxs-lookup"><span data-stu-id="e06a5-312">No</span></span></p></td>
<td><p><span data-ttu-id="e06a5-313">Numero totale di sessioni non riuscite per agente.</span><span class="sxs-lookup"><span data-stu-id="e06a5-313">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

