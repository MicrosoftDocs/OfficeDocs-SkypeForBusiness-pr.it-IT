---
title: 'Lync Server 2013: rapporto dispositivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97971d339dc57ab8786ff4a05adadd016a87e23a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522453"
---
# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="feedf-102">Report dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="feedf-102">Device Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="feedf-103">_**Ultimo argomento modificato:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="feedf-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="feedf-104">Il Rapporto dispositivi potrebbe anche essere intitolato Rapporto altoparlanti e microfono perché il Rapporto dispositivi recupera le metriche relative alle chiamate (ad esempio, la percentuale di chiamate con qualità insufficiente, l'eco e il tempo commutazione vocale) raggruppate in base ai microfoni e agli altoparlanti utilizzati nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="feedf-104">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="feedf-105">Se si è interessati ai telefoni IP (noti anche come "dispositivi"), utilizzare il [rapporto inventario telefoni IP in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) .</span><span class="sxs-lookup"><span data-stu-id="feedf-105">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="feedf-p102">Il Rapporto dispositivi è estremamente utile agli amministratori per stabilire se un tipo specifico di dispositivo riporta volumi elevati di chiamate con qualità insufficiente rispetto ad altri. Questo può influire sulle decisioni da prendere in merito all'acquisto di nuovi dispositivi o alla sostituzione dei dispositivi esistenti.</span><span class="sxs-lookup"><span data-stu-id="feedf-p102">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others. In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="feedf-p103">Per impostazione predefinita, le informazioni visualizzate nel Rapporto dispositivi si basano sul microfono (il dispositivo di acquisizione) e gli altoparlanti/auricolari (il dispositivo di rendering) utilizzati nella chiamata. Ad esempio, si supponga che vari utenti debbano utilizzare il dispositivo di acquisizione e il dispositivo di rendering seguenti:</span><span class="sxs-lookup"><span data-stu-id="feedf-p103">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="feedf-111">Dispositivo di acquisizione -- Microfono (HD Audio integrato digitale SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="feedf-111">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="feedf-112">Dispositivo di rendering -- Auricolare e microtelefono (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="feedf-112">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="feedf-113">Se gli utenti hanno eseguito un totale di 254 chiamate, nel rapporto verrà visualizzata una voce simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="feedf-113">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="feedf-114">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="feedf-114">Capture device</span></span></th>
<th><span data-ttu-id="feedf-115">Dispositivo di rendering</span><span class="sxs-lookup"><span data-stu-id="feedf-115">Render device</span></span></th>
<th><span data-ttu-id="feedf-116">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="feedf-116">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="feedf-117">Microfono (HD Audio integrato digitale SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="feedf-117">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="feedf-118">Auricolare e microtelefono (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="feedf-118">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="feedf-119">254</span><span class="sxs-lookup"><span data-stu-id="feedf-119">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="feedf-p104">Ora si supponga che un certo numero di utenti utilizzi lo stesso dispositivo di acquisizione ma un dispositivo di rendering diverso. In tal caso, nel report verrà visualizzata una voce nella seconda riga per tale combinazione univoca di dispositivo di acquisizione e dispositivo di rendering:</span><span class="sxs-lookup"><span data-stu-id="feedf-p104">Now, suppose you have a number of users who use that same capture device but a different render device. In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="feedf-122">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="feedf-122">Capture device</span></span></th>
<th><span data-ttu-id="feedf-123">Dispositivo di rendering</span><span class="sxs-lookup"><span data-stu-id="feedf-123">Render device</span></span></th>
<th><span data-ttu-id="feedf-124">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="feedf-124">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="feedf-125">Microfono (HD Audio integrato digitale SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="feedf-125">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="feedf-126">Auricolare e microtelefono (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="feedf-126">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="feedf-127">254</span><span class="sxs-lookup"><span data-stu-id="feedf-127">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feedf-128">Microfono (HD Audio integrato digitale SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="feedf-128">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="feedf-129">Altoparlanti (HD Audio integrato digitale SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="feedf-129">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="feedf-130">319</span><span class="sxs-lookup"><span data-stu-id="feedf-130">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="feedf-p105">Se si desidera visualizzare i totali combinati per un determinato dispositivo (ad esempio, per il dispositivo di acquisizione SoundMAX, indipendentemente dal dispositivo di rendering utilizzato), selezionare l'opzione appropriata dall'elenco a discesa Tipo di dispositivo (Dispositivo di acquisizione o Dispositivo di rendering). Se nell'esempio si seleziona Dispositivo di acquisizione, si riceverà il seguente output:</span><span class="sxs-lookup"><span data-stu-id="feedf-p105">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device). If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="feedf-133">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="feedf-133">Capture device</span></span></th>
<th><span data-ttu-id="feedf-134">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="feedf-134">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="feedf-135">Microfono (HD Audio integrato digitale SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="feedf-135">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="feedf-136">573</span><span class="sxs-lookup"><span data-stu-id="feedf-136">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="feedf-137">Accesso al Rapporto dispositivi</span><span class="sxs-lookup"><span data-stu-id="feedf-137">Accessing the Device Report</span></span>

<span data-ttu-id="feedf-138">In genere è possibile accedere al Rapporto dispositivi dalla home page Relazioni monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="feedf-138">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="feedf-139">Tuttavia, se si sta visualizzando il [rapporto dettagli chiamata in Lync Server 2013](lync-server-2013-call-detail-report.md) , è possibile eseguire il drill-down nel rapporto dispositivo per un dispositivo specifico facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="feedf-139">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="feedf-140">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="feedf-140">Capture Device</span></span>

  - <span data-ttu-id="feedf-141">Dispositivo di rendering</span><span class="sxs-lookup"><span data-stu-id="feedf-141">Render Device</span></span>

<span data-ttu-id="feedf-142">Dal rapporto dispositivo è possibile eseguire il drill-down [nel rapporto elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="feedf-142">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="feedf-143">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="feedf-143">Call volume</span></span>

  - <span data-ttu-id="feedf-144">Percentuale chiamate di livello insufficiente</span><span class="sxs-lookup"><span data-stu-id="feedf-144">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="feedf-145">Utilizzo del Rapporto dispositivi</span><span class="sxs-lookup"><span data-stu-id="feedf-145">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="feedf-146">Il Rapporto dispositivi è molto dettagliato in merito ai nomi dei dispositivi. Ad esempio, si supponga di disporre dei dispositivi di acquisizione seguenti:</span><span class="sxs-lookup"><span data-stu-id="feedf-146">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="feedf-147">Microfono Aastra 3002 (2- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="feedf-147">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="feedf-148">Microfono Aastra 3002 (3- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="feedf-148">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="feedf-149">Microfono Aastra 3002 (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="feedf-149">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="feedf-150">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="feedf-150">Aastra 6725ip</span></span>

  - <span data-ttu-id="feedf-151">Microfono Aastra 6725ip (10- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="feedf-151">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="feedf-152">Microfono Aastra 6725ip (10- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="feedf-152">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="feedf-153">Microfono Aastra 6725ip (2- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="feedf-153">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="feedf-154">Microfono Aastra 6725ip (3- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="feedf-154">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="feedf-155">Microfono Aastra 6725ip (4- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="feedf-155">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="feedf-156">Microfono Aastra 6725ip (5- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="feedf-156">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="feedf-157">Microfono Aastra 6725ip (6- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="feedf-157">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="feedf-158">Microfono Aastra 6725ip (7- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="feedf-158">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="feedf-159">Microfono Aastra 6725ip (9- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="feedf-159">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="feedf-160">Microfono Aastra 6725ip (9- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="feedf-160">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="feedf-161">Microfono Aastra 6725ip (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="feedf-161">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="feedf-162">Microfono Aastra 6725ip (Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="feedf-162">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="feedf-163">Microfono Aastra 6725ip (dispositivo audio USB)</span><span class="sxs-lookup"><span data-stu-id="feedf-163">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="feedf-164">Microfono Aastra 6725ip (dispositivo audio USB)-V0</span><span class="sxs-lookup"><span data-stu-id="feedf-164">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="feedf-165">Tenere presente che i nomi dei dispositivi di acquisizione potrebbero non essere uguali se si eseguono versioni localizzate di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feedf-165">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="feedf-166">Un dispositivo denominato Aastra 6725ip Microphone (Aastra 6725ip)-V0 in inglese (Stati Uniti) potrebbe avere un nome diverso in francese o spagnolo.</span><span class="sxs-lookup"><span data-stu-id="feedf-166">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="feedf-167">Anche se spesso è utile questo livello di dettaglio, a volte si potrebbe essere interessati solo al numero di chiamate che utilizzano qualsiasi microfono Aastra, indipendentemente dal numero del modello.</span><span class="sxs-lookup"><span data-stu-id="feedf-167">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="feedf-168">Un modo per ottenere informazioni di questo tipo consiste nell'esportare i dati del report del dispositivo in Microsoft Excel e quindi salvarli in un file con valori delimitati da virgole (ad esempio, C: \\ data \\ devices \_Report.csv).</span><span class="sxs-lookup"><span data-stu-id="feedf-168">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="feedf-169">È possibile utilizzare un insieme di comandi simili a questi per importare il file CSV in Windows PowerShell e restituire il numero totale di chiamate eseguite utilizzando un dispositivo di acquisizione Aastra:</span><span class="sxs-lookup"><span data-stu-id="feedf-169">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="feedf-p109">Verrà restituito un unico valore che rappresenta il numero totale di chiamate eseguite utilizzando un dispositivo di acquisizione Aastra. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="feedf-p109">That will return a single value representing the total number of calls made using an Aastra capture device. For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="feedf-172">Filtri</span><span class="sxs-lookup"><span data-stu-id="feedf-172">Filters</span></span>

<span data-ttu-id="feedf-p110">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il Rapporto dispositivi consente di filtrare in base a elementi quali il tipo di chiamata (ossia se la chiamata è di tipo client) una conferenza telefonica o una chiamata PSTN (Public Switched Telephone Network). È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso i dispositivi sono raggruppabili per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="feedf-p110">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call. You can also choose how data should be grouped. In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="feedf-177">Nella tabella seguente sono elencati i filtri applicabili al Rapporto dispositivi.</span><span class="sxs-lookup"><span data-stu-id="feedf-177">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="feedf-178">Filtri del Rapporto dispositivi</span><span class="sxs-lookup"><span data-stu-id="feedf-178">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="feedf-179">Nome</span><span class="sxs-lookup"><span data-stu-id="feedf-179">Name</span></span></th>
<th><span data-ttu-id="feedf-180">Descrizione</span><span class="sxs-lookup"><span data-stu-id="feedf-180">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="feedf-181"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-181"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-p111">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="feedf-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="feedf-184">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="feedf-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="feedf-p112">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="feedf-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="feedf-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="feedf-187">7/7/2012</span></span></p>
<p><span data-ttu-id="feedf-188">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="feedf-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="feedf-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="feedf-189">7/3/2012</span></span></p>
<p><span data-ttu-id="feedf-190">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="feedf-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feedf-191"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-191"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-p113">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="feedf-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="feedf-194">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="feedf-194">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="feedf-p114">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="feedf-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="feedf-197">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="feedf-197">7/7/2012</span></span></p>
<p><span data-ttu-id="feedf-198">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="feedf-198">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="feedf-199">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="feedf-199">7/3/2012</span></span></p>
<p><span data-ttu-id="feedf-200">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="feedf-200">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feedf-201"><strong>Causa commutazione vocale</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-201"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-p115">Motivo per cui è stato necessario effettuare una chiamata in modalità half-duplex per evitare l'eco. In modalità half-duplex la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo ai turni effettuati dagli utenti in una comunicazione con un walkie-talkie. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="feedf-p115">Reason why a call had to be placed into half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-205">Tutti</span><span class="sxs-lookup"><span data-stu-id="feedf-205">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-206">Nessuno</span><span class="sxs-lookup"><span data-stu-id="feedf-206">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-207">Timestamp non valido</span><span class="sxs-lookup"><span data-stu-id="feedf-207">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-208">Echo</span><span class="sxs-lookup"><span data-stu-id="feedf-208">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-209">DNLP (dynamic nonlinear processor)</span><span class="sxs-lookup"><span data-stu-id="feedf-209">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-210">Complessità bassa</span><span class="sxs-lookup"><span data-stu-id="feedf-210">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-211">Stato dispositivo non valido</span><span class="sxs-lookup"><span data-stu-id="feedf-211">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-212">Eco dopo eliminazione eco acustica</span><span class="sxs-lookup"><span data-stu-id="feedf-212">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feedf-213"><strong>Causa eco</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-213"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-p116">Motivo per cui in una chiamata è stato rilevato l'eco sopra il livello accettato (nelle telecomunicazioni l'eco è un riflesso del suono, lo stesso effetto che si produce gridando verso il fondo di un pozzo). Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="feedf-p116">Reason why echo above the accepted level was detected in a call. (In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-216">Tutti</span><span class="sxs-lookup"><span data-stu-id="feedf-216">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-217">Nessuno</span><span class="sxs-lookup"><span data-stu-id="feedf-217">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-218">Timestamp non valido</span><span class="sxs-lookup"><span data-stu-id="feedf-218">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-219">Eco dopo eliminazione eco acustica</span><span class="sxs-lookup"><span data-stu-id="feedf-219">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-220">ANLP (adaptive nonlinear processor)</span><span class="sxs-lookup"><span data-stu-id="feedf-220">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-221">DNLP (dynamic nonlinear processor)</span><span class="sxs-lookup"><span data-stu-id="feedf-221">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-222">Clip microfono</span><span class="sxs-lookup"><span data-stu-id="feedf-222">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feedf-223"><strong>Tipo di chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-223"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-p117">Indica il tipo di chiamata effettuata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="feedf-p117">Indicates the type of call that was made. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-226">Tutti</span><span class="sxs-lookup"><span data-stu-id="feedf-226">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-227">Chiamata client</span><span class="sxs-lookup"><span data-stu-id="feedf-227">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-228">Chiamata PSTN</span><span class="sxs-lookup"><span data-stu-id="feedf-228">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-229">Conferenza telefonica</span><span class="sxs-lookup"><span data-stu-id="feedf-229">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feedf-230"><strong>Tipo di accesso</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-230"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-p118">Indica se al momento dell'esecuzione della chiamata il client era connesso alla rete interna o alla rete esterna. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="feedf-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-233">Tutti</span><span class="sxs-lookup"><span data-stu-id="feedf-233">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-234">Interno</span><span class="sxs-lookup"><span data-stu-id="feedf-234">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-235">Esterno</span><span class="sxs-lookup"><span data-stu-id="feedf-235">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feedf-236"><strong>Tipo di rete</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-236"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-p119">Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="feedf-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-239">Tutti</span><span class="sxs-lookup"><span data-stu-id="feedf-239">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-240">Cablata</span><span class="sxs-lookup"><span data-stu-id="feedf-240">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-241">Wireless</span><span class="sxs-lookup"><span data-stu-id="feedf-241">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feedf-242"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-242"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-p120">Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="feedf-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-245">Tutti</span><span class="sxs-lookup"><span data-stu-id="feedf-245">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-246">VPN</span><span class="sxs-lookup"><span data-stu-id="feedf-246">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-247">Non VPN</span><span class="sxs-lookup"><span data-stu-id="feedf-247">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feedf-248"><strong>Tipo di dispositivo</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-248"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-p121">Indica il tipo di dispositivo. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="feedf-p121">Indicates the type of device. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-251">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="feedf-251">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-252">Dispositivo di rendering</span><span class="sxs-lookup"><span data-stu-id="feedf-252">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="feedf-253">Coppia di dispositivi di acquisizione/rendering</span><span class="sxs-lookup"><span data-stu-id="feedf-253">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feedf-254"><strong>Nome dispositivo</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-254"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-p122">Nome del dispositivo di acquisizione o di rendering. È possibile immettere il nome completo del dispositivo o una parte di esso. Ad esempio, per trovare il dispositivo Microfono (Microsoft LifeCam VX-1000.), è possibile immettere il nome del dispositivo completo come segue:</span><span class="sxs-lookup"><span data-stu-id="feedf-p122">Name of the capture or render device. You can enter the complete device name or any portion of the device name. For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="feedf-258">Microfono (Microsoft LifeCam VX-1000.)</span><span class="sxs-lookup"><span data-stu-id="feedf-258">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="feedf-p123">In alternativa, è possibile immettere solo una parte del nome, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="feedf-p123">Or, you can enter just a portion of the name. For example:</span></span></p>
<p><span data-ttu-id="feedf-261">LifeCam</span><span class="sxs-lookup"><span data-stu-id="feedf-261">LifeCam</span></span></p>
<p><span data-ttu-id="feedf-262">Si noti che il filtro precedente restituisce qualsiasi dispositivo che contiene la stringa &quot; LifeCam &quot; Anywhere nel relativo nome.</span><span class="sxs-lookup"><span data-stu-id="feedf-262">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="feedf-263">Metriche</span><span class="sxs-lookup"><span data-stu-id="feedf-263">Metrics</span></span>

<span data-ttu-id="feedf-264">Nella tabella seguente sono elencate le informazioni fornite nel Rapporto dispositivi.</span><span class="sxs-lookup"><span data-stu-id="feedf-264">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="feedf-265">Metriche del rapporto dispositivi</span><span class="sxs-lookup"><span data-stu-id="feedf-265">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="feedf-266">Nome</span><span class="sxs-lookup"><span data-stu-id="feedf-266">Name</span></span></th>
<th><span data-ttu-id="feedf-267">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="feedf-267">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="feedf-268">Descrizione</span><span class="sxs-lookup"><span data-stu-id="feedf-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="feedf-269"><strong>Dispositivo di acquisizione</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-269"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-270">Sì</span><span class="sxs-lookup"><span data-stu-id="feedf-270">Yes</span></span></p></td>
<td><p><span data-ttu-id="feedf-271">Dispositivo (ad esempio un microfono o una webcam) utilizzato per la trasmissione dell'audio.</span><span class="sxs-lookup"><span data-stu-id="feedf-271">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feedf-272"><strong>Dispositivo di rendering</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-272"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-273">Sì</span><span class="sxs-lookup"><span data-stu-id="feedf-273">Yes</span></span></p></td>
<td><p><span data-ttu-id="feedf-274">Dispositivo (ad esempio cuffie o altoparlanti) utilizzato per la ricezione dell'audio.</span><span class="sxs-lookup"><span data-stu-id="feedf-274">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feedf-275"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-275"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-276">Sì</span><span class="sxs-lookup"><span data-stu-id="feedf-276">Yes</span></span></p></td>
<td><p><span data-ttu-id="feedf-277">Numero totale di chiamate effettuate.</span><span class="sxs-lookup"><span data-stu-id="feedf-277">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feedf-278"><strong>Percentuale chiamate di livello insufficiente</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-278"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-279">Sì</span><span class="sxs-lookup"><span data-stu-id="feedf-279">Yes</span></span></p></td>
<td><p><span data-ttu-id="feedf-280">Percentuale di chiamate classificate di qualità &quot; scadente. &quot; Una chiamata scadente è qualsiasi chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata in cui si è verificato un eccessivo instabilità.</span><span class="sxs-lookup"><span data-stu-id="feedf-280">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feedf-281"><strong>Utenti univoci</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-281"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-282">Sì</span><span class="sxs-lookup"><span data-stu-id="feedf-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="feedf-p124">Utenti univoci che hanno utilizzato il dispositivo. Se un utente ha utilizzato 13 volte il dispositivo, verrà conteggiato come utente univoco, come un utente che ha utilizzato il dispositivo una sola volta.</span><span class="sxs-lookup"><span data-stu-id="feedf-p124">Unique users who used the device. If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feedf-285"><strong>Rapporto di tempo commutazione vocale</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-285"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-286">Sì</span><span class="sxs-lookup"><span data-stu-id="feedf-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="feedf-p125">Percentuale della chiamata che è stato necessario effettuare in modalità half-duplex per evitare l'eco. In modalità half-duplex la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo ai turni effettuati dagli utenti in una comunicazione con un walkie-talkie.</span><span class="sxs-lookup"><span data-stu-id="feedf-p125">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feedf-289"><strong>Rapporto di microfono non funzionante</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-289"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-290">Sì</span><span class="sxs-lookup"><span data-stu-id="feedf-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="feedf-p126">Percentuale della chiamata in cui il dispositivo di acquisizione non ha funzionato a un livello accettabile. Un valore elevato indica che i problemi di qualità della chiamata erano principalmente dovuti a un funzionamento improprio del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="feedf-p126">Percentage of the call in which the capture device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feedf-293"><strong>Rapporto di altoparlante non funzionante</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-293"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-294">Sì</span><span class="sxs-lookup"><span data-stu-id="feedf-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="feedf-p127">Percentuale della chiamata in cui il dispositivo di rendering non ha funzionato a un livello accettabile. Un valore elevato indica che i problemi di qualità della chiamata erano principalmente dovuti a un funzionamento improprio del dispositivo di rendering.</span><span class="sxs-lookup"><span data-stu-id="feedf-p127">Percentage of the call in which the render device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feedf-297"><strong>Chiamate con commutazione vocale (%)</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-297"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-298">Sì</span><span class="sxs-lookup"><span data-stu-id="feedf-298">Yes</span></span></p></td>
<td><p><span data-ttu-id="feedf-p128">Percentuale delle chiamate totali che è stato necessario effettuare in modalità half-duplex. In modalità half-duplex la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo ai turni effettuati dagli utenti in una comunicazione con un walkie-talkie.</span><span class="sxs-lookup"><span data-stu-id="feedf-p128">Percentage of the total calls which had to be placed into half duplex mode. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feedf-301"><strong>Eco microfono in ingresso (%)</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-301"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-302">Sì</span><span class="sxs-lookup"><span data-stu-id="feedf-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="feedf-303">Percentuale del tempo in cui è stata rilevata eco nel flusso di acquisizione del microfono.</span><span class="sxs-lookup"><span data-stu-id="feedf-303">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="feedf-304">In genere, i valori sono bassi per gli auricolari o i telefoni e sono più alti per i telefoni speaker o per gli altoparlanti autonomi.</span><span class="sxs-lookup"><span data-stu-id="feedf-304">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="feedf-305">Per i dispositivi che supportano l'annullamento dell'eco acustica di bordo, i valori elevati indicano una perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="feedf-305">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="feedf-306">Per gli altri dispositivi, questa metrica non deve essere utilizzata per valutare la qualità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="feedf-306">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feedf-307"><strong>Invio eco (%)</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-307"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-308">Sì</span><span class="sxs-lookup"><span data-stu-id="feedf-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="feedf-309">Percentuale di eco trasmesso ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="feedf-309">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feedf-310"><strong>Chiamate con eco (%)</strong></span><span class="sxs-lookup"><span data-stu-id="feedf-310"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="feedf-311">Sì</span><span class="sxs-lookup"><span data-stu-id="feedf-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="feedf-312">Percentuale delle chiamate totali con eco superiore al livello accettabile.</span><span class="sxs-lookup"><span data-stu-id="feedf-312">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

