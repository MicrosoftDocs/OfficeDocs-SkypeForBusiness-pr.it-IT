---
title: 'Lync Server 2013: rapporto di diagnostica attività peer-to-peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53e47232a6345749f78f6136929209722a83621e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524393"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="7e70d-102">Rapporto di diagnostica attività peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e70d-102">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e70d-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7e70d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7e70d-104">Il Rapporto di diagnostica attività peer-to-peer fornisce informazioni sull'esito positivo o negativo delle sessioni di comunicazione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="7e70d-104">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="7e70d-105">Si noti che Microsoft Lync Server 2013 distingue diversi tipi di errore:</span><span class="sxs-lookup"><span data-stu-id="7e70d-105">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="7e70d-106">**Errore previsto**.</span><span class="sxs-lookup"><span data-stu-id="7e70d-106">**Expected failure**.</span></span> <span data-ttu-id="7e70d-107">Un errore previsto è in genere un errore solo nel senso più tecnico del termine.</span><span class="sxs-lookup"><span data-stu-id="7e70d-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="7e70d-108">Si supponga ad esempio di chiamare un utente, che però non è in ufficio e dunque non può rispondere al telefono.</span><span class="sxs-lookup"><span data-stu-id="7e70d-108">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="7e70d-109">Poiché la chiamata non ha ricevuto risposta, tecnicamente viene considerata un errore.</span><span class="sxs-lookup"><span data-stu-id="7e70d-109">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="7e70d-110">D'altra parte, si è verificato un errore atteso: Microsoft Lync Server 2013 non prevede di rispondere al telefono se non si è a disposizione per rispondere al telefono.</span><span class="sxs-lookup"><span data-stu-id="7e70d-110">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="7e70d-111">Analogamente, si verificherà un errore previsto se si tenta di inviare un messaggio istantaneo a un utente offline, oppure connesso a un telefono che non supporta la messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="7e70d-111">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="7e70d-112">**Errore imprevisto**.</span><span class="sxs-lookup"><span data-stu-id="7e70d-112">**Unexpected failure**.</span></span> <span data-ttu-id="7e70d-113">Un errore imprevisto è esattamente tale, ovvero un errore che, in determinate circostanze, non ci si aspetterebbe.</span><span class="sxs-lookup"><span data-stu-id="7e70d-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="7e70d-114">Si supponga, ad esempio, di chiamare qualcuno e che la persona sia disponibile per rispondere alla chiamata; Tuttavia, quando Lync Server 2013 tenta di instradare la chiamata alla segreteria telefonica, la chiamata ha esito negativo perché la connettività alla messaggistica unificata di Exchange è stata persa.</span><span class="sxs-lookup"><span data-stu-id="7e70d-114">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="7e70d-115">Questo è un errore imprevisto: si prevede che le chiamate possano sempre essere instradate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="7e70d-115">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="7e70d-116">Come regola generale, gli errori imprevisti sono guasti veri: sono problemi che probabilmente non possono essere risolti tramite l'educazione degli utenti o misure simili.</span><span class="sxs-lookup"><span data-stu-id="7e70d-116">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="7e70d-p104">Tenere presente che la somma delle metriche relative a esiti positivi, errori previsti ed errori imprevisti potrebbe non corrispondere al valore della metrica Totale sessioni. Ad esempio, nell'illustrazione precedente sono presenti i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e70d-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e70d-119">Operazioni riuscite</span><span class="sxs-lookup"><span data-stu-id="7e70d-119">Successes</span></span></th>
<th><span data-ttu-id="7e70d-120">Errori previsti</span><span class="sxs-lookup"><span data-stu-id="7e70d-120">Expected failures</span></span></th>
<th><span data-ttu-id="7e70d-121">Errori imprevisti</span><span class="sxs-lookup"><span data-stu-id="7e70d-121">Unexpected failures</span></span></th>
<th><span data-ttu-id="7e70d-122">Totale sessioni</span><span class="sxs-lookup"><span data-stu-id="7e70d-122">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e70d-123">2024</span><span class="sxs-lookup"><span data-stu-id="7e70d-123">2024</span></span></p></td>
<td><p><span data-ttu-id="7e70d-124">469</span><span class="sxs-lookup"><span data-stu-id="7e70d-124">469</span></span></p></td>
<td><p><span data-ttu-id="7e70d-125">16 </span><span class="sxs-lookup"><span data-stu-id="7e70d-125">16</span></span></p></td>
<td><p><span data-ttu-id="7e70d-126">2521</span><span class="sxs-lookup"><span data-stu-id="7e70d-126">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7e70d-127">Sommando 2024 + 469 + 16 si ottiene un totale di 2.509 sessioni, ma la colonna Totale sessioni mostra un totale di 2.521 sessioni.</span><span class="sxs-lookup"><span data-stu-id="7e70d-127">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="7e70d-128">Le 12 sessioni "mancanti" sono quelle che il sistema non è riuscito a classificare come riuscite o non riuscite.</span><span class="sxs-lookup"><span data-stu-id="7e70d-128">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="7e70d-129">A volte si verificherà il caso in cui un prodotto di terze parti introduce un nuovo codice diagnostico sconosciuto a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7e70d-129">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="7e70d-130">Quando ciò accade, le chiamate effettuate usando tale prodotto e contrassegnate da tale codice diagnostico non sempre possono essere correttamente classificate come un esito positivo, un errore previsto o un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="7e70d-130">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="7e70d-131">Accesso al Rapporto di diagnostica attività peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="7e70d-131">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="7e70d-132">Il rapporto di diagnostica peer-to-peer è accessibile dalla home page dei rapporti di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="7e70d-132">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="7e70d-133">È possibile accedere al [rapporto distribuzione errori in Lync Server 2013](lync-server-2013-failure-distribution-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e70d-133">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="7e70d-134">Quantità di errori imprevisti</span><span class="sxs-lookup"><span data-stu-id="7e70d-134">Unexpected failure volume</span></span>

  - <span data-ttu-id="7e70d-135">Expected failure volume</span><span class="sxs-lookup"><span data-stu-id="7e70d-135">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="7e70d-136">Uso ottimale del Rapporto di diagnostica attività peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="7e70d-136">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="7e70d-p107">È possibile filtrare il Rapporto di diagnostica attività peer-to-peer in vari modi, ma per impostazione predefinita le impostazioni di filtro sono nascoste. Per visualizzare le opzioni di filtro disponibili, fare clic sul pulsante Mostra/Nascondi parametri nell'angolo superiore destro della finestra del rapporto. Fatto questo, le opzioni di filtro saranno disponibili per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="7e70d-p107">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view. To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window. Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7e70d-140">Filtri</span><span class="sxs-lookup"><span data-stu-id="7e70d-140">Filters</span></span>

<span data-ttu-id="7e70d-p108">I filtri consentono di ottenere un set di dati più mirato o di visualizzare i dati restituiti in diversi modi. Il rapporto di diagnostica attività peer-to-peer ad esempio consente di filtrare i dati in base ad aspetti come la modalità della sessione, ovvero messaggistica istantanea, trasferimento di file o condivisione applicazioni. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In tal caso, le chiamate vengono raggruppate in base all'ora, al giorno, alla settimana o al mese.</span><span class="sxs-lookup"><span data-stu-id="7e70d-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing). You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="7e70d-145">Nella tabella seguente sono riportati i filtri che è possibile utilizzare con il rapporto di diagnostica attività peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="7e70d-145">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="7e70d-146">Filtri per il rapporto di diagnostica attività peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="7e70d-146">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e70d-147">Nome</span><span class="sxs-lookup"><span data-stu-id="7e70d-147">Name</span></span></th>
<th><span data-ttu-id="7e70d-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e70d-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e70d-149"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="7e70d-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7e70d-p109">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="7e70d-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7e70d-152">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="7e70d-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7e70d-p110">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="7e70d-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7e70d-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7e70d-155">7/7/2012</span></span></p>
<p><span data-ttu-id="7e70d-156">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="7e70d-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7e70d-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7e70d-157">7/3/2012</span></span></p>
<p><span data-ttu-id="7e70d-158">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="7e70d-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e70d-159"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="7e70d-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7e70d-p111">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="7e70d-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7e70d-162">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="7e70d-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7e70d-p112">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="7e70d-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7e70d-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7e70d-165">7/7/2012</span></span></p>
<p><span data-ttu-id="7e70d-166">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="7e70d-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7e70d-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7e70d-167">7/3/2012</span></span></p>
<p><span data-ttu-id="7e70d-168">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="7e70d-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e70d-169"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="7e70d-169"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="7e70d-p113">Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e70d-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7e70d-172">Orario (è possibile visualizzare un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="7e70d-172">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7e70d-173">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="7e70d-173">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7e70d-174">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="7e70d-174">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7e70d-175">Mensile (è possibile visualizzare un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="7e70d-175">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="7e70d-p114">Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo giornaliero con data di inizio 07/07/2012 e data di fine 28/02/2012, verranno visualizzati i dati per i giorni da 07/08/2012 ore 00.00 a 07/09/2012 ore 00:00 (per un totale di 31 giorni).</span><span class="sxs-lookup"><span data-stu-id="7e70d-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e70d-178"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="7e70d-178"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="7e70d-p115">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su <strong>[Tutto]</strong> per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="7e70d-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e70d-182"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="7e70d-182"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="7e70d-p116">Indica il tipo di attività di comunicazione verificatasi. Selezionare una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e70d-p116">Indicates the type of communication activity that took place. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7e70d-185">Tutti</span><span class="sxs-lookup"><span data-stu-id="7e70d-185">[All]</span></span></p></li>
<li><p><span data-ttu-id="7e70d-186">Messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="7e70d-186">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="7e70d-187">Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="7e70d-187">File transfer</span></span></p></li>
<li><p><span data-ttu-id="7e70d-188">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="7e70d-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="7e70d-189">Audio</span><span class="sxs-lookup"><span data-stu-id="7e70d-189">Audio</span></span></p></li>
<li><p><span data-ttu-id="7e70d-190">Video</span><span class="sxs-lookup"><span data-stu-id="7e70d-190">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="7e70d-191">Metrica (per modalità)</span><span class="sxs-lookup"><span data-stu-id="7e70d-191">Metrics (per modality)</span></span>

<span data-ttu-id="7e70d-192">Nella tabella seguente sono riportate le informazioni fornite nel rapporto di diagnostica attività peer-to-peer per le singole modalità.</span><span class="sxs-lookup"><span data-stu-id="7e70d-192">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="7e70d-193">Metrica (per modalità)</span><span class="sxs-lookup"><span data-stu-id="7e70d-193">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e70d-194">Nome</span><span class="sxs-lookup"><span data-stu-id="7e70d-194">Name</span></span></th>
<th><span data-ttu-id="7e70d-195">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="7e70d-195">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7e70d-196">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e70d-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e70d-197"><strong>Success volume</strong></span><span class="sxs-lookup"><span data-stu-id="7e70d-197"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7e70d-198">No</span><span class="sxs-lookup"><span data-stu-id="7e70d-198">No</span></span></p></td>
<td><p><span data-ttu-id="7e70d-199">Numero totale di sessioni peer-to-peer con esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e70d-199">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e70d-200"><strong>Success percentage</strong></span><span class="sxs-lookup"><span data-stu-id="7e70d-200"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7e70d-201">No</span><span class="sxs-lookup"><span data-stu-id="7e70d-201">No</span></span></p></td>
<td><p><span data-ttu-id="7e70d-p117">Percentuale di sessioni peer-to-peer completate con problemi significativi. Viene calcolata dividendo il valore Success volume per il valore Total sessions.</span><span class="sxs-lookup"><span data-stu-id="7e70d-p117">Percentage of peer-to-peer sessions that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e70d-204"><strong>Expected failure volume</strong></span><span class="sxs-lookup"><span data-stu-id="7e70d-204"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7e70d-205">No</span><span class="sxs-lookup"><span data-stu-id="7e70d-205">No</span></span></p></td>
<td><p><span data-ttu-id="7e70d-206">Numero totale di sessioni in cui &quot; &quot; si è verificato un errore previsto.</span><span class="sxs-lookup"><span data-stu-id="7e70d-206">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="7e70d-p118">Per errore previsto si intende un errore che è previsto che si verifichi. Se ad esempio un utente imposta il proprio stato su Non disturbare, è previsto che qualsiasi chiamata effettuata a tale utente non riesca.</span><span class="sxs-lookup"><span data-stu-id="7e70d-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e70d-209"><strong>Expected failure percentage</strong></span><span class="sxs-lookup"><span data-stu-id="7e70d-209"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7e70d-210">No</span><span class="sxs-lookup"><span data-stu-id="7e70d-210">No</span></span></p></td>
<td><p><span data-ttu-id="7e70d-p119">Percentuale di sessioni peer-to-peer in cui si è verificato un errore previsto. Viene calcolata dividendo il valore Expected failure volume per il valore Total sessions.</span><span class="sxs-lookup"><span data-stu-id="7e70d-p119">Percentage of peer-to-peer sessions that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e70d-213"><strong>Unexpected failure volume</strong></span><span class="sxs-lookup"><span data-stu-id="7e70d-213"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7e70d-214">No</span><span class="sxs-lookup"><span data-stu-id="7e70d-214">No</span></span></p></td>
<td><p><span data-ttu-id="7e70d-215">Numero totale di sessioni in cui &quot; si è verificato un errore imprevisto &quot; .</span><span class="sxs-lookup"><span data-stu-id="7e70d-215">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="7e70d-p120">Per errore non previsto si intende un errore che si verifica in un sistema che sembrerebbe altrimenti integro. Ad esempio, una chiamata non dovrebbe essere terminata se il chiamante la mette in attesa. Se questo errore si verifica, viene contrassegnato come imprevisto.</span><span class="sxs-lookup"><span data-stu-id="7e70d-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e70d-219"><strong>Unexpected failure percentage</strong></span><span class="sxs-lookup"><span data-stu-id="7e70d-219"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7e70d-220">No</span><span class="sxs-lookup"><span data-stu-id="7e70d-220">No</span></span></p></td>
<td><p><span data-ttu-id="7e70d-p121">Percentuale di sessioni peer-to-peer in cui si è verificato un errore imprevisto. Viene calcolata dividendo il valore Unexpected failure volume per il valore Total sessions.</span><span class="sxs-lookup"><span data-stu-id="7e70d-p121">Percentage of peer-to-peer sessions that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e70d-223"><strong>Total sessions</strong></span><span class="sxs-lookup"><span data-stu-id="7e70d-223"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7e70d-224">No</span><span class="sxs-lookup"><span data-stu-id="7e70d-224">No</span></span></p></td>
<td><p><span data-ttu-id="7e70d-225">Numero totale di sessioni, comprendente le sessioni con esito positivo, le sessioni con esito negativo (per errori sia previsti che imprevisti) e le sessioni senza categoria.</span><span class="sxs-lookup"><span data-stu-id="7e70d-225">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

