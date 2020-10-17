---
title: 'Lync Server 2013: rapporto attività utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36001aaf38dc39d0bb4eb7524e41c616b0a1c160
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530233"
---
# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="ba2a6-102">Rapporto attività utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba2a6-102">User Activity Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba2a6-103">_**Ultimo argomento modificato:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="ba2a6-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="ba2a6-p101">Nel Rapporto attività utente viene fornito un elenco dettagliato delle sessioni peer-to-peer e di conferenza per ogni utente in riferimento a un periodo di tempo specifico. Diversamente da molti rapporti di monitoraggio, il Rapporto attività utente associa ogni chiamata al singolo utente. Ad esempio le sessioni peer-to-peer specificano gli URI SIP della persona che ha effettuato la chiamata (Da utente) e della persona che ha ricevuto la chiamata (A utente). Se si espandono le informazioni relative a una conferenza, è possibile visualizzare un elenco di tutti i partecipanti con l'indicazione del ruolo che hanno svolto nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-p101">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="ba2a6-p102">Spesso si fa riferimento al Rapporto attività utente come al rapporto "help desk", in quanto il rapporto viene spesso utilizzato dal personale dell'help desk per recuperare informazioni sulla sessione per un utente specifico. È possibile applicare un filtro in base alle chiamate effettuate o ricevute da un singolo utente semplicemente digitando l'URI SIP dell'utente nella casella Prefisso URI utente.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-p102">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="ba2a6-111">Se si esegue questa operazione, il rapporto attività utente restituirà informazioni su qualsiasi utente il cui URI SIP inizia con la stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-111">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="ba2a6-112">Ad esempio, se si digita **Ken** nella casella URI, il rapporto attività utente individuerà **Ken**. Myer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-112">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="ba2a6-113">Tuttavia, verranno individuati anche gli utenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba2a6-113">However, it will also locate these users:</span></span>

  - <span data-ttu-id="ba2a6-114">**ken**azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ba2a6-114">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="ba2a6-115">**ken**Burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ba2a6-115">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="ba2a6-116">**Ken**. Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ba2a6-116">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="ba2a6-117">**Ken**Nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ba2a6-117">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="ba2a6-118">Per assicurarsi che vengano restituite solo le informazioni per Ken, digitare l'URI completo (Ken.Myer@litwareinc.com) nella casella di ricerca o almeno un numero sufficiente di URI di Ken per distinguerlo in modo univoco dagli altri utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-118">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="ba2a6-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ba2a6-119">For example:</span></span>

<span data-ttu-id="ba2a6-120">Ken.my</span><span class="sxs-lookup"><span data-stu-id="ba2a6-120">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="ba2a6-121">Per accedere al Rapporto attività utente</span><span class="sxs-lookup"><span data-stu-id="ba2a6-121">To access the user activity report</span></span>

<span data-ttu-id="ba2a6-122">È possibile accedere al rapporto attività utente dalla Home page dei rapporti di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-122">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="ba2a6-123">È inoltre possibile raggiungere il rapporto attività utente facendo clic sulla metrica URI utente nel [rapporto inventario telefoni IP in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span><span class="sxs-lookup"><span data-stu-id="ba2a6-123">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="ba2a6-124">Nell'ambito del rapporto attività utente, facendo clic sull'URI conferenza (per una conferenza) viene utilizzato il report Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-124">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="ba2a6-125">Analogamente, fare clic sulla metrica Dettagli per una chiamata peer-to-peer consente di accedere al [rapporto Dettagli sessione peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="ba2a6-125">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="ba2a6-126">Utilizzo ottimale del rapporto attività utente</span><span class="sxs-lookup"><span data-stu-id="ba2a6-126">Making the best use of the user activity report</span></span>

<span data-ttu-id="ba2a6-127">Anche se nel rapporto attività utente sono presenti numerose informazioni valide, è possibile che le informazioni a volte siano difficili da individuare.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-127">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="ba2a6-128">Ad esempio, tutte le attività degli utenti che si verificano nell'organizzazione nel corso di un periodo di tempo specificato sono incluse nel rapporto attività utente. Questo significa che, sepolto, all'interno del report sono disponibili informazioni sugli utenti che hanno effettivamente utilizzato Microsoft Lync Server 2013 in qualche modo.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-128">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="ba2a6-129">Tecnicamente, è possibile che alcune attività dell'utente non vengano registrate: mentre Lync Server cerca di mantenere le informazioni su tutte le chiamate telefoniche, è possibile che sia stata eseguita una chiamata senza che le informazioni relative alla chiamata vengano scritte nel database.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-129">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="ba2a6-130">Lync Server è stato creato per fornire un'occhiata estremamente accurata ma non necessariamente perfetta per la modalità di utilizzo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-130">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="ba2a6-131">Il fatto che non vi sia alcuna garanzia che il 100% di tutte le chiamate vengano registrate spiega perché Lync Server Monitoring non deve essere utilizzato come sistema di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-131">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="ba2a6-p108">Un altro limite consiste nel fatto che il numero massimo di record visualizzabile in un rapporto di Relazioni monitoraggio è 1.000. Ciò significa che, a seconda della quantità di attività utente svolta e del periodo di tempo di riferimento, la query potrebbe non restituire tutti i dati effettivamente memorizzati nel database.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-p108">Second, a Monitoring Report report can only display, at most, 1,000 records. Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="ba2a6-134">Quali utenti hanno effettivamente usato il sistema in questo periodo di tempo?</span><span class="sxs-lookup"><span data-stu-id="ba2a6-134">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="ba2a6-135">Qual è stato l'utente più attivo in questo periodo di tempo?</span><span class="sxs-lookup"><span data-stu-id="ba2a6-135">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="ba2a6-136">Gli utenti che effettuano il numero maggiore di chiamate telefoniche sono anche quelli che partecipano alla maggior parte di sessioni di messaggistica istantanea?</span><span class="sxs-lookup"><span data-stu-id="ba2a6-136">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="ba2a6-137">Per rispondere a domande come queste, è possibile esportare i dati recuperati dai rapporti di monitoraggio in un foglio di calcolo di Excel.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-137">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="ba2a6-138">Successivamente si può utilizzare questo foglio di calcolo e/o un file di valori separati da virgole per analizzare i dati in modo analogo al Rapporto attività utenti.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-138">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="ba2a6-139">Si supponga ad esempio di avere esportato i dati di rapporto in Excel, quindi in un file di valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-139">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="ba2a6-140">A questo punto, è possibile importare i dati da. File CSV in Windows PowerShell utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ba2a6-140">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="ba2a6-141">Dopo che i dati sono stati importati, è possibile utilizzare semplici comandi di Windows PowerShell per rispondere alle proprie domande.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-141">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="ba2a6-142">Il comando seguente, ad esempio, restituisce un elenco di utenti univoci che in almeno una sessione sono stati gli utenti di "Da utente":</span><span class="sxs-lookup"><span data-stu-id="ba2a6-142">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="ba2a6-143">In altri termini:</span><span class="sxs-lookup"><span data-stu-id="ba2a6-143">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="ba2a6-144">Questo comando elenca gli utenti univoci in base al numero totale di sessioni a cui hanno partecipato:</span><span class="sxs-lookup"><span data-stu-id="ba2a6-144">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="ba2a6-145">Restituisce dati simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba2a6-145">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="ba2a6-146">Questo comando limita le sessioni incluse nel rapporto a quelle che includevano l'audio come modalità:</span><span class="sxs-lookup"><span data-stu-id="ba2a6-146">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="ba2a6-147">Posizionando il mouse su un ID diagnostica mostrato nel rapporto, viene visualizzata una descrizione comando che descrive l'ID.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-147">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ba2a6-148">Filtri</span><span class="sxs-lookup"><span data-stu-id="ba2a6-148">Filters</span></span>

<span data-ttu-id="ba2a6-p111">I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Il Rapporto attività utente ad esempio consente di filtrare i dati restituiti in base a fattori come il tipo di attività, ovvero sessioni peer-to-peer o di conferenza, oppure in base all'indirizzo SIP dell'utente in modo da visualizzare le attività per un solo utente. È inoltre possibile scegliere come raggruppare i dati. In questo caso, gli utilizzi vengono raggruppati per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-p111">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="ba2a6-153">Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto attività utente.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-153">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="ba2a6-154">Filtri per il Rapporto attività utente</span><span class="sxs-lookup"><span data-stu-id="ba2a6-154">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba2a6-155">Nome</span><span class="sxs-lookup"><span data-stu-id="ba2a6-155">Name</span></span></th>
<th><span data-ttu-id="ba2a6-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba2a6-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba2a6-157"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-157"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-p112">Data/ora di inizio dell'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ba2a6-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="ba2a6-160">17/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="ba2a6-160">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="ba2a6-p113">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="ba2a6-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ba2a6-163">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="ba2a6-163">7/17/12012</span></span></p>
<p><span data-ttu-id="ba2a6-164">Per visualizzare i dati in base alla settimana o al mese, immettere una data che rientra nella settimana o nel mese in base a cui deve essere effettuata la visualizzazione. Non è necessario immettere il primo giorno della settimana o del mese:</span><span class="sxs-lookup"><span data-stu-id="ba2a6-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ba2a6-165">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="ba2a6-165">7/13/2012</span></span></p>
<p><span data-ttu-id="ba2a6-166">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba2a6-167"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-167"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-p114">Data/ora di fine dell'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ba2a6-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="ba2a6-170">17/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="ba2a6-170">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="ba2a6-p115">Se non si specifica l'ora di fine, il rapporto termina automaticamente alla mezzanotte del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="ba2a6-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ba2a6-173">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="ba2a6-173">7/17/12012</span></span></p>
<p><span data-ttu-id="ba2a6-174">Per visualizzare i dati in base alla settimana o al mese, immettere una data che rientra nella settimana o nel mese in base a cui deve essere effettuata la visualizzazione. Non è necessario immettere il primo giorno della settimana o del mese:</span><span class="sxs-lookup"><span data-stu-id="ba2a6-174">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ba2a6-175">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="ba2a6-175">7/13/2012</span></span></p>
<p><span data-ttu-id="ba2a6-176">Le settimane vengono calcolate sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-176">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba2a6-177"><strong>Tipo di attività</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-177"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-p116">Tipo di attività. Selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba2a6-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ba2a6-180">Tutti</span><span class="sxs-lookup"><span data-stu-id="ba2a6-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="ba2a6-181">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="ba2a6-181">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="ba2a6-182">Conferenza</span><span class="sxs-lookup"><span data-stu-id="ba2a6-182">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba2a6-183"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-184">La modalità disponibile varia in base al tipo di attività selezionato.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-184">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="ba2a6-185">Se il tipo di attività è peer-to-peer, è possibile selezionare messaggistica istantanea. Trasferimento di file; Condivisione applicazioni Voce o video come modalità.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-185">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="ba2a6-186">Se il tipo di attività è Conference, è possibile selezionare Chat Phone Conference; Conferenza Web; Condivisione applicazioni Conferenza vocale/video; o la conferenza telefonica.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-186">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba2a6-187"><strong>Categoria sessione</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-187"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-p118">Indica l'esito dell'attività in questione. Selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba2a6-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ba2a6-190">Tutti</span><span class="sxs-lookup"><span data-stu-id="ba2a6-190">[All]</span></span></p></li>
<li><p><span data-ttu-id="ba2a6-191">Completato</span><span class="sxs-lookup"><span data-stu-id="ba2a6-191">Success</span></span></p></li>
<li><p><span data-ttu-id="ba2a6-192">Errore previsto</span><span class="sxs-lookup"><span data-stu-id="ba2a6-192">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="ba2a6-193">Errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="ba2a6-193">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="ba2a6-194">Un &quot; errore previsto &quot; è un errore che dovrebbe verificarsi, ad esempio, se un utente ha impostato lo stato su non disturbare, si prevede che qualsiasi chiamata all'utente non venga eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-194">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="ba2a6-195">Un &quot; errore imprevisto &quot; è un errore che si verifica in un sistema altrimenti integro.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-195">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="ba2a6-196">Una chiamata ad esempio non dovrebbe interrompersi quando il chiamante viene messo in attesa.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-196">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="ba2a6-197">Se la chiamata si interrompe, l'evento verrà contrassegnato come errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-197">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba2a6-198"><strong>Prefisso URI utente</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-p120">Indirizzo SIP dell'utente. Per visualizzare solo i record relativi all'utente Ken Myer, è necessario immettere l'indirizzo SIP di Ken Myer, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ba2a6-p120">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span></p>
<p><span data-ttu-id="ba2a6-202">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ba2a6-202">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="ba2a6-203">Metrica per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="ba2a6-203">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="ba2a6-204">Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto attività utente per le sessioni peer-to-peer, ovvero le sessioni che coinvolgono solo due partecipanti.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-204">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="ba2a6-205">Metrica per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="ba2a6-205">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba2a6-206">Nome</span><span class="sxs-lookup"><span data-stu-id="ba2a6-206">Name</span></span></th>
<th><span data-ttu-id="ba2a6-207">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="ba2a6-207">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ba2a6-208">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba2a6-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba2a6-209"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-209"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-210">No</span><span class="sxs-lookup"><span data-stu-id="ba2a6-210">No</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-211">Quando si fa clic su questo elemento, nel rapporto viene mostrato il Rapporto Dettagli sessione peer-to-peer per la sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-211">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba2a6-212"><strong>Da utente</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-212"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-213">Sì</span><span class="sxs-lookup"><span data-stu-id="ba2a6-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-214">Indirizzo SIP dell'utente che ha avviato la sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-214">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba2a6-215"><strong>A utente</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-215"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-216">Sì</span><span class="sxs-lookup"><span data-stu-id="ba2a6-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-217">Indirizzo SIP dell'utente che ha partecipato alla sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-217">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba2a6-218"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-218"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-219">Sì</span><span class="sxs-lookup"><span data-stu-id="ba2a6-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-p121">Tipo di comunicazione utilizzato nella sessione, ad esempio messaggistica istantanea, audio o trasferimento file.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-p121">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba2a6-222"><strong>Ora invito</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-222"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-223">Sì</span><span class="sxs-lookup"><span data-stu-id="ba2a6-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-224">Data e ora di invio dell'invito iniziale a partecipare alla sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-224">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba2a6-225"><strong>Ora risposta</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-225"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-226">Sì</span><span class="sxs-lookup"><span data-stu-id="ba2a6-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-227">Data e ora in cui &quot; l' &quot; utente ha accettato l'invito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-227">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba2a6-228"><strong>Ora fine</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-228"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-229">Sì</span><span class="sxs-lookup"><span data-stu-id="ba2a6-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-230">Data e ora di fine della sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-230">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba2a6-231"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-231"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-232">Sì</span><span class="sxs-lookup"><span data-stu-id="ba2a6-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-p122">Identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi. Le intestazioni di diagnostica sono facoltative (è possibile che in alcune sessioni SIP non siano incluse queste intestazioni) e gli ID diagnostica sono spesso indicati solo per sessioni in cui si sono verificati problemi di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="ba2a6-235">Metrica per le sessioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="ba2a6-235">Metrics for conferencing sessions</span></span>

<span data-ttu-id="ba2a6-236">Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto attività utente per le sessioni di conferenza, ovvero le sessioni che coinvolgono tre o più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-236">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="ba2a6-237">Metrica per le sessioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="ba2a6-237">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba2a6-238">Nome</span><span class="sxs-lookup"><span data-stu-id="ba2a6-238">Name</span></span></th>
<th><span data-ttu-id="ba2a6-239">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="ba2a6-239">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ba2a6-240">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba2a6-240">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba2a6-241"><strong>URI conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-241"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-242">Sì</span><span class="sxs-lookup"><span data-stu-id="ba2a6-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-243">Identificatore di conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-243">Unique conference identifier.</span></span> <span data-ttu-id="ba2a6-244">Quando si fa clic su questo elemento, nel rapporto viene mostrato il Rapporto Dettagli conferenza per la sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-244">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="ba2a6-245">Quando si espande questo elemento, nel rapporto vengono mostrate le informazioni sui partecipanti della conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-245">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="ba2a6-246">Per ulteriori informazioni, vedere la &quot; sezione metriche per i partecipanti alla conferenza &quot; più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-246">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba2a6-247"><strong>Organizzatore</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-247"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-248">Sì</span><span class="sxs-lookup"><span data-stu-id="ba2a6-248">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-249">Indirizzo SIP dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-249">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba2a6-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-251">Sì</span><span class="sxs-lookup"><span data-stu-id="ba2a6-251">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-252">Nome dell'eventuale server perimetrale utilizzato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-252">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba2a6-253"><strong>Ora inizio</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-253"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-254">Sì</span><span class="sxs-lookup"><span data-stu-id="ba2a6-254">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-255">Data e ora di inizio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-255">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba2a6-256"><strong>Ora fine</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-256"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-257">Sì</span><span class="sxs-lookup"><span data-stu-id="ba2a6-257">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-258">Data e ora di fine della conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-258">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="ba2a6-259">Metrica per i partecipanti di una conferenza</span><span class="sxs-lookup"><span data-stu-id="ba2a6-259">Metrics for conference participants</span></span>

<span data-ttu-id="ba2a6-260">Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto attività utente per ogni partecipante di una conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-260">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="ba2a6-261">Metrica per i partecipanti di una conferenza</span><span class="sxs-lookup"><span data-stu-id="ba2a6-261">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba2a6-262">Nome</span><span class="sxs-lookup"><span data-stu-id="ba2a6-262">Name</span></span></th>
<th><span data-ttu-id="ba2a6-263">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="ba2a6-263">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ba2a6-264">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba2a6-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba2a6-265"><strong>Ruolo</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-265"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-266">No</span><span class="sxs-lookup"><span data-stu-id="ba2a6-266">No</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-267">Ruolo dell'utente nella conferenza, ad esempio Relatore.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-267">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba2a6-268"><strong>Partecipante</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-268"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-269">No</span><span class="sxs-lookup"><span data-stu-id="ba2a6-269">No</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-270">Indirizzo SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-270">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba2a6-271"><strong>Connettività</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-271"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-272">No</span><span class="sxs-lookup"><span data-stu-id="ba2a6-272">No</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-273">Tipo di connessione di rete.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-273">Network connection type.</span></span> <span data-ttu-id="ba2a6-274">Ad esempio &quot; da Internal &quot; per la connessione interna o &quot; da PSTN &quot; per gli utenti con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-274">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba2a6-275"><strong>Ora partecipazione</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-275"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-276">No</span><span class="sxs-lookup"><span data-stu-id="ba2a6-276">No</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-277">Data e ora in cui l'utente ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-277">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba2a6-278"><strong>Ora uscita</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-278"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-279">No</span><span class="sxs-lookup"><span data-stu-id="ba2a6-279">No</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-280">Data e ora in cui l'utente è uscito dalla conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-280">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba2a6-281"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="ba2a6-281"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="ba2a6-282">No</span><span class="sxs-lookup"><span data-stu-id="ba2a6-282">No</span></span></p></td>
<td><p><span data-ttu-id="ba2a6-p125">Identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi. Le intestazioni di diagnostica sono facoltative (è possibile che in alcune sessioni SIP non siano incluse queste intestazioni) e gli ID diagnostica sono spesso indicati solo per sessioni in cui si sono verificati problemi di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="ba2a6-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

