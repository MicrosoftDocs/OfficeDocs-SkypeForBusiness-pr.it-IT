---
title: 'Lync Server 2013: requisiti per i video client di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56743abd386cb59b177806eed3d441aaf587ccce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="c6ac1-102">Requisiti per i video client di Lync per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6ac1-102">Lync client video requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6ac1-103">_**Argomento Ultima modifica:** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="c6ac1-103">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="c6ac1-104">Questa sezione descrive il supporto hardware video per le chiamate video di Lync 2013 e descrive come determinare la qualità video prevista per varie configurazioni di computer, tablet e dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-104">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="c6ac1-105">Requisiti e funzionalità di Windows desktop e tablet video</span><span class="sxs-lookup"><span data-stu-id="c6ac1-105">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="c6ac1-106">Lync 2013 introduce l'accelerazione hardware per la codifica e la decodifica video in base allo standard di codifica video avanzato H. 264/MPEG-4 Part 10.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-106">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="c6ac1-107">Questa funzionalità consente ai computer con velocità di clock della CPU inferiore di codificare e decodificare video con risoluzione superiore.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-107">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="c6ac1-108">I requisiti hardware video variano in base alla configurazione del computer e alla risoluzione video desiderata.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-108">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="c6ac1-109">Requisiti hardware video</span><span class="sxs-lookup"><span data-stu-id="c6ac1-109">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6ac1-110">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="c6ac1-110">Feature</span></span></th>
<th><span data-ttu-id="c6ac1-111">Requisito</span><span class="sxs-lookup"><span data-stu-id="c6ac1-111">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6ac1-112">Decodifica H. 264 con accelerazione hardware con DirectX Video Acceleration (DXVA)</span><span class="sxs-lookup"><span data-stu-id="c6ac1-112">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c6ac1-113">La scheda grafica deve supportare DirectX 9,0 e deve esporre la modalità di decodifica DXVA2_ModeH264_VLD_NoFGT.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-113">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="c6ac1-114">Il driver della scheda grafica più recente deve essere installato.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-114">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="c6ac1-115">Per informazioni dettagliate sulle modalità di decodifica, <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>vedere.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-115">For details about decoding modes, see <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6ac1-116">Codifica H. 264 con accelerazione hardware: requisiti del chipset</span><span class="sxs-lookup"><span data-stu-id="c6ac1-116">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-117">Sono supportate le soluzioni di codifica video con accelerazione hardware Intel seguenti:</span><span class="sxs-lookup"><span data-stu-id="c6ac1-117">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6ac1-118">La seconda e la terza generazione di chipset Intel HD Graphics 2000, 2500, 3000 e 4000 (o versioni successive) con codificatori video hardware integrati.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-118">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="c6ac1-119">È necessario installare il driver di grafica Intel HD 15.28.9.2884 o il driver più recente che contiene le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c6ac1-119">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6ac1-120">Visualizzare il driver 9.17.10.2884 o il driver più recente</span><span class="sxs-lookup"><span data-stu-id="c6ac1-120">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="c6ac1-121">Hardware Media Foundation Transform (HMFT) versione 3.12.10.31 o l'ultima HMFT</span><span class="sxs-lookup"><span data-stu-id="c6ac1-121">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="c6ac1-122">Sono supportate le seguenti soluzioni di codifica video con accelerazione hardware AMD (richiede gli aggiornamenti di CU1 per Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="c6ac1-122">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="c6ac1-123">AMD video codec Engine, disponibile in diverse schede grafiche discrete e in unità di elaborazione accelerata integrata di processori AMD A-Series accelerati.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-123">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors.</span></span> <span data-ttu-id="c6ac1-124">Il driver del motore di codec AMD video 9.12.0.0 o versione successiva deve essere installato.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-124">The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6ac1-125">Codifica H. 264 con accelerazione hardware: requisiti della fotocamera</span><span class="sxs-lookup"><span data-stu-id="c6ac1-125">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-126">Videocamere USB con codificatore hardware H. 264 integrato conforme alla specifica UVC (USB video Class) versione 1,5.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-126">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c6ac1-127">Lync 2013 supporta le telecamere UVC 1,5 con Windows 8 o Windows 8,1, che include il supporto per UVC 1,5.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-127">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="c6ac1-128">Dato che Windows 7 non include il supporto per UVC 1,5, Lync 2013 tratta le fotocamere UVC 1,5 come normali fotocamere senza supporto per la codifica hardware.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-128">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="c6ac1-129">Determinazione delle funzionalità di codifica e decodifica video H. 264</span><span class="sxs-lookup"><span data-stu-id="c6ac1-129">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="c6ac1-130">In genere, esistono quattro fattori principali che determinano la funzionalità di codifica e decodifica massima di una particolare configurazione del computer:</span><span class="sxs-lookup"><span data-stu-id="c6ac1-130">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="c6ac1-131">Supporto della decodifica con accelerazione hardware tramite DXVA</span><span class="sxs-lookup"><span data-stu-id="c6ac1-131">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="c6ac1-132">Supporto per la codifica accelerata hardware</span><span class="sxs-lookup"><span data-stu-id="c6ac1-132">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="c6ac1-133">Numero di core fisici</span><span class="sxs-lookup"><span data-stu-id="c6ac1-133">Number of physical cores</span></span>

  - <span data-ttu-id="c6ac1-134">Indice di Windows Experience (WEI)</span><span class="sxs-lookup"><span data-stu-id="c6ac1-134">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="c6ac1-135">Lo strumento di valutazione di sistema Windows (WinSAT) determina il WEI.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-135">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="c6ac1-136">Quando si esegue lo strumento WinSAT, viene generato un documento XML formale di valutazione nel computer nella directory% windir%\\performance\\WinSAT\\datastore.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-136">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="c6ac1-137">Questo file XML contiene i due punteggi seguenti che rivestono particolare importanza per la determinazione delle funzionalità di codifica e decodifica:</span><span class="sxs-lookup"><span data-stu-id="c6ac1-137">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="c6ac1-138">VideoEncodeScore indica la funzionalità di codifica video basata sul software del computer.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-138">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="c6ac1-139">Il valore GraphicsScore indica la funzionalità di codifica accelerata hardware del computer.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-139">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="c6ac1-140">Le tre tabelle seguenti spiegano la funzionalità di codifica e decodifica massima per diversi tipi di PC, a seconda dell'accelerazione hardware supportata.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-140">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support.</span></span> <span data-ttu-id="c6ac1-141">Per le risoluzioni di 640x360 e successive, la frequenza dei fotogrammi supportata massima è di 30 fotogrammi al secondo (fps).</span><span class="sxs-lookup"><span data-stu-id="c6ac1-141">For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps).</span></span> <span data-ttu-id="c6ac1-142">Per le risoluzioni inferiori a 640x360, la frequenza dei fotogrammi massima supportata è di 15 fps.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-142">For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="c6ac1-143">Computer senza DXVA e senza codificatore accelerato hardware</span><span class="sxs-lookup"><span data-stu-id="c6ac1-143">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6ac1-144">Risoluzione encoder in grado</span><span class="sxs-lookup"><span data-stu-id="c6ac1-144">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="c6ac1-145">Risoluzione del decoder in grado</span><span class="sxs-lookup"><span data-stu-id="c6ac1-145">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="c6ac1-146">Requisito</span><span class="sxs-lookup"><span data-stu-id="c6ac1-146">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6ac1-147">424x240</span><span class="sxs-lookup"><span data-stu-id="c6ac1-147">424x240</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-148">424x240 (640x360 a 15fps per gli scenari di ricezione solo)</span><span class="sxs-lookup"><span data-stu-id="c6ac1-148">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-149">1 core e VideoEncodeScore ≥ 4,0</span><span class="sxs-lookup"><span data-stu-id="c6ac1-149">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6ac1-150">640x360</span><span class="sxs-lookup"><span data-stu-id="c6ac1-150">640x360</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-151">640x360</span><span class="sxs-lookup"><span data-stu-id="c6ac1-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-152">2 core e VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="c6ac1-152">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6ac1-153">640x360</span><span class="sxs-lookup"><span data-stu-id="c6ac1-153">640x360</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-154">1280x720</span><span class="sxs-lookup"><span data-stu-id="c6ac1-154">1280x720</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-155">2 core e VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="c6ac1-155">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6ac1-156">640x360</span><span class="sxs-lookup"><span data-stu-id="c6ac1-156">640x360</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-157">1920x1080</span><span class="sxs-lookup"><span data-stu-id="c6ac1-157">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-158">4 core e VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="c6ac1-158">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6ac1-159">1280x720</span><span class="sxs-lookup"><span data-stu-id="c6ac1-159">1280x720</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-160">1280x720</span><span class="sxs-lookup"><span data-stu-id="c6ac1-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-161">4 core e VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="c6ac1-161">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6ac1-162">1280x720</span><span class="sxs-lookup"><span data-stu-id="c6ac1-162">1280x720</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-163">1920x1080</span><span class="sxs-lookup"><span data-stu-id="c6ac1-163">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-164">4 core e VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="c6ac1-164">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6ac1-165">1920x1080</span><span class="sxs-lookup"><span data-stu-id="c6ac1-165">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-166">1920x1080</span><span class="sxs-lookup"><span data-stu-id="c6ac1-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-167">N/D</span><span class="sxs-lookup"><span data-stu-id="c6ac1-167">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="c6ac1-168">Computer con DXVA ma senza codificatore accelerato hardware</span><span class="sxs-lookup"><span data-stu-id="c6ac1-168">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6ac1-169">Risoluzione encoder in grado</span><span class="sxs-lookup"><span data-stu-id="c6ac1-169">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="c6ac1-170">Risoluzione del decoder in grado</span><span class="sxs-lookup"><span data-stu-id="c6ac1-170">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="c6ac1-171">Requisito</span><span class="sxs-lookup"><span data-stu-id="c6ac1-171">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6ac1-172">424x240</span><span class="sxs-lookup"><span data-stu-id="c6ac1-172">424x240</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-173">1920x1080</span><span class="sxs-lookup"><span data-stu-id="c6ac1-173">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-174">1 core e VideoEncodeScore ≥ 3,0</span><span class="sxs-lookup"><span data-stu-id="c6ac1-174">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6ac1-175">640x360</span><span class="sxs-lookup"><span data-stu-id="c6ac1-175">640x360</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-176">1920x1080</span><span class="sxs-lookup"><span data-stu-id="c6ac1-176">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-177">2 core e VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="c6ac1-177">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6ac1-178">960x540</span><span class="sxs-lookup"><span data-stu-id="c6ac1-178">960x540</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-179">1920x1080</span><span class="sxs-lookup"><span data-stu-id="c6ac1-179">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-180">2 core e VideoEncodeScore ≥ 6,0</span><span class="sxs-lookup"><span data-stu-id="c6ac1-180">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6ac1-181">1280x720</span><span class="sxs-lookup"><span data-stu-id="c6ac1-181">1280x720</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-182">1920x1080</span><span class="sxs-lookup"><span data-stu-id="c6ac1-182">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-183">4 core e VideoEncodeScore ≥ 6,7</span><span class="sxs-lookup"><span data-stu-id="c6ac1-183">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6ac1-184">1920x1080</span><span class="sxs-lookup"><span data-stu-id="c6ac1-184">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-185">1920x1080</span><span class="sxs-lookup"><span data-stu-id="c6ac1-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-186">4 core e VideoEncodeScore ≥ 8,2</span><span class="sxs-lookup"><span data-stu-id="c6ac1-186">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c6ac1-187">Il Punteggio WinSAT in Windows 7 è limitato a un massimo di 7,9.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-187">The WinSAT score on Windows 7 is limited to a maximum of 7.9.</span></span> <span data-ttu-id="c6ac1-188">Di conseguenza, la funzionalità di codifica per un computer senza un codificatore accelerato hardware può essere raggiunta solo in Windows 8 o Windows 8,1, dove il punteggio massimo di WinSAT è 9,9.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-188">Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="c6ac1-189">Computer con DXVA e con encoder accelerato hardware per grafica Intel HD</span><span class="sxs-lookup"><span data-stu-id="c6ac1-189">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6ac1-190">Risoluzione encoder in grado</span><span class="sxs-lookup"><span data-stu-id="c6ac1-190">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="c6ac1-191">Risoluzione del decoder in grado</span><span class="sxs-lookup"><span data-stu-id="c6ac1-191">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="c6ac1-192">Requisito</span><span class="sxs-lookup"><span data-stu-id="c6ac1-192">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6ac1-193">1280x720</span><span class="sxs-lookup"><span data-stu-id="c6ac1-193">1280x720</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-194">1920x1080</span><span class="sxs-lookup"><span data-stu-id="c6ac1-194">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-195">Tutte le seconde e terze generazioni di Intel HD Graphics</span><span class="sxs-lookup"><span data-stu-id="c6ac1-195">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6ac1-196">1920x1080</span><span class="sxs-lookup"><span data-stu-id="c6ac1-196">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-197">1920x1080</span><span class="sxs-lookup"><span data-stu-id="c6ac1-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-198">2 ° e 3 ° generazione di grafica Intel HD e GraphicsScore ≥ 5,0</span><span class="sxs-lookup"><span data-stu-id="c6ac1-198">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="c6ac1-199">Funzionalità video per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="c6ac1-199">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="c6ac1-200">La tabella seguente descrive le funzionalità video massime per i dispositivi mobili supportati.</span><span class="sxs-lookup"><span data-stu-id="c6ac1-200">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="c6ac1-201">Per altre informazioni sul supporto di dispositivi mobili, vedere [pianificazione per i client mobili in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="c6ac1-201">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6ac1-202">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="c6ac1-202">Feature</span></span></th>
<th><span data-ttu-id="c6ac1-203">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="c6ac1-203">Windows Phone</span></span></th>
<th><span data-ttu-id="c6ac1-204">iPhone</span><span class="sxs-lookup"><span data-stu-id="c6ac1-204">iPhone</span></span></th>
<th><span data-ttu-id="c6ac1-205">iPad</span><span class="sxs-lookup"><span data-stu-id="c6ac1-205">iPad</span></span></th>
<th><span data-ttu-id="c6ac1-206">Android</span><span class="sxs-lookup"><span data-stu-id="c6ac1-206">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6ac1-207">Risoluzione massima della codifica H. 264</span><span class="sxs-lookup"><span data-stu-id="c6ac1-207">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-208">VGA</span><span class="sxs-lookup"><span data-stu-id="c6ac1-208">VGA</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-209">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="c6ac1-209">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="c6ac1-210">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="c6ac1-210">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="c6ac1-211">720p: iPhone 5S e versioni successive</span><span class="sxs-lookup"><span data-stu-id="c6ac1-211">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-212">VGA: iPad 2 e versioni successive/iPad mini 1 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="c6ac1-212">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="c6ac1-213">720p: iPad Air/iPad mini 2/iPad Pro e versioni successive</span><span class="sxs-lookup"><span data-stu-id="c6ac1-213">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-214">Fino a VGA a seconda del modello di dispositivo</span><span class="sxs-lookup"><span data-stu-id="c6ac1-214">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6ac1-215">Risoluzione massima di decodifica H. 264</span><span class="sxs-lookup"><span data-stu-id="c6ac1-215">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-216">VGA</span><span class="sxs-lookup"><span data-stu-id="c6ac1-216">VGA</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-217">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="c6ac1-217">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="c6ac1-218">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="c6ac1-218">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="c6ac1-219">720p: iPhone 5S e versioni successive</span><span class="sxs-lookup"><span data-stu-id="c6ac1-219">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-220">VGA: iPad 2 e versioni successive/iPad mini 1 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="c6ac1-220">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="c6ac1-221">720p: iPad Air/iPad mini 2/iPad Pro e versioni successive</span><span class="sxs-lookup"><span data-stu-id="c6ac1-221">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="c6ac1-222">Fino a VGA a seconda del modello di dispositivo</span><span class="sxs-lookup"><span data-stu-id="c6ac1-222">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

