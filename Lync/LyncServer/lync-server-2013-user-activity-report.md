---
title: 'Lync Server 2013: report attività utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04a7dd3dd1f2a061a327cc2a0bac79ee05f21d82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="8697e-102">Report attività utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8697e-102">User Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8697e-103">_**Argomento Ultima modifica:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="8697e-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="8697e-104">Il report attività utente fornisce un elenco dettagliato delle sessioni peer-to-peer e di conferenza svolte dagli utenti in un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="8697e-104">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period.</span></span> <span data-ttu-id="8697e-105">Diversamente da molti dei report di monitoraggio, il report attività utente lega ogni chiamata a singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="8697e-105">Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users.</span></span> <span data-ttu-id="8697e-106">Ad esempio, le sessioni peer-to-peer specificano gli URI SIP della persona che ha avviato la chiamata (l'utente da) e la persona che veniva chiamata (l'utente).</span><span class="sxs-lookup"><span data-stu-id="8697e-106">For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user).</span></span> <span data-ttu-id="8697e-107">Se si espandono le informazioni per una conferenza, viene visualizzato un elenco di tutti i partecipanti alla conferenza e il ruolo che hanno tenuto per la conferenza.</span><span class="sxs-lookup"><span data-stu-id="8697e-107">If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="8697e-108">Il report attività utente viene talvolta indicato come report "Help desk".</span><span class="sxs-lookup"><span data-stu-id="8697e-108">The User Activity Report is sometimes referred to as the "help desk" report.</span></span> <span data-ttu-id="8697e-109">Questo perché il report viene spesso usato dal personale dell'helpdesk per recuperare le informazioni sulla sessione per un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="8697e-109">That's because the report is often used by help desk personnel to retrieve session information for a specific user.</span></span> <span data-ttu-id="8697e-110">Puoi filtrare le chiamate effettuate o effettuate da un singolo utente semplicemente digitando l'URI SIP dell'utente nella casella prefisso URI utente.</span><span class="sxs-lookup"><span data-stu-id="8697e-110">You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="8697e-111">In questo caso, il report attività utente restituirà informazioni per tutti gli utenti il cui URI SIP inizia con la stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="8697e-111">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="8697e-112">Ad esempio, se si digita **Ken** nella casella URI, il report attività utente individuerà **Ken**. Myer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="8697e-112">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="8697e-113">Verranno tuttavia individuati anche gli utenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8697e-113">However, it will also locate these users:</span></span>

  - <span data-ttu-id="8697e-114">**davide**azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8697e-114">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="8697e-115">**davide**Burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8697e-115">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="8697e-116">**Ken**. Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8697e-116">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="8697e-117">**Davide**Nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8697e-117">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="8697e-118">Per fare in modo che vengano restituite le informazioni solo per Ken, digitare l'URI completo (Ken.Myer@litwareinc.com) nella casella di ricerca o almeno il tipo di URI di Ken per distinguerlo in modo univoco dagli altri utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8697e-118">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="8697e-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8697e-119">For example:</span></span>

<span data-ttu-id="8697e-120">Ken.my</span><span class="sxs-lookup"><span data-stu-id="8697e-120">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="8697e-121">Per accedere al report attività utente</span><span class="sxs-lookup"><span data-stu-id="8697e-121">To access the user activity report</span></span>

<span data-ttu-id="8697e-122">Il report attività utente si accede dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="8697e-122">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="8697e-123">È anche possibile accedere al report attività utente facendo clic sulla metrica URI utente nel [report inventario IP telefono in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span><span class="sxs-lookup"><span data-stu-id="8697e-123">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="8697e-124">Dall'interno del report attività utente fare clic sull'URI conferenza (per una conferenza) per il report Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="8697e-124">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="8697e-125">Analogamente, se si fa clic sulla metrica di dettaglio per una chiamata peer-to-peer si passa al [report Dettagli sessione peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="8697e-125">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="8697e-126">Sfruttare al meglio il report attività utente</span><span class="sxs-lookup"><span data-stu-id="8697e-126">Making the best use of the user activity report</span></span>

<span data-ttu-id="8697e-127">Anche se nel report attività utente sono presenti numerose informazioni utili, è possibile che le informazioni a volte siano difficili da individuare.</span><span class="sxs-lookup"><span data-stu-id="8697e-127">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="8697e-128">Ad esempio, tutte le attività utente che si svolgono nell'organizzazione durante un periodo specificato sono incluse nel report attività utente; Questo significa che, sepolto, nel report sono disponibili informazioni su quali utenti hanno effettivamente usato Microsoft Lync Server 2013 in qualche modo.</span><span class="sxs-lookup"><span data-stu-id="8697e-128">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="8697e-129">Tecnicamente, è possibile che alcune attività dell'utente non vengano registrate: mentre Lync Server si sforza di conservare le informazioni su tutte le telefonate, è possibile che sia stata eseguita una chiamata senza che le informazioni relative alla chiamata vengano scritte nel database.</span><span class="sxs-lookup"><span data-stu-id="8697e-129">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="8697e-130">Lync Server è progettato per fornire un aspetto estremamente accurato ma non necessariamente perfetto per l'uso di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8697e-130">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="8697e-131">Il fatto che non sia garantito che il 100% di tutte le chiamate venga registrato spiega perché il monitoraggio di Lync Server non deve essere usato come sistema di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="8697e-131">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="8697e-132">In secondo luogo, un report di report di monitoraggio può solo visualizzare, al massimo, i record di 1.000.</span><span class="sxs-lookup"><span data-stu-id="8697e-132">Second, a Monitoring Report report can only display, at most, 1,000 records.</span></span> <span data-ttu-id="8697e-133">A seconda della quantità di attività utente in uso e in base al periodo di tempo in cui si sta lavorando, significa che la query potrebbe non restituire tutti i dati effettivamente archiviati nel database.</span><span class="sxs-lookup"><span data-stu-id="8697e-133">Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="8697e-134">Quali utenti hanno effettivamente usato il sistema durante questo periodo di tempo?</span><span class="sxs-lookup"><span data-stu-id="8697e-134">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="8697e-135">Quali utenti sono stati i più attivi durante questo periodo di tempo?</span><span class="sxs-lookup"><span data-stu-id="8697e-135">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="8697e-136">Gli utenti che effettuano la maggior parte delle chiamate telefoniche sono anche gli utenti che partecipano alle sessioni di messaggistica istantanea più?</span><span class="sxs-lookup"><span data-stu-id="8697e-136">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="8697e-137">Se è necessario rispondere a domande di questo tipo, è possibile esportare i dati recuperati dai report di monitoraggio in un foglio di calcolo di Excel.</span><span class="sxs-lookup"><span data-stu-id="8697e-137">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="8697e-138">Puoi quindi usare il foglio di calcolo e/o un file con valori delimitati da virgole per analizzare i dati in modo che il report attività utente.</span><span class="sxs-lookup"><span data-stu-id="8697e-138">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="8697e-139">Si supponga ad esempio di aver esportato i dati del report in Excel e quindi in un file con valori delimitati da virgole.</span><span class="sxs-lookup"><span data-stu-id="8697e-139">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="8697e-140">A questo punto è possibile importare i dati da. File CSV in Windows PowerShell usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="8697e-140">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="8697e-141">Dopo aver importato i dati, è possibile usare semplici comandi di Windows PowerShell per rispondere alle domande.</span><span class="sxs-lookup"><span data-stu-id="8697e-141">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="8697e-142">Ad esempio, questo comando restituisce un elenco di utenti univoci che hanno servito come "da utente" in almeno una sessione:</span><span class="sxs-lookup"><span data-stu-id="8697e-142">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="8697e-143">In altre parole:</span><span class="sxs-lookup"><span data-stu-id="8697e-143">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="8697e-144">Questo comando elenca gli utenti univoci (in base al numero totale di sessioni a cui hanno partecipato:</span><span class="sxs-lookup"><span data-stu-id="8697e-144">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="8697e-145">Che restituisce dati simili a questi:</span><span class="sxs-lookup"><span data-stu-id="8697e-145">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="8697e-146">Questo comando limita le sessioni segnalate a quelle che includevano l'audio come modalità:</span><span class="sxs-lookup"><span data-stu-id="8697e-146">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="8697e-147">Se si tiene il mouse su un ID di diagnostica visualizzato nel report, verrà visualizzata una descrizione comando che descrive l'ID.</span><span class="sxs-lookup"><span data-stu-id="8697e-147">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8697e-148">Filtri</span><span class="sxs-lookup"><span data-stu-id="8697e-148">Filters</span></span>

<span data-ttu-id="8697e-149">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="8697e-149">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="8697e-150">Ad esempio, il report attività utente consente di filtrare i dati restituiti in base a elementi come il tipo di attività (ovvero sessioni peer-to-peer o sessioni di conferenza) o l'indirizzo SIP dell'utente (che consente di visualizzare le attività di un utente).</span><span class="sxs-lookup"><span data-stu-id="8697e-150">For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user).</span></span> <span data-ttu-id="8697e-151">È anche possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="8697e-151">You can also choose how data should be grouped.</span></span> <span data-ttu-id="8697e-152">In questo caso, gli usi vengono raggruppati per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="8697e-152">In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="8697e-153">Nella tabella seguente sono elencati i filtri che è possibile usare con il report attività utente.</span><span class="sxs-lookup"><span data-stu-id="8697e-153">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="8697e-154">Filtri di report attività utente</span><span class="sxs-lookup"><span data-stu-id="8697e-154">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8697e-155">Nome</span><span class="sxs-lookup"><span data-stu-id="8697e-155">Name</span></span></th>
<th><span data-ttu-id="8697e-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8697e-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8697e-157"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-157"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-158">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="8697e-158">Start date/time for the time range.</span></span> <span data-ttu-id="8697e-159">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8697e-159">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8697e-160">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8697e-160">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="8697e-161">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="8697e-161">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="8697e-162">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="8697e-162">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8697e-163">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="8697e-163">7/17/12012</span></span></p>
<p><span data-ttu-id="8697e-164">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="8697e-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8697e-165">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="8697e-165">7/13/2012</span></span></p>
<p><span data-ttu-id="8697e-166">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="8697e-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8697e-167"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-167"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-168">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="8697e-168">End date/time for the time range.</span></span> <span data-ttu-id="8697e-169">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8697e-169">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8697e-170">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8697e-170">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="8697e-171">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="8697e-171">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="8697e-172">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="8697e-172">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8697e-173">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="8697e-173">7/17/12012</span></span></p>
<p><span data-ttu-id="8697e-174">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="8697e-174">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8697e-175">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="8697e-175">7/13/2012</span></span></p>
<p><span data-ttu-id="8697e-176">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="8697e-176">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8697e-177"><strong>Tipo di attività</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-177"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-178">Tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="8697e-178">Type of activity.</span></span> <span data-ttu-id="8697e-179">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8697e-179">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8697e-180">Tutti</span><span class="sxs-lookup"><span data-stu-id="8697e-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="8697e-181">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="8697e-181">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="8697e-182">Conferenza</span><span class="sxs-lookup"><span data-stu-id="8697e-182">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8697e-183"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-184">La modalità disponibile varia in base al tipo di attività seleziona.</span><span class="sxs-lookup"><span data-stu-id="8697e-184">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="8697e-185">Se il tipo di attività è peer-to-peer, è possibile selezionare la messaggistica istantanea. Trasferimento file; Condivisione di applicazioni; Segreteria telefonica o video come modalità.</span><span class="sxs-lookup"><span data-stu-id="8697e-185">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="8697e-186">Se il tipo di attività è conferenza, è possibile selezionare conferenza telefonica di messaggistica istantanea; Conferenza Web; Condivisione di applicazioni; Conferenza vocale/video; o conferenza telefonica.</span><span class="sxs-lookup"><span data-stu-id="8697e-186">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8697e-187"><strong>Categoria sessione</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-187"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-188">Indica se l'attività in questione è riuscita o meno.</span><span class="sxs-lookup"><span data-stu-id="8697e-188">Indicates whether the activity in question succeeded or failed.</span></span> <span data-ttu-id="8697e-189">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8697e-189">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8697e-190">Tutti</span><span class="sxs-lookup"><span data-stu-id="8697e-190">[All]</span></span></p></li>
<li><p><span data-ttu-id="8697e-191">Successo</span><span class="sxs-lookup"><span data-stu-id="8697e-191">Success</span></span></p></li>
<li><p><span data-ttu-id="8697e-192">Errore previsto</span><span class="sxs-lookup"><span data-stu-id="8697e-192">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="8697e-193">Errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="8697e-193">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="8697e-194">Un &quot;errore&quot; previsto è un errore che dovrebbe verificarsi; ad esempio, se un utente ha impostato il proprio stato su non disturbare, si prevede che qualsiasi chiamata non venga eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="8697e-194">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="8697e-195">Un &quot;errore&quot; imprevisto è un errore che si verifica in quello che sembrerebbe essere un sistema altrimenti integro.</span><span class="sxs-lookup"><span data-stu-id="8697e-195">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="8697e-196">Ad esempio, una chiamata non deve essere terminata se il chiamante viene posizionato in attesa.</span><span class="sxs-lookup"><span data-stu-id="8697e-196">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="8697e-197">Se questo si verifica, verrebbe contrassegnato come errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="8697e-197">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8697e-198"><strong>Prefisso URI utente</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-199">Indirizzo SIP per l'utente.</span><span class="sxs-lookup"><span data-stu-id="8697e-199">SIP address for the user.</span></span> <span data-ttu-id="8697e-200">Per visualizzare solo i record per l'utente Ken si deve immettere l'indirizzo SIP di Ken.</span><span class="sxs-lookup"><span data-stu-id="8697e-200">To view records only for the user Ken Myer you need to enter Ken Myer's SIP address.</span></span> <span data-ttu-id="8697e-201">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8697e-201">For example:</span></span></p>
<p><span data-ttu-id="8697e-202">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8697e-202">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="8697e-203">Metriche per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="8697e-203">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="8697e-204">Nella tabella seguente sono elencate le informazioni fornite nel report attività utente per le sessioni peer-to-peer, ovvero le sessioni che coinvolgono solo due partecipanti.</span><span class="sxs-lookup"><span data-stu-id="8697e-204">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="8697e-205">Metriche per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="8697e-205">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8697e-206">Nome</span><span class="sxs-lookup"><span data-stu-id="8697e-206">Name</span></span></th>
<th><span data-ttu-id="8697e-207">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="8697e-207">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8697e-208">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8697e-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8697e-209"><strong>Dettaglio</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-209"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-210">No</span><span class="sxs-lookup"><span data-stu-id="8697e-210">No</span></span></p></td>
<td><p><span data-ttu-id="8697e-211">Quando si fa clic su questo elemento, il report Mostra il report Dettagli sessione peer-to-peer per la sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="8697e-211">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8697e-212"><strong>Dall'utente</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-212"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-213">Sì</span><span class="sxs-lookup"><span data-stu-id="8697e-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="8697e-214">Indirizzo SIP dell'utente che ha avviato la sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="8697e-214">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8697e-215"><strong>All'utente</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-215"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-216">Sì</span><span class="sxs-lookup"><span data-stu-id="8697e-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="8697e-217">Indirizzo SIP dell'utente che ha partecipato alla sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="8697e-217">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8697e-218"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-218"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-219">Sì</span><span class="sxs-lookup"><span data-stu-id="8697e-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="8697e-220">Tipo di comunicazione usato nella sessione.</span><span class="sxs-lookup"><span data-stu-id="8697e-220">Type of communication used in the session.</span></span> <span data-ttu-id="8697e-221">Ad esempio, messaggistica istantanea, audio o trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="8697e-221">For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8697e-222"><strong>Invitare il tempo</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-222"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-223">Sì</span><span class="sxs-lookup"><span data-stu-id="8697e-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="8697e-224">Data e ora in cui è stato inviato l'invito iniziale a partecipare alla sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="8697e-224">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8697e-225"><strong>Tempo di risposta</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-225"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-226">Sì</span><span class="sxs-lookup"><span data-stu-id="8697e-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="8697e-227">Data e ora in &quot;&quot; cui l'utente ha accettato l'invito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="8697e-227">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8697e-228"><strong>Ora di fine</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-228"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-229">Sì</span><span class="sxs-lookup"><span data-stu-id="8697e-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="8697e-230">Data e ora terminata la sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="8697e-230">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8697e-231"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-231"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-232">Sì</span><span class="sxs-lookup"><span data-stu-id="8697e-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="8697e-233">Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</span><span class="sxs-lookup"><span data-stu-id="8697e-233">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="8697e-234">Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.</span><span class="sxs-lookup"><span data-stu-id="8697e-234">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="8697e-235">Metriche per le sessioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="8697e-235">Metrics for conferencing sessions</span></span>

<span data-ttu-id="8697e-236">Nella tabella seguente sono elencate le informazioni fornite nel report attività utente per le sessioni di conferenza, ovvero le sessioni che coinvolgono tre o più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="8697e-236">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="8697e-237">Metriche per le sessioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="8697e-237">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8697e-238">Nome</span><span class="sxs-lookup"><span data-stu-id="8697e-238">Name</span></span></th>
<th><span data-ttu-id="8697e-239">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="8697e-239">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8697e-240">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8697e-240">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8697e-241"><strong>URI conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-241"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-242">Sì</span><span class="sxs-lookup"><span data-stu-id="8697e-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="8697e-243">Identificatore di conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="8697e-243">Unique conference identifier.</span></span> <span data-ttu-id="8697e-244">Quando si fa clic su questo elemento, il report Mostra il report Dettagli conferenza per la sessione selezionata.</span><span class="sxs-lookup"><span data-stu-id="8697e-244">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="8697e-245">Quando si espande questo elemento, il report Mostra le informazioni sui partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="8697e-245">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="8697e-246">Per informazioni dettagliate, vedere &quot;la sezione metriche per i&quot; partecipanti alla conferenza più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8697e-246">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8697e-247"><strong>Organizzatore</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-247"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-248">Sì</span><span class="sxs-lookup"><span data-stu-id="8697e-248">Yes</span></span></p></td>
<td><p><span data-ttu-id="8697e-249">Indirizzo SIP dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="8697e-249">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8697e-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-251">Sì</span><span class="sxs-lookup"><span data-stu-id="8697e-251">Yes</span></span></p></td>
<td><p><span data-ttu-id="8697e-252">Nome del server perimetrale (se presente) usato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="8697e-252">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8697e-253"><strong>Ora di inizio</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-253"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-254">Sì</span><span class="sxs-lookup"><span data-stu-id="8697e-254">Yes</span></span></p></td>
<td><p><span data-ttu-id="8697e-255">Data e ora di inizio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="8697e-255">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8697e-256"><strong>Ora di fine</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-256"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-257">Sì</span><span class="sxs-lookup"><span data-stu-id="8697e-257">Yes</span></span></p></td>
<td><p><span data-ttu-id="8697e-258">Data e ora di fine della conferenza.</span><span class="sxs-lookup"><span data-stu-id="8697e-258">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="8697e-259">Metriche per i partecipanti alla conferenza</span><span class="sxs-lookup"><span data-stu-id="8697e-259">Metrics for conference participants</span></span>

<span data-ttu-id="8697e-260">La tabella seguente elenca le informazioni fornite nel report attività utente per ogni partecipante di una conferenza.</span><span class="sxs-lookup"><span data-stu-id="8697e-260">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="8697e-261">Metriche per i partecipanti alla conferenza</span><span class="sxs-lookup"><span data-stu-id="8697e-261">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8697e-262">Nome</span><span class="sxs-lookup"><span data-stu-id="8697e-262">Name</span></span></th>
<th><span data-ttu-id="8697e-263">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="8697e-263">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8697e-264">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8697e-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8697e-265"><strong>Ruolo</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-265"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-266">No</span><span class="sxs-lookup"><span data-stu-id="8697e-266">No</span></span></p></td>
<td><p><span data-ttu-id="8697e-267">Ruolo conferenza, ad esempio relatore, per l'utente.</span><span class="sxs-lookup"><span data-stu-id="8697e-267">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8697e-268"><strong>Partecipante</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-268"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-269">No</span><span class="sxs-lookup"><span data-stu-id="8697e-269">No</span></span></p></td>
<td><p><span data-ttu-id="8697e-270">Indirizzo SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8697e-270">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8697e-271"><strong>Connettività</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-271"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-272">No</span><span class="sxs-lookup"><span data-stu-id="8697e-272">No</span></span></p></td>
<td><p><span data-ttu-id="8697e-273">Tipo di connessione di rete.</span><span class="sxs-lookup"><span data-stu-id="8697e-273">Network connection type.</span></span> <span data-ttu-id="8697e-274">Ad esempio &quot;da Internal&quot; per la connessione interna &quot;o da&quot; PSTN per gli utenti con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="8697e-274">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8697e-275"><strong>Tempo di partecipazione</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-275"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-276">No</span><span class="sxs-lookup"><span data-stu-id="8697e-276">No</span></span></p></td>
<td><p><span data-ttu-id="8697e-277">Data e ora in cui l'utente ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="8697e-277">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8697e-278"><strong>Ora di uscita</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-278"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-279">No</span><span class="sxs-lookup"><span data-stu-id="8697e-279">No</span></span></p></td>
<td><p><span data-ttu-id="8697e-280">Data e ora in cui l'utente ha lasciato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="8697e-280">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8697e-281"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="8697e-281"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="8697e-282">No</span><span class="sxs-lookup"><span data-stu-id="8697e-282">No</span></span></p></td>
<td><p><span data-ttu-id="8697e-283">Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</span><span class="sxs-lookup"><span data-stu-id="8697e-283">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="8697e-284">Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.</span><span class="sxs-lookup"><span data-stu-id="8697e-284">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

