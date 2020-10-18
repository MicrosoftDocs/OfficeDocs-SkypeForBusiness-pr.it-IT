---
title: 'Lync Server 2013: rapporto dispositivi'
description: 'Lync Server 2013: rapporto dispositivo.'
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
ms.openlocfilehash: a8bff8e973d5c3e2d96c18992a2a2d917d4deb1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575122"
---
# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="07f07-103">Report dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07f07-103">Device Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07f07-104">_**Ultimo argomento modificato:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="07f07-104">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="07f07-105">Il Rapporto dispositivi potrebbe anche essere intitolato Rapporto altoparlanti e microfono perché il Rapporto dispositivi recupera le metriche relative alle chiamate (ad esempio, la percentuale di chiamate con qualità insufficiente, l'eco e il tempo commutazione vocale) raggruppate in base ai microfoni e agli altoparlanti utilizzati nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="07f07-105">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="07f07-106">Se si è interessati ai telefoni IP (noti anche come "dispositivi"), utilizzare il [rapporto inventario telefoni IP in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) .</span><span class="sxs-lookup"><span data-stu-id="07f07-106">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="07f07-p102">Il Rapporto dispositivi è estremamente utile agli amministratori per stabilire se un tipo specifico di dispositivo riporta volumi elevati di chiamate con qualità insufficiente rispetto ad altri. Questo può influire sulle decisioni da prendere in merito all'acquisto di nuovi dispositivi o alla sostituzione dei dispositivi esistenti.</span><span class="sxs-lookup"><span data-stu-id="07f07-p102">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others. In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="07f07-p103">Per impostazione predefinita, le informazioni visualizzate nel Rapporto dispositivi si basano sul microfono (il dispositivo di acquisizione) e gli altoparlanti/auricolari (il dispositivo di rendering) utilizzati nella chiamata. Ad esempio, si supponga che vari utenti debbano utilizzare il dispositivo di acquisizione e il dispositivo di rendering seguenti:</span><span class="sxs-lookup"><span data-stu-id="07f07-p103">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="07f07-112">Dispositivo di acquisizione -- Microfono (HD Audio integrato digitale SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="07f07-112">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="07f07-113">Dispositivo di rendering -- Auricolare e microtelefono (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="07f07-113">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="07f07-114">Se gli utenti hanno eseguito un totale di 254 chiamate, nel rapporto verrà visualizzata una voce simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="07f07-114">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07f07-115">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="07f07-115">Capture device</span></span></th>
<th><span data-ttu-id="07f07-116">Dispositivo di rendering</span><span class="sxs-lookup"><span data-stu-id="07f07-116">Render device</span></span></th>
<th><span data-ttu-id="07f07-117">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="07f07-117">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07f07-118">Microfono (HD Audio integrato digitale SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="07f07-118">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="07f07-119">Auricolare e microtelefono (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="07f07-119">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="07f07-120">254</span><span class="sxs-lookup"><span data-stu-id="07f07-120">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="07f07-p104">Ora si supponga che un certo numero di utenti utilizzi lo stesso dispositivo di acquisizione ma un dispositivo di rendering diverso. In tal caso, nel report verrà visualizzata una voce nella seconda riga per tale combinazione univoca di dispositivo di acquisizione e dispositivo di rendering:</span><span class="sxs-lookup"><span data-stu-id="07f07-p104">Now, suppose you have a number of users who use that same capture device but a different render device. In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07f07-123">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="07f07-123">Capture device</span></span></th>
<th><span data-ttu-id="07f07-124">Dispositivo di rendering</span><span class="sxs-lookup"><span data-stu-id="07f07-124">Render device</span></span></th>
<th><span data-ttu-id="07f07-125">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="07f07-125">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07f07-126">Microfono (HD Audio integrato digitale SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="07f07-126">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="07f07-127">Auricolare e microtelefono (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="07f07-127">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="07f07-128">254</span><span class="sxs-lookup"><span data-stu-id="07f07-128">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f07-129">Microfono (HD Audio integrato digitale SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="07f07-129">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="07f07-130">Altoparlanti (HD Audio integrato digitale SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="07f07-130">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="07f07-131">319</span><span class="sxs-lookup"><span data-stu-id="07f07-131">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="07f07-p105">Se si desidera visualizzare i totali combinati per un determinato dispositivo (ad esempio, per il dispositivo di acquisizione SoundMAX, indipendentemente dal dispositivo di rendering utilizzato), selezionare l'opzione appropriata dall'elenco a discesa Tipo di dispositivo (Dispositivo di acquisizione o Dispositivo di rendering). Se nell'esempio si seleziona Dispositivo di acquisizione, si riceverà il seguente output:</span><span class="sxs-lookup"><span data-stu-id="07f07-p105">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device). If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07f07-134">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="07f07-134">Capture device</span></span></th>
<th><span data-ttu-id="07f07-135">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="07f07-135">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07f07-136">Microfono (HD Audio integrato digitale SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="07f07-136">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="07f07-137">573</span><span class="sxs-lookup"><span data-stu-id="07f07-137">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="07f07-138">Accesso al Rapporto dispositivi</span><span class="sxs-lookup"><span data-stu-id="07f07-138">Accessing the Device Report</span></span>

<span data-ttu-id="07f07-139">In genere è possibile accedere al Rapporto dispositivi dalla home page Relazioni monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="07f07-139">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="07f07-140">Tuttavia, se si sta visualizzando il [rapporto dettagli chiamata in Lync Server 2013](lync-server-2013-call-detail-report.md) , è possibile eseguire il drill-down nel rapporto dispositivo per un dispositivo specifico facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="07f07-140">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="07f07-141">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="07f07-141">Capture Device</span></span>

  - <span data-ttu-id="07f07-142">Dispositivo di rendering</span><span class="sxs-lookup"><span data-stu-id="07f07-142">Render Device</span></span>

<span data-ttu-id="07f07-143">Dal rapporto dispositivo è possibile eseguire il drill-down [nel rapporto elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="07f07-143">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="07f07-144">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="07f07-144">Call volume</span></span>

  - <span data-ttu-id="07f07-145">Percentuale chiamate di livello insufficiente</span><span class="sxs-lookup"><span data-stu-id="07f07-145">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="07f07-146">Utilizzo del Rapporto dispositivi</span><span class="sxs-lookup"><span data-stu-id="07f07-146">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="07f07-147">Il Rapporto dispositivi è molto dettagliato in merito ai nomi dei dispositivi. Ad esempio, si supponga di disporre dei dispositivi di acquisizione seguenti:</span><span class="sxs-lookup"><span data-stu-id="07f07-147">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="07f07-148">Microfono Aastra 3002 (2- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="07f07-148">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="07f07-149">Microfono Aastra 3002 (3- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="07f07-149">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="07f07-150">Microfono Aastra 3002 (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="07f07-150">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="07f07-151">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="07f07-151">Aastra 6725ip</span></span>

  - <span data-ttu-id="07f07-152">Microfono Aastra 6725ip (10- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="07f07-152">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="07f07-153">Microfono Aastra 6725ip (10- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="07f07-153">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="07f07-154">Microfono Aastra 6725ip (2- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="07f07-154">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="07f07-155">Microfono Aastra 6725ip (3- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="07f07-155">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="07f07-156">Microfono Aastra 6725ip (4- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="07f07-156">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="07f07-157">Microfono Aastra 6725ip (5- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="07f07-157">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="07f07-158">Microfono Aastra 6725ip (6- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="07f07-158">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="07f07-159">Microfono Aastra 6725ip (7- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="07f07-159">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="07f07-160">Microfono Aastra 6725ip (9- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="07f07-160">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="07f07-161">Microfono Aastra 6725ip (9- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="07f07-161">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="07f07-162">Microfono Aastra 6725ip (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="07f07-162">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="07f07-163">Microfono Aastra 6725ip (Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="07f07-163">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="07f07-164">Microfono Aastra 6725ip (dispositivo audio USB)</span><span class="sxs-lookup"><span data-stu-id="07f07-164">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="07f07-165">Microfono Aastra 6725ip (dispositivo audio USB)-V0</span><span class="sxs-lookup"><span data-stu-id="07f07-165">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07f07-166">Tenere presente che i nomi dei dispositivi di acquisizione potrebbero non essere uguali se si eseguono versioni localizzate di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="07f07-166">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="07f07-167">Un dispositivo denominato Aastra 6725ip Microphone (Aastra 6725ip)-V0 in inglese (Stati Uniti) potrebbe avere un nome diverso in francese o spagnolo.</span><span class="sxs-lookup"><span data-stu-id="07f07-167">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="07f07-168">Anche se spesso è utile questo livello di dettaglio, a volte si potrebbe essere interessati solo al numero di chiamate che utilizzano qualsiasi microfono Aastra, indipendentemente dal numero del modello.</span><span class="sxs-lookup"><span data-stu-id="07f07-168">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="07f07-169">Un modo per ottenere informazioni di questo tipo consiste nell'esportare i dati del report del dispositivo in Microsoft Excel e quindi salvarli in un file con valori delimitati da virgole (ad esempio, C: \\ data \\ devices \_Report.csv).</span><span class="sxs-lookup"><span data-stu-id="07f07-169">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="07f07-170">È possibile utilizzare un insieme di comandi simili a questi per importare il file CSV in Windows PowerShell e restituire il numero totale di chiamate eseguite utilizzando un dispositivo di acquisizione Aastra:</span><span class="sxs-lookup"><span data-stu-id="07f07-170">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="07f07-p109">Verrà restituito un unico valore che rappresenta il numero totale di chiamate eseguite utilizzando un dispositivo di acquisizione Aastra. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="07f07-p109">That will return a single value representing the total number of calls made using an Aastra capture device. For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="07f07-173">Filtri</span><span class="sxs-lookup"><span data-stu-id="07f07-173">Filters</span></span>

<span data-ttu-id="07f07-p110">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il Rapporto dispositivi consente di filtrare in base a elementi quali il tipo di chiamata (ossia se la chiamata è di tipo client) una conferenza telefonica o una chiamata PSTN (Public Switched Telephone Network). È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso i dispositivi sono raggruppabili per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="07f07-p110">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call. You can also choose how data should be grouped. In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="07f07-178">Nella tabella seguente sono elencati i filtri applicabili al Rapporto dispositivi.</span><span class="sxs-lookup"><span data-stu-id="07f07-178">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="07f07-179">Filtri del Rapporto dispositivi</span><span class="sxs-lookup"><span data-stu-id="07f07-179">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07f07-180">Nome</span><span class="sxs-lookup"><span data-stu-id="07f07-180">Name</span></span></th>
<th><span data-ttu-id="07f07-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07f07-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07f07-182"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-182"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-p111">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="07f07-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="07f07-185">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="07f07-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="07f07-p112">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="07f07-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="07f07-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="07f07-188">7/7/2012</span></span></p>
<p><span data-ttu-id="07f07-189">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="07f07-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="07f07-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="07f07-190">7/3/2012</span></span></p>
<p><span data-ttu-id="07f07-191">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="07f07-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f07-192"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-192"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-p113">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="07f07-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="07f07-195">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="07f07-195">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="07f07-p114">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="07f07-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="07f07-198">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="07f07-198">7/7/2012</span></span></p>
<p><span data-ttu-id="07f07-199">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="07f07-199">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="07f07-200">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="07f07-200">7/3/2012</span></span></p>
<p><span data-ttu-id="07f07-201">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="07f07-201">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f07-202"><strong>Causa commutazione vocale</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-202"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-p115">Motivo per cui è stato necessario effettuare una chiamata in modalità half-duplex per evitare l'eco. In modalità half-duplex la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo ai turni effettuati dagli utenti in una comunicazione con un walkie-talkie. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07f07-p115">Reason why a call had to be placed into half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-206">Tutti</span><span class="sxs-lookup"><span data-stu-id="07f07-206">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-207">Nessuno</span><span class="sxs-lookup"><span data-stu-id="07f07-207">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-208">Timestamp non valido</span><span class="sxs-lookup"><span data-stu-id="07f07-208">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-209">Echo</span><span class="sxs-lookup"><span data-stu-id="07f07-209">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-210">DNLP (dynamic nonlinear processor)</span><span class="sxs-lookup"><span data-stu-id="07f07-210">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-211">Complessità bassa</span><span class="sxs-lookup"><span data-stu-id="07f07-211">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-212">Stato dispositivo non valido</span><span class="sxs-lookup"><span data-stu-id="07f07-212">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-213">Eco dopo eliminazione eco acustica</span><span class="sxs-lookup"><span data-stu-id="07f07-213">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f07-214"><strong>Causa eco</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-214"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-p116">Motivo per cui in una chiamata è stato rilevato l'eco sopra il livello accettato (nelle telecomunicazioni l'eco è un riflesso del suono, lo stesso effetto che si produce gridando verso il fondo di un pozzo). Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07f07-p116">Reason why echo above the accepted level was detected in a call. (In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-217">Tutti</span><span class="sxs-lookup"><span data-stu-id="07f07-217">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-218">Nessuno</span><span class="sxs-lookup"><span data-stu-id="07f07-218">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-219">Timestamp non valido</span><span class="sxs-lookup"><span data-stu-id="07f07-219">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-220">Eco dopo eliminazione eco acustica</span><span class="sxs-lookup"><span data-stu-id="07f07-220">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-221">ANLP (adaptive nonlinear processor)</span><span class="sxs-lookup"><span data-stu-id="07f07-221">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-222">DNLP (dynamic nonlinear processor)</span><span class="sxs-lookup"><span data-stu-id="07f07-222">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-223">Clip microfono</span><span class="sxs-lookup"><span data-stu-id="07f07-223">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f07-224"><strong>Tipo di chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-224"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-p117">Indica il tipo di chiamata effettuata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07f07-p117">Indicates the type of call that was made. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-227">Tutti</span><span class="sxs-lookup"><span data-stu-id="07f07-227">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-228">Chiamata client</span><span class="sxs-lookup"><span data-stu-id="07f07-228">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-229">Chiamata PSTN</span><span class="sxs-lookup"><span data-stu-id="07f07-229">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-230">Conferenza telefonica</span><span class="sxs-lookup"><span data-stu-id="07f07-230">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f07-231"><strong>Tipo di accesso</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-231"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-p118">Indica se al momento dell'esecuzione della chiamata il client era connesso alla rete interna o alla rete esterna. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07f07-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-234">Tutti</span><span class="sxs-lookup"><span data-stu-id="07f07-234">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-235">Interno</span><span class="sxs-lookup"><span data-stu-id="07f07-235">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-236">Esterno</span><span class="sxs-lookup"><span data-stu-id="07f07-236">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f07-237"><strong>Tipo di rete</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-237"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-p119">Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07f07-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-240">Tutti</span><span class="sxs-lookup"><span data-stu-id="07f07-240">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-241">Cablata</span><span class="sxs-lookup"><span data-stu-id="07f07-241">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-242">Wireless</span><span class="sxs-lookup"><span data-stu-id="07f07-242">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f07-243"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-243"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-p120">Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07f07-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-246">Tutti</span><span class="sxs-lookup"><span data-stu-id="07f07-246">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-247">VPN</span><span class="sxs-lookup"><span data-stu-id="07f07-247">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-248">Non VPN</span><span class="sxs-lookup"><span data-stu-id="07f07-248">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f07-249"><strong>Tipo di dispositivo</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-249"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-p121">Indica il tipo di dispositivo. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07f07-p121">Indicates the type of device. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-252">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="07f07-252">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-253">Dispositivo di rendering</span><span class="sxs-lookup"><span data-stu-id="07f07-253">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="07f07-254">Coppia di dispositivi di acquisizione/rendering</span><span class="sxs-lookup"><span data-stu-id="07f07-254">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f07-255"><strong>Nome dispositivo</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-255"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-p122">Nome del dispositivo di acquisizione o di rendering. È possibile immettere il nome completo del dispositivo o una parte di esso. Ad esempio, per trovare il dispositivo Microfono (Microsoft LifeCam VX-1000.), è possibile immettere il nome del dispositivo completo come segue:</span><span class="sxs-lookup"><span data-stu-id="07f07-p122">Name of the capture or render device. You can enter the complete device name or any portion of the device name. For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="07f07-259">Microfono (Microsoft LifeCam VX-1000.)</span><span class="sxs-lookup"><span data-stu-id="07f07-259">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="07f07-p123">In alternativa, è possibile immettere solo una parte del nome, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="07f07-p123">Or, you can enter just a portion of the name. For example:</span></span></p>
<p><span data-ttu-id="07f07-262">LifeCam</span><span class="sxs-lookup"><span data-stu-id="07f07-262">LifeCam</span></span></p>
<p><span data-ttu-id="07f07-263">Si noti che il filtro precedente restituisce qualsiasi dispositivo che contiene la stringa &quot; LifeCam &quot; Anywhere nel relativo nome.</span><span class="sxs-lookup"><span data-stu-id="07f07-263">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="07f07-264">Metriche</span><span class="sxs-lookup"><span data-stu-id="07f07-264">Metrics</span></span>

<span data-ttu-id="07f07-265">Nella tabella seguente sono elencate le informazioni fornite nel Rapporto dispositivi.</span><span class="sxs-lookup"><span data-stu-id="07f07-265">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="07f07-266">Metriche del rapporto dispositivi</span><span class="sxs-lookup"><span data-stu-id="07f07-266">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07f07-267">Nome</span><span class="sxs-lookup"><span data-stu-id="07f07-267">Name</span></span></th>
<th><span data-ttu-id="07f07-268">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="07f07-268">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="07f07-269">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07f07-269">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07f07-270"><strong>Dispositivo di acquisizione</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-270"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-271">Sì</span><span class="sxs-lookup"><span data-stu-id="07f07-271">Yes</span></span></p></td>
<td><p><span data-ttu-id="07f07-272">Dispositivo (ad esempio un microfono o una webcam) utilizzato per la trasmissione dell'audio.</span><span class="sxs-lookup"><span data-stu-id="07f07-272">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f07-273"><strong>Dispositivo di rendering</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-273"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-274">Sì</span><span class="sxs-lookup"><span data-stu-id="07f07-274">Yes</span></span></p></td>
<td><p><span data-ttu-id="07f07-275">Dispositivo (ad esempio cuffie o altoparlanti) utilizzato per la ricezione dell'audio.</span><span class="sxs-lookup"><span data-stu-id="07f07-275">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f07-276"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-276"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-277">Sì</span><span class="sxs-lookup"><span data-stu-id="07f07-277">Yes</span></span></p></td>
<td><p><span data-ttu-id="07f07-278">Numero totale di chiamate effettuate.</span><span class="sxs-lookup"><span data-stu-id="07f07-278">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f07-279"><strong>Percentuale chiamate di livello insufficiente</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-279"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-280">Sì</span><span class="sxs-lookup"><span data-stu-id="07f07-280">Yes</span></span></p></td>
<td><p><span data-ttu-id="07f07-281">Percentuale di chiamate classificate di qualità &quot; scadente. &quot; Una chiamata scadente è qualsiasi chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata in cui si è verificato un eccessivo instabilità.</span><span class="sxs-lookup"><span data-stu-id="07f07-281">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f07-282"><strong>Utenti univoci</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-282"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-283">Sì</span><span class="sxs-lookup"><span data-stu-id="07f07-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="07f07-p124">Utenti univoci che hanno utilizzato il dispositivo. Se un utente ha utilizzato 13 volte il dispositivo, verrà conteggiato come utente univoco, come un utente che ha utilizzato il dispositivo una sola volta.</span><span class="sxs-lookup"><span data-stu-id="07f07-p124">Unique users who used the device. If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f07-286"><strong>Rapporto di tempo commutazione vocale</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-286"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-287">Sì</span><span class="sxs-lookup"><span data-stu-id="07f07-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="07f07-p125">Percentuale della chiamata che è stato necessario effettuare in modalità half-duplex per evitare l'eco. In modalità half-duplex la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo ai turni effettuati dagli utenti in una comunicazione con un walkie-talkie.</span><span class="sxs-lookup"><span data-stu-id="07f07-p125">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f07-290"><strong>Rapporto di microfono non funzionante</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-290"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-291">Sì</span><span class="sxs-lookup"><span data-stu-id="07f07-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="07f07-p126">Percentuale della chiamata in cui il dispositivo di acquisizione non ha funzionato a un livello accettabile. Un valore elevato indica che i problemi di qualità della chiamata erano principalmente dovuti a un funzionamento improprio del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="07f07-p126">Percentage of the call in which the capture device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f07-294"><strong>Rapporto di altoparlante non funzionante</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-294"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-295">Sì</span><span class="sxs-lookup"><span data-stu-id="07f07-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="07f07-p127">Percentuale della chiamata in cui il dispositivo di rendering non ha funzionato a un livello accettabile. Un valore elevato indica che i problemi di qualità della chiamata erano principalmente dovuti a un funzionamento improprio del dispositivo di rendering.</span><span class="sxs-lookup"><span data-stu-id="07f07-p127">Percentage of the call in which the render device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f07-298"><strong>Chiamate con commutazione vocale (%)</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-298"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-299">Sì</span><span class="sxs-lookup"><span data-stu-id="07f07-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="07f07-p128">Percentuale delle chiamate totali che è stato necessario effettuare in modalità half-duplex. In modalità half-duplex la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo ai turni effettuati dagli utenti in una comunicazione con un walkie-talkie.</span><span class="sxs-lookup"><span data-stu-id="07f07-p128">Percentage of the total calls which had to be placed into half duplex mode. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f07-302"><strong>Eco microfono in ingresso (%)</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-302"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-303">Sì</span><span class="sxs-lookup"><span data-stu-id="07f07-303">Yes</span></span></p></td>
<td><p><span data-ttu-id="07f07-304">Percentuale del tempo in cui è stata rilevata eco nel flusso di acquisizione del microfono.</span><span class="sxs-lookup"><span data-stu-id="07f07-304">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="07f07-305">In genere, i valori sono bassi per gli auricolari o i telefoni e sono più alti per i telefoni speaker o per gli altoparlanti autonomi.</span><span class="sxs-lookup"><span data-stu-id="07f07-305">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="07f07-306">Per i dispositivi che supportano l'annullamento dell'eco acustica di bordo, i valori elevati indicano una perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="07f07-306">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="07f07-307">Per gli altri dispositivi, questa metrica non deve essere utilizzata per valutare la qualità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="07f07-307">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f07-308"><strong>Invio eco (%)</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-308"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-309">Sì</span><span class="sxs-lookup"><span data-stu-id="07f07-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="07f07-310">Percentuale di eco trasmesso ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="07f07-310">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f07-311"><strong>Chiamate con eco (%)</strong></span><span class="sxs-lookup"><span data-stu-id="07f07-311"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="07f07-312">Sì</span><span class="sxs-lookup"><span data-stu-id="07f07-312">Yes</span></span></p></td>
<td><p><span data-ttu-id="07f07-313">Percentuale delle chiamate totali con eco superiore al livello accettabile.</span><span class="sxs-lookup"><span data-stu-id="07f07-313">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

