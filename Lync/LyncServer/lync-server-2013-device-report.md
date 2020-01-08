---
title: 'Lync Server 2013: report dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e172837622c4ad40a29cca74dcaf42497c4b2bd5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="2d498-102">Report dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d498-102">Device Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d498-103">_**Argomento Ultima modifica:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="2d498-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="2d498-104">Il report del dispositivo potrebbe essere meglio intitolato il rapporto microfono e altoparlanti; Questo perché il report del dispositivo recupera le metriche correlate alle chiamate, ad esempio la percentuale di chiamata scadente, l'eco e il tempo di cambio vocale, raggruppate per i microfoni e gli altoparlanti usati nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="2d498-104">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="2d498-105">Se si è interessati ai telefoni IP (detti anche "dispositivi"), usare invece il report sull' [inventario dei telefoni IP in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) .</span><span class="sxs-lookup"><span data-stu-id="2d498-105">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="2d498-106">Il report del dispositivo è estremamente utile per gli amministratori per determinare se un determinato tipo di dispositivo sta vivendo alti volumi di chiamate di qualità scadente rispetto ad altri.</span><span class="sxs-lookup"><span data-stu-id="2d498-106">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others.</span></span> <span data-ttu-id="2d498-107">A sua volta, questo potrebbe influenzare qualsiasi decisione da apportare quando arriva il momento di acquistare nuovi dispositivi o di sostituire i dispositivi esistenti.</span><span class="sxs-lookup"><span data-stu-id="2d498-107">In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="2d498-108">Per impostazione predefinita, le informazioni visualizzate nel report del dispositivo si basano anche sul microfono (il dispositivo di acquisizione) e gli altoparlanti/auricolare (il dispositivo di rendering) usati nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="2d498-108">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call.</span></span> <span data-ttu-id="2d498-109">Supponi ad esempio di avere diversi utenti che usano il dispositivo di acquisizione seguente e il dispositivo di rendering seguente: per impostazione predefinita, le informazioni visualizzate nel report del dispositivo si basano anche sul microfono (il dispositivo di acquisizione) e gli altoparlanti/auricolare (il dispositivo di rendering) usati nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="2d498-109">For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call.</span></span> <span data-ttu-id="2d498-110">Supponi ad esempio di avere diversi utenti che usano il dispositivo di acquisizione seguente e il dispositivo di rendering seguente:</span><span class="sxs-lookup"><span data-stu-id="2d498-110">For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="2d498-111">Dispositivo di acquisizione: microfono (SoundMAX Integrated Digital HD audio)</span><span class="sxs-lookup"><span data-stu-id="2d498-111">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="2d498-112">Dispositivo di rendering: auricolare Headset (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="2d498-112">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="2d498-113">Se gli utenti hanno apportato un totale di 254 chiamate, nel report verrà visualizzata una voce simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="2d498-113">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d498-114">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="2d498-114">Capture device</span></span></th>
<th><span data-ttu-id="2d498-115">Dispositivo di rendering</span><span class="sxs-lookup"><span data-stu-id="2d498-115">Render device</span></span></th>
<th><span data-ttu-id="2d498-116">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="2d498-116">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d498-117">Microfono (SoundMAX Integrated Digital audio HD)</span><span class="sxs-lookup"><span data-stu-id="2d498-117">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="2d498-118">Auricolare (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="2d498-118">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="2d498-119">254</span><span class="sxs-lookup"><span data-stu-id="2d498-119">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2d498-120">Supponiamo che tu abbia un certo numero di utenti che usano lo stesso dispositivo di acquisizione, ma un dispositivo di rendering diverso.</span><span class="sxs-lookup"><span data-stu-id="2d498-120">Now, suppose you have a number of users who use that same capture device but a different render device.</span></span> <span data-ttu-id="2d498-121">In questo caso, nel report verrà visualizzata una seconda voce, una per la combinazione univoca di dispositivo di acquisizione e dispositivo di rendering:</span><span class="sxs-lookup"><span data-stu-id="2d498-121">In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d498-122">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="2d498-122">Capture device</span></span></th>
<th><span data-ttu-id="2d498-123">Dispositivo di rendering</span><span class="sxs-lookup"><span data-stu-id="2d498-123">Render device</span></span></th>
<th><span data-ttu-id="2d498-124">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="2d498-124">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d498-125">Microfono (SoundMAX Integrated Digital audio HD)</span><span class="sxs-lookup"><span data-stu-id="2d498-125">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="2d498-126">Auricolare (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="2d498-126">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="2d498-127">254</span><span class="sxs-lookup"><span data-stu-id="2d498-127">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d498-128">Microfono (SoundMAX Integrated Digital audio HD)</span><span class="sxs-lookup"><span data-stu-id="2d498-128">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="2d498-129">Altoparlanti (SoundMAX Integrated Digital HD audio)</span><span class="sxs-lookup"><span data-stu-id="2d498-129">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="2d498-130">319</span><span class="sxs-lookup"><span data-stu-id="2d498-130">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2d498-131">Se si preferisce visualizzare i totali combinati per un dispositivo specifico, ad esempio per il dispositivo di acquisizione SoundMAX, indipendentemente dal dispositivo di rendering usato, selezionare l'opzione appropriata nell'elenco a discesa tipo di dispositivo (dispositivo di acquisizione o dispositivo di rendering).</span><span class="sxs-lookup"><span data-stu-id="2d498-131">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device).</span></span> <span data-ttu-id="2d498-132">Se si seleziona dispositivo di acquisizione in questo esempio, verrà restituito un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="2d498-132">If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d498-133">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="2d498-133">Capture device</span></span></th>
<th><span data-ttu-id="2d498-134">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="2d498-134">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d498-135">Microfono (SoundMAX Integrated Digital audio HD)</span><span class="sxs-lookup"><span data-stu-id="2d498-135">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="2d498-136">573</span><span class="sxs-lookup"><span data-stu-id="2d498-136">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="2d498-137">Accesso al report del dispositivo</span><span class="sxs-lookup"><span data-stu-id="2d498-137">Accessing the Device Report</span></span>

<span data-ttu-id="2d498-138">Il report del dispositivo è in genere accessibile dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="2d498-138">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="2d498-139">Se tuttavia si sta visualizzando il [report dettagli chiamata in Lync Server 2013](lync-server-2013-call-detail-report.md) , è possibile eseguire il drill-down per il report del dispositivo per un dispositivo specifico facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d498-139">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="2d498-140">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="2d498-140">Capture Device</span></span>

  - <span data-ttu-id="2d498-141">Dispositivo di rendering</span><span class="sxs-lookup"><span data-stu-id="2d498-141">Render Device</span></span>

<span data-ttu-id="2d498-142">Nel report del dispositivo è possibile eseguire il drill-down [nel report elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d498-142">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="2d498-143">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="2d498-143">Call volume</span></span>

  - <span data-ttu-id="2d498-144">Percentuale di chiamata scadente</span><span class="sxs-lookup"><span data-stu-id="2d498-144">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="2d498-145">Sfruttare al meglio il report del dispositivo</span><span class="sxs-lookup"><span data-stu-id="2d498-145">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="2d498-146">Quando si tratta di nomi di dispositivi, il report del dispositivo è estremamente dettagliato; Supponiamo ad esempio di avere i seguenti dispositivi di acquisizione:</span><span class="sxs-lookup"><span data-stu-id="2d498-146">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="2d498-147">Aastra 3002 microfono (2-Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="2d498-147">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="2d498-148">Aastra 3002 microfono (3-Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="2d498-148">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="2d498-149">Aastra 3002 microfono (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="2d498-149">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="2d498-150">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="2d498-150">Aastra 6725ip</span></span>

  - <span data-ttu-id="2d498-151">Microfono 6725ip Aastra (10-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2d498-151">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="2d498-152">Microfono 6725ip Aastra (10-Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="2d498-152">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="2d498-153">Microfono 6725ip Aastra (2-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2d498-153">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="2d498-154">Microfono 6725ip Aastra (3-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2d498-154">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="2d498-155">Microfono 6725ip Aastra (4-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2d498-155">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="2d498-156">Microfono 6725ip Aastra (5-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2d498-156">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="2d498-157">Microfono 6725ip Aastra (6-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2d498-157">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="2d498-158">Microfono 6725ip Aastra (7-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2d498-158">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="2d498-159">Microfono 6725ip Aastra (9-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2d498-159">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="2d498-160">Microfono 6725ip Aastra (9-Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="2d498-160">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="2d498-161">Microfono 6725ip Aastra (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2d498-161">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="2d498-162">Microfono 6725ip Aastra (Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="2d498-162">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="2d498-163">Microfono 6725ip Aastra (dispositivo audio USB)</span><span class="sxs-lookup"><span data-stu-id="2d498-163">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="2d498-164">Microfono 6725ip Aastra (dispositivo audio USB)-V0</span><span class="sxs-lookup"><span data-stu-id="2d498-164">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2d498-165">Tieni presente che i nomi dei dispositivi di acquisizione potrebbero non essere uguali se Esegui versioni localizzate di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d498-165">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="2d498-166">Un dispositivo denominato Aastra 6725ip Microphone (Aastra 6725ip)-V0 in inglese USA potrebbe avere un nome diverso in francese o spagnolo.</span><span class="sxs-lookup"><span data-stu-id="2d498-166">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="2d498-167">Spesso si vorrà questo livello di dettaglio; in altri casi, tuttavia, potresti essere interessato al numero di chiamate che usano qualsiasi microfono Aastra, indipendentemente dal tipo di modello.</span><span class="sxs-lookup"><span data-stu-id="2d498-167">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="2d498-168">Un modo per ottenere informazioni come questo consiste nell'esportare i dati del report del dispositivo in Microsoft Excel e quindi salvare i dati in un file con valori separati da virgola, ad\\esempio\\C\_: data Devices report. csv.</span><span class="sxs-lookup"><span data-stu-id="2d498-168">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="2d498-169">Puoi quindi usare un set di comandi simili a questi per importare. File CSV in Windows PowerShell e riportare il numero totale di chiamate effettuate con un dispositivo di acquisizione Aastra:</span><span class="sxs-lookup"><span data-stu-id="2d498-169">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="2d498-170">Questo restituirà un singolo valore che rappresenta il numero totale di chiamate effettuate con un dispositivo di acquisizione di Aastra.</span><span class="sxs-lookup"><span data-stu-id="2d498-170">That will return a single value representing the total number of calls made using an Aastra capture device.</span></span> <span data-ttu-id="2d498-171">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2d498-171">For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2d498-172">Filtri</span><span class="sxs-lookup"><span data-stu-id="2d498-172">Filters</span></span>

<span data-ttu-id="2d498-173">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="2d498-173">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="2d498-174">Ad esempio, il report dispositivo consente di filtrare in base a elementi come il tipo di chiamata, ovvero la chiamata a una chiamata client, una conferenza telefonica o una chiamata PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="2d498-174">For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call.</span></span> <span data-ttu-id="2d498-175">È anche possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="2d498-175">You can also choose how data should be grouped.</span></span> <span data-ttu-id="2d498-176">In questo caso, i dispositivi vengono raggruppati per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="2d498-176">In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="2d498-177">Nella tabella seguente sono elencati i filtri che è possibile usare con il report del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2d498-177">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="2d498-178">Filtri di report per dispositivi</span><span class="sxs-lookup"><span data-stu-id="2d498-178">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d498-179">Nome</span><span class="sxs-lookup"><span data-stu-id="2d498-179">Name</span></span></th>
<th><span data-ttu-id="2d498-180">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d498-180">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d498-181"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-181"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-182">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="2d498-182">Start date/time for the time range.</span></span> <span data-ttu-id="2d498-183">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2d498-183">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2d498-184">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2d498-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2d498-185">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="2d498-185">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="2d498-186">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="2d498-186">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2d498-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2d498-187">7/7/2012</span></span></p>
<p><span data-ttu-id="2d498-188">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="2d498-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2d498-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2d498-189">7/3/2012</span></span></p>
<p><span data-ttu-id="2d498-190">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="2d498-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d498-191"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-191"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-192">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="2d498-192">End date/time for the time range.</span></span> <span data-ttu-id="2d498-193">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2d498-193">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2d498-194">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2d498-194">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2d498-195">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="2d498-195">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="2d498-196">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="2d498-196">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2d498-197">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2d498-197">7/7/2012</span></span></p>
<p><span data-ttu-id="2d498-198">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="2d498-198">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2d498-199">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2d498-199">7/3/2012</span></span></p>
<p><span data-ttu-id="2d498-200">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="2d498-200">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d498-201"><strong>Causa interruttore vocale</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-201"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-202">Motivo per cui una chiamata deve essere inserita in modalità half duplex per evitare l'eco.</span><span class="sxs-lookup"><span data-stu-id="2d498-202">Reason why a call had to be placed into half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="2d498-203">In modalità half duplex, la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo a quando gli utenti si alternano quando comunicano con un walkie-talkie.</span><span class="sxs-lookup"><span data-stu-id="2d498-203">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span> <span data-ttu-id="2d498-204">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d498-204">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-205">Tutti</span><span class="sxs-lookup"><span data-stu-id="2d498-205">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-206">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2d498-206">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-207">Timestamp errato</span><span class="sxs-lookup"><span data-stu-id="2d498-207">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-208">Echo</span><span class="sxs-lookup"><span data-stu-id="2d498-208">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-209">DNLP (Dynamic Nonlinear Processor)</span><span class="sxs-lookup"><span data-stu-id="2d498-209">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-210">Bassa complessità</span><span class="sxs-lookup"><span data-stu-id="2d498-210">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-211">Stato del dispositivo non valido</span><span class="sxs-lookup"><span data-stu-id="2d498-211">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-212">Echo post-AEC (annullamento dell'eco acustica)</span><span class="sxs-lookup"><span data-stu-id="2d498-212">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d498-213"><strong>Causa eco</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-213"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-214">Motivo per cui l'eco sopra il livello accettato è stato rilevato in una chiamata.</span><span class="sxs-lookup"><span data-stu-id="2d498-214">Reason why echo above the accepted level was detected in a call.</span></span> <span data-ttu-id="2d498-215">(In telecomunicazioni Echo è un riflesso del suono, lo stesso fenomeno che si sente se si urla in fondo a un pozzo). Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d498-215">(In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-216">Tutti</span><span class="sxs-lookup"><span data-stu-id="2d498-216">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-217">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2d498-217">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-218">Timestamp errato</span><span class="sxs-lookup"><span data-stu-id="2d498-218">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-219">Echo post-AEC (annullamento dell'eco acustica)</span><span class="sxs-lookup"><span data-stu-id="2d498-219">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-220">ANLP (processore nonlineare adattivo)</span><span class="sxs-lookup"><span data-stu-id="2d498-220">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-221">DNLP (Dynamic Nonlinear Processor)</span><span class="sxs-lookup"><span data-stu-id="2d498-221">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-222">Ritaglio del microfono</span><span class="sxs-lookup"><span data-stu-id="2d498-222">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d498-223"><strong>Tipo di chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-223"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-224">Indica il tipo di chiamata effettuata.</span><span class="sxs-lookup"><span data-stu-id="2d498-224">Indicates the type of call that was made.</span></span> <span data-ttu-id="2d498-225">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d498-225">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-226">Tutti</span><span class="sxs-lookup"><span data-stu-id="2d498-226">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-227">Chiamata client</span><span class="sxs-lookup"><span data-stu-id="2d498-227">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-228">Chiamata PSTN</span><span class="sxs-lookup"><span data-stu-id="2d498-228">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-229">Conferenza telefonica</span><span class="sxs-lookup"><span data-stu-id="2d498-229">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d498-230"><strong>Tipo di accesso</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-230"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-231">Indica se il client ha effettuato l'accesso alla rete interna o alla rete esterna quando è stata inserita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2d498-231">Indicates whether the client was logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="2d498-232">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d498-232">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-233">Tutti</span><span class="sxs-lookup"><span data-stu-id="2d498-233">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-234">Interno</span><span class="sxs-lookup"><span data-stu-id="2d498-234">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-235">Esterno</span><span class="sxs-lookup"><span data-stu-id="2d498-235">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d498-236"><strong>Tipo di rete</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-236"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-237">Indica il tipo di rete a cui il client è connesso quando è stata inserita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2d498-237">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="2d498-238">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d498-238">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-239">Tutti</span><span class="sxs-lookup"><span data-stu-id="2d498-239">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-240">Cablata</span><span class="sxs-lookup"><span data-stu-id="2d498-240">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-241">Wireless</span><span class="sxs-lookup"><span data-stu-id="2d498-241">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d498-242"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-242"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-243">Indica se un client esterno usa una connessione VPN (Virtual Private Network) quando la chiamata è stata inserita.</span><span class="sxs-lookup"><span data-stu-id="2d498-243">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="2d498-244">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d498-244">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-245">Tutti</span><span class="sxs-lookup"><span data-stu-id="2d498-245">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-246">VPN</span><span class="sxs-lookup"><span data-stu-id="2d498-246">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-247">Non VPN</span><span class="sxs-lookup"><span data-stu-id="2d498-247">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d498-248"><strong>Tipo di dispositivo</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-248"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-249">Indica il tipo di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2d498-249">Indicates the type of device.</span></span> <span data-ttu-id="2d498-250">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d498-250">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-251">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="2d498-251">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-252">Dispositivo di rendering</span><span class="sxs-lookup"><span data-stu-id="2d498-252">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2d498-253">Coppia di dispositivi di acquisizione/rendering</span><span class="sxs-lookup"><span data-stu-id="2d498-253">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d498-254"><strong>Nome dispositivo</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-254"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-255">Nome del dispositivo di acquisizione o rendering.</span><span class="sxs-lookup"><span data-stu-id="2d498-255">Name of the capture or render device.</span></span> <span data-ttu-id="2d498-256">È possibile immettere il nome completo del dispositivo o qualsiasi parte del nome del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2d498-256">You can enter the complete device name or any portion of the device name.</span></span> <span data-ttu-id="2d498-257">Ad esempio, per trovare il microfono del dispositivo (Microsoft LifeCam VX-1000.), è possibile immettere il nome completo del dispositivo nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="2d498-257">For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="2d498-258">Microfono (Microsoft LifeCam VX-1000.)</span><span class="sxs-lookup"><span data-stu-id="2d498-258">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="2d498-259">In alternativa, è possibile immettere solo una parte del nome.</span><span class="sxs-lookup"><span data-stu-id="2d498-259">Or, you can enter just a portion of the name.</span></span> <span data-ttu-id="2d498-260">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2d498-260">For example:</span></span></p>
<p><span data-ttu-id="2d498-261">LifeCam</span><span class="sxs-lookup"><span data-stu-id="2d498-261">LifeCam</span></span></p>
<p><span data-ttu-id="2d498-262">Tieni presente che il filtro precedente restituisce qualsiasi dispositivo che contiene la &quot;stringa&quot; LifeCam in qualsiasi punto del suo nome.</span><span class="sxs-lookup"><span data-stu-id="2d498-262">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="2d498-263">Metriche</span><span class="sxs-lookup"><span data-stu-id="2d498-263">Metrics</span></span>

<span data-ttu-id="2d498-264">Nella tabella seguente sono elencate le informazioni fornite nel report del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2d498-264">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="2d498-265">Metriche del report del dispositivo</span><span class="sxs-lookup"><span data-stu-id="2d498-265">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d498-266">Nome</span><span class="sxs-lookup"><span data-stu-id="2d498-266">Name</span></span></th>
<th><span data-ttu-id="2d498-267">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="2d498-267">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2d498-268">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d498-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d498-269"><strong>Dispositivo di acquisizione</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-269"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-270">Sì</span><span class="sxs-lookup"><span data-stu-id="2d498-270">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d498-271">Dispositivo, ad esempio un microfono o una webcam, usato per la trasmissione di audio.</span><span class="sxs-lookup"><span data-stu-id="2d498-271">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d498-272"><strong>Dispositivo di rendering</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-272"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-273">Sì</span><span class="sxs-lookup"><span data-stu-id="2d498-273">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d498-274">Dispositivo, ad esempio un auricolare o un altoparlante, usato per ricevere l'audio.</span><span class="sxs-lookup"><span data-stu-id="2d498-274">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d498-275"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-275"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-276">Sì</span><span class="sxs-lookup"><span data-stu-id="2d498-276">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d498-277">Numero totale di chiamate inserite.</span><span class="sxs-lookup"><span data-stu-id="2d498-277">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d498-278"><strong>Percentuale di chiamata scadente</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-278"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-279">Sì</span><span class="sxs-lookup"><span data-stu-id="2d498-279">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d498-280">Percentuale di chiamate classificate come &quot;scadenti. &quot; Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.</span><span class="sxs-lookup"><span data-stu-id="2d498-280">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d498-281"><strong>Utenti univoci</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-281"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-282">Sì</span><span class="sxs-lookup"><span data-stu-id="2d498-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d498-283">Utenti univoci che hanno usato il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2d498-283">Unique users who used the device.</span></span> <span data-ttu-id="2d498-284">Se un utente ha usato il dispositivo 13 volte, conta come un utente univoco, come un utente che ha usato solo il dispositivo una sola volta.</span><span class="sxs-lookup"><span data-stu-id="2d498-284">If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d498-285"><strong>Rapporto tra il tempo di cambio vocale</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-285"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-286">Sì</span><span class="sxs-lookup"><span data-stu-id="2d498-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d498-287">Percentuale della chiamata che deve essere eseguita in modalità half duplex per evitare l'eco.</span><span class="sxs-lookup"><span data-stu-id="2d498-287">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="2d498-288">In modalità half duplex, la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo a quando gli utenti si alternano quando comunicano con un walkie-talkie.</span><span class="sxs-lookup"><span data-stu-id="2d498-288">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d498-289"><strong>Rapporto del microfono non funzionante</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-289"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-290">Sì</span><span class="sxs-lookup"><span data-stu-id="2d498-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d498-291">Percentuale della chiamata in cui il dispositivo di acquisizione non funzionava a un livello accettabile.</span><span class="sxs-lookup"><span data-stu-id="2d498-291">Percentage of the call in which the capture device was not functioning at an acceptable level.</span></span> <span data-ttu-id="2d498-292">Un valore elevato suggerisce che i problemi di qualità con la chiamata sono dovuti principalmente al dispositivo di acquisizione che non funziona come previsto.</span><span class="sxs-lookup"><span data-stu-id="2d498-292">A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d498-293"><strong>Rapporto tra l'altoparlante non funziona</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-293"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-294">Sì</span><span class="sxs-lookup"><span data-stu-id="2d498-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d498-295">Percentuale della chiamata in cui il dispositivo di rendering non funzionava a un livello accettabile.</span><span class="sxs-lookup"><span data-stu-id="2d498-295">Percentage of the call in which the render device was not functioning at an acceptable level.</span></span> <span data-ttu-id="2d498-296">Un valore elevato suggerisce che i problemi di qualità con la chiamata sono dovuti principalmente al dispositivo di rendering che non funziona come previsto.</span><span class="sxs-lookup"><span data-stu-id="2d498-296">A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d498-297"><strong>Chiamate con interruttore vocale (%)</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-297"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-298">Sì</span><span class="sxs-lookup"><span data-stu-id="2d498-298">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d498-299">Percentuale delle chiamate totali che dovevano essere inserite nella modalità half duplex.</span><span class="sxs-lookup"><span data-stu-id="2d498-299">Percentage of the total calls which had to be placed into half duplex mode.</span></span> <span data-ttu-id="2d498-300">In modalità half duplex, la comunicazione può viaggiare in una sola direzione alla volta, in modo analogo a quando gli utenti si alternano quando comunicano con un walkie-talkie.</span><span class="sxs-lookup"><span data-stu-id="2d498-300">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d498-301"><strong>Microfono Echo in (%)</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-301"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-302">Sì</span><span class="sxs-lookup"><span data-stu-id="2d498-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d498-303">Percentuale di tempo in cui Echo è stato rilevato nel flusso di acquisizione del microfono.</span><span class="sxs-lookup"><span data-stu-id="2d498-303">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="2d498-304">In genere, i valori sono bassi per gli auricolari o i dispositivi portatili e più in alto per i telefoni con altoparlante o per gli altoparlanti autonomi.</span><span class="sxs-lookup"><span data-stu-id="2d498-304">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="2d498-305">Per i dispositivi che supportano l'annullamento dell'eco acustica a bordo, i valori elevati indicano la perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="2d498-305">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="2d498-306">Per altri dispositivi, questa metrica non deve essere usata per valutare la qualità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2d498-306">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d498-307"><strong>Invio Echo (%)</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-307"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-308">Sì</span><span class="sxs-lookup"><span data-stu-id="2d498-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d498-309">Percentuale di eco trasmessa ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="2d498-309">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d498-310"><strong>Chiamate con Echo (%)</strong></span><span class="sxs-lookup"><span data-stu-id="2d498-310"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d498-311">Sì</span><span class="sxs-lookup"><span data-stu-id="2d498-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d498-312">Percentuale delle chiamate totali con echo che supera il livello accettabile.</span><span class="sxs-lookup"><span data-stu-id="2d498-312">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

