---
title: 'Lync Server 2013: utilizzo di report di monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b7c1e70a47e3f3043215e1d16e1f01bfec4b677
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-monitoring-reports-in-lync-server-2013"></a><span data-ttu-id="c0e37-102">Uso di report di monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0e37-102">Using Monitoring Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0e37-103">_**Argomento Ultima modifica:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="c0e37-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="c0e37-104">Lync Server 2013 include un set di report standard pubblicati da Microsoft SQL Server Reporting Service.</span><span class="sxs-lookup"><span data-stu-id="c0e37-104">Lync Server 2013 includes a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="c0e37-105">Questi report, accessibili tramite un Web browser, consentono l'utilizzo, le informazioni di diagnostica delle chiamate e le informazioni sulla qualità dei contenuti multimediali, tutte basate sui record di registrazione dei dettagli delle chiamate (CDR) e la qualità dell'esperienza (QoE) archiviati nei database CDR e QoE.</span><span class="sxs-lookup"><span data-stu-id="c0e37-105">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span>

<span data-ttu-id="c0e37-106">Per usare questi report, è necessario installare i report di monitoraggio in un computer in cui è in corso un'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c0e37-106">In order to use these reports, you must install Monitoring Reports on a computer that is running an instance of the SQL Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c0e37-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c0e37-107">In This Section</span></span>

  - <span data-ttu-id="c0e37-108">[L'uso del dashboard di monitoraggio in Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   offre agli amministratori una rapida panoramica dell'integrità del sistema e dell'uso del sistema.</span><span class="sxs-lookup"><span data-stu-id="c0e37-108">[Using the Monitoring Dashboard in Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   Provides administrators with a quick overview of their system health and system usage.</span></span>

  - <span data-ttu-id="c0e37-109">[I report sull'utilizzo del sistema in Lync Server 2013](lync-server-2013-system-usage-reports.md)   offrono informazioni sull'uso del sistema in base ai dati CDR raccolti da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c0e37-109">[System usage reports in Lync Server 2013](lync-server-2013-system-usage-reports.md)   Provides system usage information based on CDR data collected by Lync Server.</span></span>

  - <span data-ttu-id="c0e37-110">[I report di diagnostica delle chiamate (per utente) in Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   offrono informazioni per utente sulle sessioni peer-to-peer e conferenze non riuscite.</span><span class="sxs-lookup"><span data-stu-id="c0e37-110">[Call Diagnostic Reports (per user) in Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   Provides per-user information about failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="c0e37-111">[I report di diagnostica delle chiamate in Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   offrono informazioni di riepilogo e dati di diagnostica per sessioni peer-to-peer e conferenze non riuscite.</span><span class="sxs-lookup"><span data-stu-id="c0e37-111">[Call Diagnostic Reports in Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   Provides summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="c0e37-112">[Report di diagnostica di qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   fornisce informazioni sulla qualità delle chiamate, nonché informazioni di diagnostica e risoluzione dei problemi per le chiamate non riuscite.</span><span class="sxs-lookup"><span data-stu-id="c0e37-112">[Media Quality Diagnostic Reports in Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   Provides information about call quality as well as diagnostic and troubleshooting information for failed calls.</span></span>

</div>

<div>

## <a name="locating-records"></a><span data-ttu-id="c0e37-113">Individuazione di record</span><span class="sxs-lookup"><span data-stu-id="c0e37-113">Locating Records</span></span>

<span data-ttu-id="c0e37-114">I report di monitoraggio mostrano solo un numero limitato di record sullo schermo in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="c0e37-114">Monitoring Reports only show a limited number of records on the screen at any one time.</span></span> <span data-ttu-id="c0e37-115">Il numero effettivo di record visualizzati in uno schermo varia a seconda del report.</span><span class="sxs-lookup"><span data-stu-id="c0e37-115">The actual number of records displayed on a screen varies depending on the report.</span></span> <span data-ttu-id="c0e37-116">Per visualizzare i record che non sono attualmente visualizzati sullo schermo, è possibile usare il controllo avanti e indietro standard (disponibile nella barra degli strumenti di ogni report) che consente di eseguire la pagina dei dati.</span><span class="sxs-lookup"><span data-stu-id="c0e37-116">To view the records that are not currently shown on the screen you can use the standard forward and backward control (found on each report’s toolbar) that enable you to page through the data.</span></span> <span data-ttu-id="c0e37-117">È anche possibile passare rapidamente alla prima pagina o all'ultima pagina del set di dati.</span><span class="sxs-lookup"><span data-stu-id="c0e37-117">You can also quickly jump to the first page or the last page of the dataset.</span></span>

<span data-ttu-id="c0e37-118">Oltre a usare i controlli avanti e indietro, è anche possibile passare a una pagina qualsiasi del DataSet digitando semplicemente il numero di pagina nella casella **pagina corrente** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="c0e37-118">In addition to using the forward and backward controls, you can also jump to any page in the dataset simply by typing the page number in the **Current Page** box, and then press ENTER.</span></span>

<span data-ttu-id="c0e37-119">Oltre a fornire la possibilità di paginare i dati, ogni report include anche la limitata capacità di trovare record.</span><span class="sxs-lookup"><span data-stu-id="c0e37-119">In addition to providing the ability to page through the data, each report also includes the limited ability to find records.</span></span> <span data-ttu-id="c0e37-120">Per trovare i record in base a un valore specifico, digitare tale valore nella casella **trova** e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="c0e37-120">To find records based on a given value, type that value into the **Find** box, and then click **Find**.</span></span> <span data-ttu-id="c0e37-121">Il report inizia la ricerca nei dati e si arresta nella prima istanza del valore immesso nella casella **trova** .</span><span class="sxs-lookup"><span data-stu-id="c0e37-121">The report begins searching through the data and stops on the first instance of the value that you entered in the **Find** box.</span></span> <span data-ttu-id="c0e37-122">Per trovare il record successivo che soddisfa i criteri di ricerca, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c0e37-122">To find the next record that meets the search criteria, click **Next**.</span></span>

<span data-ttu-id="c0e37-123">Come indicato, i report di monitoraggio contengono solo le funzioni di ricerca più basilari.</span><span class="sxs-lookup"><span data-stu-id="c0e37-123">As noted, the Monitoring Reports provide only the most basic search functions.</span></span> <span data-ttu-id="c0e37-124">Ad esempio, non è possibile specificare il campo in cui deve essere trovato il valore.</span><span class="sxs-lookup"><span data-stu-id="c0e37-124">For example, you cannot specify which field the value should be found in.</span></span> <span data-ttu-id="c0e37-125">Il meccanismo di ricerca cerca automaticamente i valori corrispondenti in tutti i campi di ogni record.</span><span class="sxs-lookup"><span data-stu-id="c0e37-125">The search mechanism automatically searches for matching values in every field in every record.</span></span> <span data-ttu-id="c0e37-126">Non è possibile usare i caratteri jolly nelle ricerche e tutte le ricerche cercano valori parziali.</span><span class="sxs-lookup"><span data-stu-id="c0e37-126">You cannot use wildcards in your searches, and all searches look for partial values.</span></span> <span data-ttu-id="c0e37-127">Ciò significa che se si cerca 111 la ricerca restituisce il valore 111 insieme ai valori 11100, 811, 3112, 611A5B e tutti gli altri campi che includono il valore 111 in un punto qualsiasi all'interno di tale campo.</span><span class="sxs-lookup"><span data-stu-id="c0e37-127">That means that if you search for 111 the search returns the value 111 along with the values 11100, 811, 3112, 611A5B, and any other fields that include the value 111 anywhere within that field.</span></span>

<span data-ttu-id="c0e37-128">Ogni report è configurato per visualizzare un set predefinito di record.</span><span class="sxs-lookup"><span data-stu-id="c0e37-128">Each report is configured to show a default set of records.</span></span> <span data-ttu-id="c0e37-129">Per impostazione predefinita, ad esempio, il report di registrazione dell'utente Mostra le attività di registrazione degli utenti per la settimana passata.</span><span class="sxs-lookup"><span data-stu-id="c0e37-129">For example, by default the User Registration Report shows user registration activities for the past week.</span></span> <span data-ttu-id="c0e37-130">In alcuni casi, potrebbe verificarsi un report che restituisce nessun record.</span><span class="sxs-lookup"><span data-stu-id="c0e37-130">In some cases, this might result in a report that returns no records.</span></span> <span data-ttu-id="c0e37-131">In questo caso, significa che non sono state registrate registrazioni utente nell'ultima settimana.</span><span class="sxs-lookup"><span data-stu-id="c0e37-131">In this case, it means that no user registrations have taken place in the past week.</span></span> <span data-ttu-id="c0e37-132">Se viene visualizzato il messaggio "nessun risultato corrisponde ai filtri dei report", provare a modificare i valori di filtro (ad esempio, cambiare il periodo di tempo dell'ultimo mese anziché la settimana precedente) e rieseguire la query.</span><span class="sxs-lookup"><span data-stu-id="c0e37-132">If you see the message “No results match the report filters,” try changing the filter values (for example, change the time period to the past month rather than the past week) and rerun the query.</span></span> <span data-ttu-id="c0e37-133">Per informazioni dettagliate, vedere la sezione "filtro dei dati" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c0e37-133">For details, see the "Filtering Data" section later in this topic.</span></span>

</div>

<div>

## <a name="filtering-data"></a><span data-ttu-id="c0e37-134">Filtrare i dati</span><span class="sxs-lookup"><span data-stu-id="c0e37-134">Filtering Data</span></span>

<span data-ttu-id="c0e37-135">Ci saranno probabilmente momenti in cui si vuole esaminare solo un sottoinsieme di record.</span><span class="sxs-lookup"><span data-stu-id="c0e37-135">There will likely be times when you want to look at only a subset of records.</span></span> <span data-ttu-id="c0e37-136">Ad esempio, solo le sessioni peer-to-peer invece di sessioni peer-to-peer e conferenze.</span><span class="sxs-lookup"><span data-stu-id="c0e37-136">For example, only peer-to-peer sessions as opposed to both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="c0e37-137">Allo stesso modo, ci saranno momenti in cui è necessario ridurre il numero di record restituiti.</span><span class="sxs-lookup"><span data-stu-id="c0e37-137">Likewise, there will be times when you need to reduce the number of records that are returned.</span></span> <span data-ttu-id="c0e37-138">Per impostazione predefinita, un report può visualizzare solo i primi record di 1.000 in un set di dati.</span><span class="sxs-lookup"><span data-stu-id="c0e37-138">By default, a report can only display the first 1,000 records in a data set.</span></span> <span data-ttu-id="c0e37-139">Per risolvere questi problemi, la maggior parte dei report include una serie di opzioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="c0e37-139">To address these issues, most reports include a number of filtering options.</span></span> <span data-ttu-id="c0e37-140">Ad esempio, se si vogliono visualizzare solo i record per l'intervallo di tempo compreso tra il 1 ° gennaio 2011 e il 15 gennaio 2011, è possibile immettere il 1 ° gennaio 2011 nella casella **da** e il 15 gennaio 2011 nella casella **a** .</span><span class="sxs-lookup"><span data-stu-id="c0e37-140">For example, if you want to view only records for the time period January 1, 2011 through January 15, 2011, you can enter January 1, 2011 in the **From** box and January 15, 2011 in the **To** box.</span></span> <span data-ttu-id="c0e37-141">Se si fa clic su **Visualizza report**, i dati restituiti saranno limitati alle attività che hanno avuto luogo tra il 1 ° gennaio 2011 e il 15 gennaio 2011.</span><span class="sxs-lookup"><span data-stu-id="c0e37-141">If you then click **View Report**, the returned data will be limited to activities that took place between January 1, 2011 and January 15, 2011.</span></span>

<span data-ttu-id="c0e37-142">I filtri disponibili variano a seconda del report che si sta visualizzando.</span><span class="sxs-lookup"><span data-stu-id="c0e37-142">The filters available to you vary depending on the report that you are viewing.</span></span> <span data-ttu-id="c0e37-143">Per informazioni dettagliate su un report specifico, vedere l'argomento della Guida relativo al report.</span><span class="sxs-lookup"><span data-stu-id="c0e37-143">For details about a specific report, see the help topic for that report.</span></span>

</div>

<div>

## <a name="exporting-data"></a><span data-ttu-id="c0e37-144">Esportazione di dati</span><span class="sxs-lookup"><span data-stu-id="c0e37-144">Exporting Data</span></span>

<span data-ttu-id="c0e37-145">I report di monitoraggio includono almeno due modi diversi per esportare i dati inclusi in un report.</span><span class="sxs-lookup"><span data-stu-id="c0e37-145">The Monitoring Reports provide at least two different ways to export the data included in a report.</span></span> <span data-ttu-id="c0e37-146">È possibile usare l'opzione **Esporta** nella barra degli strumenti visualizzata nella parte superiore di ogni report.</span><span class="sxs-lookup"><span data-stu-id="c0e37-146">You can use the **Export** option in the toolbar that appears at the top of each report.</span></span> <span data-ttu-id="c0e37-147">Per usare questa opzione, selezionare il formato di esportazione desiderato nell'elenco a discesa **selezionare un formato** .</span><span class="sxs-lookup"><span data-stu-id="c0e37-147">To use this option, select the desired export format from the **Select a format** drop-down list.</span></span> <span data-ttu-id="c0e37-148">I formati seguenti sono disponibili:</span><span class="sxs-lookup"><span data-stu-id="c0e37-148">The following formats are available to you:</span></span>

  - <span data-ttu-id="c0e37-149">File XML con i dati del report</span><span class="sxs-lookup"><span data-stu-id="c0e37-149">XML file with report data</span></span>

  - <span data-ttu-id="c0e37-150">CSV (delimitato da virgola)</span><span class="sxs-lookup"><span data-stu-id="c0e37-150">CSV (comma delimited)</span></span>

  - <span data-ttu-id="c0e37-151">File Acrobat (PDF)</span><span class="sxs-lookup"><span data-stu-id="c0e37-151">Acrobat (PDF) file</span></span>

  - <span data-ttu-id="c0e37-152">MHTML (archivio Web)</span><span class="sxs-lookup"><span data-stu-id="c0e37-152">MHTML (web archive)</span></span>

  - <span data-ttu-id="c0e37-153">Excel</span><span class="sxs-lookup"><span data-stu-id="c0e37-153">Excel</span></span>

  - <span data-ttu-id="c0e37-154">File TIFF</span><span class="sxs-lookup"><span data-stu-id="c0e37-154">TIFF file</span></span>

  - <span data-ttu-id="c0e37-155">Word</span><span class="sxs-lookup"><span data-stu-id="c0e37-155">Word</span></span>

<span data-ttu-id="c0e37-156">Dopo aver selezionato un formato, fare clic su **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="c0e37-156">After selecting a format, click **Export**.</span></span> <span data-ttu-id="c0e37-157">Quando viene visualizzata la finestra di dialogo **Download file** , fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c0e37-157">When the **File Download** dialog box appears, click **Save**.</span></span> <span data-ttu-id="c0e37-158">Nella finestra di dialogo **Salva con** nome selezionare una cartella di destinazione e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c0e37-158">In the **Save As** dialog box, select a destination folder, enter a file name, and then click **Save**.</span></span>

<span data-ttu-id="c0e37-159">Se è installato Microsoft OneNote, è anche possibile copiare i dati del report in OneNote.</span><span class="sxs-lookup"><span data-stu-id="c0e37-159">If you have Microsoft OneNote installed, you can also copy the report data to OneNote.</span></span> <span data-ttu-id="c0e37-160">A questo scopo, fai clic con il **pulsante destro del mouse sulla barra** degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="c0e37-160">To do this, right-click the **View Report** button on the toolbar.</span></span> <span data-ttu-id="c0e37-161">Nella finestra di dialogo **Seleziona posizione in OneNote** selezionare la sezione in OneNote in cui si vogliono copiare i dati e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0e37-161">In the **Select Location in OneNote** dialog box select the section in OneNote where you want to copy the data, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

