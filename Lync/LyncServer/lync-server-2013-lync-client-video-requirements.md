---
title: 'Lync Server 2013: requisiti video di Lync client'
description: 'Lync Server 2013: requisiti video di Lync client.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea1d4a993650ec8102d8b66ea5aa936ad1613f20
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570482"
---
# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="0f56e-103">Requisiti video di Lync client per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f56e-103">Lync client video requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f56e-104">_**Ultimo argomento modificato:** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="0f56e-104">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="0f56e-105">In questa sezione viene descritto il supporto hardware video per le chiamate video di Lync 2013 e viene descritto come determinare la qualità video prevista per le diverse configurazioni di computer, tablet e dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="0f56e-105">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="0f56e-106">Requisiti e funzionalità di Windows desktop e tablet video</span><span class="sxs-lookup"><span data-stu-id="0f56e-106">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="0f56e-107">Lync 2013 introduce l'accelerazione hardware per la codifica e decodifica video in base allo standard di codifica video avanzato della parte 10 di H. 264/MPEG-4.</span><span class="sxs-lookup"><span data-stu-id="0f56e-107">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="0f56e-108">Questa caratteristica consente ai computer con velocità di clock della CPU inferiori di codificare e decodificare video a risoluzioni più elevate.</span><span class="sxs-lookup"><span data-stu-id="0f56e-108">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="0f56e-109">I requisiti hardware video variano a seconda della configurazione del computer e alla risoluzione video desiderata.</span><span class="sxs-lookup"><span data-stu-id="0f56e-109">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="0f56e-110">Requisiti hardware video</span><span class="sxs-lookup"><span data-stu-id="0f56e-110">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f56e-111">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="0f56e-111">Feature</span></span></th>
<th><span data-ttu-id="0f56e-112">Requisito</span><span class="sxs-lookup"><span data-stu-id="0f56e-112">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f56e-113">Decodifica H.264 con accelerazione hardware mediante DirectX Video Acceleration (DXVA)</span><span class="sxs-lookup"><span data-stu-id="0f56e-113">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0f56e-114">La scheda video deve supportare DirectX 9.0 ed esporre la modalità di decodifica DXVA2_ModeH264_VLD_NoFGT.</span><span class="sxs-lookup"><span data-stu-id="0f56e-114">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="0f56e-115">Deve essere installato il driver più recente della scheda video.</span><span class="sxs-lookup"><span data-stu-id="0f56e-115">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="0f56e-116">Per informazioni dettagliate sulle modalità di decodifica, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A> .</span><span class="sxs-lookup"><span data-stu-id="0f56e-116">For details about decoding modes, see <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f56e-117">Codifica H.264 con accelerazione hardware: requisiti del chipset</span><span class="sxs-lookup"><span data-stu-id="0f56e-117">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="0f56e-118">Sono supportate le seguenti soluzioni di codifica video con accelerazione hardware Intel:</span><span class="sxs-lookup"><span data-stu-id="0f56e-118">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="0f56e-119">Chipset Intel HD Graphics 2000, 2500, 3000 e 4000 di seconda e terza generazione (o versioni successive) con codificatori video hardware integrati.</span><span class="sxs-lookup"><span data-stu-id="0f56e-119">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="0f56e-120">È necessaria l'installazione di Intel HD Graphics driver 15.28.9.2884 o dell'ultimo driver contenente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0f56e-120">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="0f56e-121">Visualizzare il driver 9.17.10.2884 o il driver più recente</span><span class="sxs-lookup"><span data-stu-id="0f56e-121">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="0f56e-122">Hardware Media Foundation Transform (HMFT) versione 3.12.10.31 o l'ultima HMFT</span><span class="sxs-lookup"><span data-stu-id="0f56e-122">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="0f56e-123">Sono supportate le seguenti soluzioni di codifica video con accelerazione hardware AMD (sono necessari aggiornamenti di CU1 per Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="0f56e-123">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="0f56e-124">AMD video codec Engine, disponibile in diverse schede grafiche discrete e in unità di elaborazione con accelerazione integrata dei processori con accelerazione AMD A-Series.</span><span class="sxs-lookup"><span data-stu-id="0f56e-124">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors.</span></span> <span data-ttu-id="0f56e-125">È necessario installare il driver del motore di codec AMD video 9.12.0.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="0f56e-125">The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f56e-126">Codifica H.264 con accelerazione hardware: requisiti fotocamera</span><span class="sxs-lookup"><span data-stu-id="0f56e-126">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="0f56e-127">Fotocamere video USB con codificatore H.264 integrato conforme alla specifica USB Video Class (UVC) versione 1.5.</span><span class="sxs-lookup"><span data-stu-id="0f56e-127">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0f56e-128">Lync 2013 supporta le fotocamere UVC 1,5 con Windows 8 o Windows 8,1, che include il supporto per UVC 1,5.</span><span class="sxs-lookup"><span data-stu-id="0f56e-128">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="0f56e-129">Poiché Windows 7 non include il supporto per UVC 1.5, Lync 2013 tratta le fotocamere UVC 1.5 come fotocamere normali senza supporto per la codifica hardware.</span><span class="sxs-lookup"><span data-stu-id="0f56e-129">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="0f56e-130">Individuazione delle funzionalità di codifica e decodifica video H.264</span><span class="sxs-lookup"><span data-stu-id="0f56e-130">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="0f56e-131">In generale, esistono quattro fattori principali che determinano la capacità di codifica e decodifica massima di una particolare configurazione di computer:</span><span class="sxs-lookup"><span data-stu-id="0f56e-131">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="0f56e-132">Supporto per decodifica con accelerazione hardware mediante DXVA</span><span class="sxs-lookup"><span data-stu-id="0f56e-132">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="0f56e-133">Supporto per la codifica con accelerazione hardware</span><span class="sxs-lookup"><span data-stu-id="0f56e-133">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="0f56e-134">Numero di core fisici</span><span class="sxs-lookup"><span data-stu-id="0f56e-134">Number of physical cores</span></span>

  - <span data-ttu-id="0f56e-135">Indice prestazioni Windows</span><span class="sxs-lookup"><span data-stu-id="0f56e-135">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="0f56e-136">Lo strumento Valutazione sistema Windows (WinSAT) determina l'Indice prestazioni Windows.</span><span class="sxs-lookup"><span data-stu-id="0f56e-136">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="0f56e-137">Quando si esegue lo strumento WinSAT, viene generato un documento XML formale di valutazione nel computer nella directory% windir% \\ performance \\ WinSAT \\ datastore.</span><span class="sxs-lookup"><span data-stu-id="0f56e-137">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="0f56e-138">Questo file XML contiene i due punteggi indicati di seguito di particolare importanza per determinare le funzionalità di codifica e decodifica:</span><span class="sxs-lookup"><span data-stu-id="0f56e-138">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="0f56e-139">VideoEncodeScore indica le capacità di codifica video basata su software del computer.</span><span class="sxs-lookup"><span data-stu-id="0f56e-139">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="0f56e-140">Il valore GraphicsScore indica la capacità di codifica con accelerazione hardware del computer.</span><span class="sxs-lookup"><span data-stu-id="0f56e-140">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="0f56e-p106">Nelle tre tabelle seguenti sono indicate le capacità massime di codifica e decodifica per diversi tipi di PC a seconda dell'accelerazione hardware supportata. Per risoluzioni pari a 640x360 e superiori, la massima frequenza dei fotogrammi supportata è pari a 30 fotogrammi al secondo (fps). Per risoluzioni inferiori a 640x360, la massima velocità dei fotogrammi supportata è pari a 15 fps.</span><span class="sxs-lookup"><span data-stu-id="0f56e-p106">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support. For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps). For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="0f56e-144">Computer senza DXVA e senza codificatore con accelerazione hardware</span><span class="sxs-lookup"><span data-stu-id="0f56e-144">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f56e-145">Risoluzione codificatore</span><span class="sxs-lookup"><span data-stu-id="0f56e-145">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="0f56e-146">Risoluzione decodificatore</span><span class="sxs-lookup"><span data-stu-id="0f56e-146">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="0f56e-147">Requisito</span><span class="sxs-lookup"><span data-stu-id="0f56e-147">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f56e-148">424x240</span><span class="sxs-lookup"><span data-stu-id="0f56e-148">424x240</span></span></p></td>
<td><p><span data-ttu-id="0f56e-149">424x240 (640x360 a 15 fps solo per scenari di ricezione)</span><span class="sxs-lookup"><span data-stu-id="0f56e-149">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="0f56e-150">1 core e VideoEncodeScore ≥ 4,0</span><span class="sxs-lookup"><span data-stu-id="0f56e-150">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f56e-151">640x360</span><span class="sxs-lookup"><span data-stu-id="0f56e-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="0f56e-152">640x360</span><span class="sxs-lookup"><span data-stu-id="0f56e-152">640x360</span></span></p></td>
<td><p><span data-ttu-id="0f56e-153">2 core e VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="0f56e-153">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f56e-154">640x360</span><span class="sxs-lookup"><span data-stu-id="0f56e-154">640x360</span></span></p></td>
<td><p><span data-ttu-id="0f56e-155">1280x720</span><span class="sxs-lookup"><span data-stu-id="0f56e-155">1280x720</span></span></p></td>
<td><p><span data-ttu-id="0f56e-156">2 core e VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="0f56e-156">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f56e-157">640x360</span><span class="sxs-lookup"><span data-stu-id="0f56e-157">640x360</span></span></p></td>
<td><p><span data-ttu-id="0f56e-158">1920x1080</span><span class="sxs-lookup"><span data-stu-id="0f56e-158">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="0f56e-159">4 core e VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="0f56e-159">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f56e-160">1280x720</span><span class="sxs-lookup"><span data-stu-id="0f56e-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="0f56e-161">1280x720</span><span class="sxs-lookup"><span data-stu-id="0f56e-161">1280x720</span></span></p></td>
<td><p><span data-ttu-id="0f56e-162">4 core e VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="0f56e-162">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f56e-163">1280x720</span><span class="sxs-lookup"><span data-stu-id="0f56e-163">1280x720</span></span></p></td>
<td><p><span data-ttu-id="0f56e-164">1920x1080</span><span class="sxs-lookup"><span data-stu-id="0f56e-164">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="0f56e-165">4 core e VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="0f56e-165">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f56e-166">1920x1080</span><span class="sxs-lookup"><span data-stu-id="0f56e-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="0f56e-167">1920x1080</span><span class="sxs-lookup"><span data-stu-id="0f56e-167">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="0f56e-168">N/D</span><span class="sxs-lookup"><span data-stu-id="0f56e-168">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="0f56e-169">Computer con DXVA ma senza codificatore con accelerazione hardware</span><span class="sxs-lookup"><span data-stu-id="0f56e-169">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f56e-170">Risoluzione codificatore</span><span class="sxs-lookup"><span data-stu-id="0f56e-170">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="0f56e-171">Risoluzione decodificatore</span><span class="sxs-lookup"><span data-stu-id="0f56e-171">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="0f56e-172">Requisito</span><span class="sxs-lookup"><span data-stu-id="0f56e-172">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f56e-173">424x240</span><span class="sxs-lookup"><span data-stu-id="0f56e-173">424x240</span></span></p></td>
<td><p><span data-ttu-id="0f56e-174">1920x1080</span><span class="sxs-lookup"><span data-stu-id="0f56e-174">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="0f56e-175">1 core e VideoEncodeScore = 3,0</span><span class="sxs-lookup"><span data-stu-id="0f56e-175">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f56e-176">640x360</span><span class="sxs-lookup"><span data-stu-id="0f56e-176">640x360</span></span></p></td>
<td><p><span data-ttu-id="0f56e-177">1920x1080</span><span class="sxs-lookup"><span data-stu-id="0f56e-177">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="0f56e-178">2 core e VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="0f56e-178">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f56e-179">960x540</span><span class="sxs-lookup"><span data-stu-id="0f56e-179">960x540</span></span></p></td>
<td><p><span data-ttu-id="0f56e-180">1920x1080</span><span class="sxs-lookup"><span data-stu-id="0f56e-180">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="0f56e-181">2 core e VideoEncodeScore ≥ 6,0</span><span class="sxs-lookup"><span data-stu-id="0f56e-181">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f56e-182">1280x720</span><span class="sxs-lookup"><span data-stu-id="0f56e-182">1280x720</span></span></p></td>
<td><p><span data-ttu-id="0f56e-183">1920x1080</span><span class="sxs-lookup"><span data-stu-id="0f56e-183">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="0f56e-184">4 core e VideoEncodeScore ≥ 6,7</span><span class="sxs-lookup"><span data-stu-id="0f56e-184">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f56e-185">1920x1080</span><span class="sxs-lookup"><span data-stu-id="0f56e-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="0f56e-186">1920x1080</span><span class="sxs-lookup"><span data-stu-id="0f56e-186">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="0f56e-187">4 core e VideoEncodeScore ≥ 8,2</span><span class="sxs-lookup"><span data-stu-id="0f56e-187">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="0f56e-188">Il Punteggio WinSAT su Windows 7 è limitato a un massimo di 7,9.</span><span class="sxs-lookup"><span data-stu-id="0f56e-188">The WinSAT score on Windows 7 is limited to a maximum of 7.9.</span></span> <span data-ttu-id="0f56e-189">Pertanto, la capacità di codifica per un computer senza un codificatore con accelerazione hardware può essere raggiunta solo su Windows 8 o Windows 8,1, dove il punteggio massimo WinSAT è 9,9.</span><span class="sxs-lookup"><span data-stu-id="0f56e-189">Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="0f56e-190">Computer con DXVA e con codificatore con accelerazione hardware Intel HD Graphics</span><span class="sxs-lookup"><span data-stu-id="0f56e-190">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f56e-191">Risoluzione codificatore</span><span class="sxs-lookup"><span data-stu-id="0f56e-191">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="0f56e-192">Risoluzione decodificatore</span><span class="sxs-lookup"><span data-stu-id="0f56e-192">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="0f56e-193">Requisito</span><span class="sxs-lookup"><span data-stu-id="0f56e-193">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f56e-194">1280x720</span><span class="sxs-lookup"><span data-stu-id="0f56e-194">1280x720</span></span></p></td>
<td><p><span data-ttu-id="0f56e-195">1920x1080</span><span class="sxs-lookup"><span data-stu-id="0f56e-195">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="0f56e-196">Tutti i driver Intel HD Graphics di seconda e terza generazione</span><span class="sxs-lookup"><span data-stu-id="0f56e-196">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f56e-197">1920x1080</span><span class="sxs-lookup"><span data-stu-id="0f56e-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="0f56e-198">1920x1080</span><span class="sxs-lookup"><span data-stu-id="0f56e-198">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="0f56e-199">Driver Intel HD Graphics di seconda e terza generazione e GraphicsScore ≥ 5,0</span><span class="sxs-lookup"><span data-stu-id="0f56e-199">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="0f56e-200">Funzionalità video per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="0f56e-200">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="0f56e-201">Nella tabella seguente vengono descritte le funzionalità video massime per i dispositivi mobili supportati.</span><span class="sxs-lookup"><span data-stu-id="0f56e-201">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="0f56e-202">Per ulteriori informazioni sul supporto dei dispositivi mobili, vedere [Planning for Mobile Clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="0f56e-202">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


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
<th><span data-ttu-id="0f56e-203">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="0f56e-203">Feature</span></span></th>
<th><span data-ttu-id="0f56e-204">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="0f56e-204">Windows Phone</span></span></th>
<th><span data-ttu-id="0f56e-205">iPhone</span><span class="sxs-lookup"><span data-stu-id="0f56e-205">iPhone</span></span></th>
<th><span data-ttu-id="0f56e-206">iPad</span><span class="sxs-lookup"><span data-stu-id="0f56e-206">iPad</span></span></th>
<th><span data-ttu-id="0f56e-207">Android</span><span class="sxs-lookup"><span data-stu-id="0f56e-207">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f56e-208">Risoluzione massima di codifica H. 264</span><span class="sxs-lookup"><span data-stu-id="0f56e-208">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="0f56e-209">VGA</span><span class="sxs-lookup"><span data-stu-id="0f56e-209">VGA</span></span></p></td>
<td><p><span data-ttu-id="0f56e-210">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="0f56e-210">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="0f56e-211">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="0f56e-211">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="0f56e-212">720p: iPhone 5S e versioni successive</span><span class="sxs-lookup"><span data-stu-id="0f56e-212">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="0f56e-213">VGA: iPad 2 e versioni successive/iPad mini 1 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="0f56e-213">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="0f56e-214">720p: iPad Air/iPad mini 2/iPad Pro e versioni successive</span><span class="sxs-lookup"><span data-stu-id="0f56e-214">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="0f56e-215">Fino a VGA a seconda del modello di dispositivo</span><span class="sxs-lookup"><span data-stu-id="0f56e-215">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f56e-216">Risoluzione massima di decodifica H. 264</span><span class="sxs-lookup"><span data-stu-id="0f56e-216">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="0f56e-217">VGA</span><span class="sxs-lookup"><span data-stu-id="0f56e-217">VGA</span></span></p></td>
<td><p><span data-ttu-id="0f56e-218">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="0f56e-218">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="0f56e-219">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="0f56e-219">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="0f56e-220">720p: iPhone 5S e versioni successive</span><span class="sxs-lookup"><span data-stu-id="0f56e-220">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="0f56e-221">VGA: iPad 2 e versioni successive/iPad mini 1 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="0f56e-221">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="0f56e-222">720p: iPad Air/iPad mini 2/iPad Pro e versioni successive</span><span class="sxs-lookup"><span data-stu-id="0f56e-222">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="0f56e-223">Fino a VGA a seconda del modello di dispositivo</span><span class="sxs-lookup"><span data-stu-id="0f56e-223">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

