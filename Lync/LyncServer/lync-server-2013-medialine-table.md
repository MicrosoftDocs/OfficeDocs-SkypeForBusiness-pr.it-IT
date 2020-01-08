---
title: 'Lync Server 2013: Tabella MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4828f67614115eb4d6f46ab0a0a7c315e02d1924
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="1ee2c-102">Tabella MediaLine in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ee2c-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ee2c-103">_**Argomento Ultima modifica:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="1ee2c-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="1ee2c-104">Ogni record rappresenta una linea media.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-104">Each record represents one media line.</span></span> <span data-ttu-id="1ee2c-105">(Una sessione audio in genere contiene una linea media audio.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="1ee2c-106">Una sessione audio e video (A/V) in genere contiene una linea media audio e una linea media video, anche se la sessione può contenere due linee multimediali video se viene usato un dispositivo per conferenze o se viene usata la visualizzazione raccolta.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ee2c-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1ee2c-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1ee2c-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1ee2c-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="1ee2c-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-113">Principale</span><span class="sxs-lookup"><span data-stu-id="1ee2c-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-114">A cui si fa riferimento dalla <a href="lync-server-2013-session-table.md">tabella di sessione in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-116">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-116">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-117">Principale</span><span class="sxs-lookup"><span data-stu-id="1ee2c-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-118">A cui si fa riferimento dalla <a href="lync-server-2013-session-table.md">tabella di sessione in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="1ee2c-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-121">Principale</span><span class="sxs-lookup"><span data-stu-id="1ee2c-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-122">0 è l'audio principale, 1 è il video principale e 2 è un video panoramico, 3 è la condivisione di applicazioni/desktop.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="1ee2c-123">Questa etichetta deve essere univoca all'interno di una singola sessione.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="1ee2c-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ee2c-126">Questa colonna è presente ma non viene usata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="1ee2c-127">Le informazioni sulla connettività usata per una linea media vengono acquisite nelle colonne CallerConnectivityICE e CalleeConnectivityICE.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-129">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ee2c-130">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in flag di bit.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="1ee2c-131">Per informazioni dettagliate, vedere la sezione relativa alla <em>qualità della specifica di protocollo di monitoraggio delle esperienze</em>disponibile per il download.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-133">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ee2c-134">Uguale a CallerIceWarningFlags, ma sul lato chiamato.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="1ee2c-135">Per informazioni dettagliate, vedere la sezione relativa alla <em>qualità della specifica di protocollo di monitoraggio delle esperienze</em>disponibile per il download.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-136"><strong>Sicurezza</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="1ee2c-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ee2c-138">Profilo di sicurezza in uso.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-138">The security profile in use.</span></span> <span data-ttu-id="1ee2c-139">0 è NONE, 1 è SRTP, 2 è V1.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="1ee2c-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ee2c-142">0 è UDP, 1 è TCP.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-144">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-144">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-145">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-146">Indirizzo IP del chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-146">IP Address of the caller.</span></span> <span data-ttu-id="1ee2c-147">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ee2c-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-149">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ee2c-150">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-152">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-152">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-153"> Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-154">Subnet del chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-154">The subnet of the caller.</span></span> <span data-ttu-id="1ee2c-155">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ee2c-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-157">po'</span><span class="sxs-lookup"><span data-stu-id="1ee2c-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ee2c-158">1 indica che il chiamante si trova all'interno della rete aziendale, 0 indica che il chiamante si trova all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-160">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-160">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-161">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-162">Indirizzo MAC del chiamante, a cui si fa riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-164">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-164">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-165">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-166">Indirizzo IP del servizio A/V Edge di Lync Server usato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="1ee2c-167">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ee2c-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-169">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ee2c-170">Porta usata nel servizio A/V Edge dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-172">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-172">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-173">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-174">Dispositivo di acquisizione usato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-174">Capture device used by the caller.</span></span> <span data-ttu-id="1ee2c-175">A cui si fa riferimento dalla <a href="lync-server-2013-device-table.md">tabella dei dispositivi in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-177">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-177">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-178">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-179">Dispositivo di rendering usato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-179">Render device used by caller.</span></span> <span data-ttu-id="1ee2c-180">A cui si fa riferimento dalla <a href="lync-server-2013-device-table.md">tabella dei dispositivi in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-182">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-182">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-183">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-184">Driver per il dispositivo di acquisizione del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-186">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-186">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-187">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-188">Driver per il dispositivo di rendering del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="1ee2c-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-191">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-192">Indica il modo in cui il chiamante si connette alla rete.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="1ee2c-193">I valori vengono ottenuti dalla <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="1ee2c-194">I valori tipici sono 0 per una connessione cablata ' 1 per una connessione WiFi; e 3 per una connessione Ethernet.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-196">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-196">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-197">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-198">BSSID del chiamante se viene usato wireless.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="1ee2c-199">A cui si fa riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-201">po'</span><span class="sxs-lookup"><span data-stu-id="1ee2c-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ee2c-202">Collegamento del chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-202">The caller's link.</span></span> <span data-ttu-id="1ee2c-203">1 è una rete privata virtuale (VPN), 0 non è VPN.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-205">decimale (18; 0)</span><span class="sxs-lookup"><span data-stu-id="1ee2c-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ee2c-206">Velocità di collegamento di rete, in bps, per l'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-208">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-208">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-209">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-210">Indirizzo IP del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-210">IP Address of the call receiver.</span></span> <span data-ttu-id="1ee2c-211">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ee2c-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-213">po'</span><span class="sxs-lookup"><span data-stu-id="1ee2c-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ee2c-214">Porta usata dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-216">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-216">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-217">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-218">Subnet del chiamato.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-218">Subnet of callee.</span></span> <span data-ttu-id="1ee2c-219">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ee2c-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-221">po'</span><span class="sxs-lookup"><span data-stu-id="1ee2c-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ee2c-222">1 indica che il destinatario della chiamata si trova all'interno della rete aziendale, 0 indica che il destinatario della chiamata si trova all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-224">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-224">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-225">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-226">Indirizzo MAC del destinatario.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-226">Callee Mac address.</span></span> <span data-ttu-id="1ee2c-227">A cui si fa riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-229">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-229">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-230">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-231">Indirizzo IP del servizio A/V Edge usato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="1ee2c-232">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ee2c-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-234">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ee2c-235">Porta usata nel servizio A/V Edge dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-237">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-237">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-238">esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-239">Dispositivo di acquisizione usato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="1ee2c-240">A cui si fa riferimento dalla <a href="lync-server-2013-device-table.md">tabella dei dispositivi in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-242">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-242">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-243">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-244">Dispositivo di rendering usato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-244">Render device used by the call receiver.</span></span> <span data-ttu-id="1ee2c-245">A cui si fa riferimento dalla <a href="lync-server-2013-device-table.md">tabella dei dispositivi in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-247">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-247">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-248">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-249">Driver per il dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="1ee2c-250">A cui si fa riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ee2c-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-253">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-254">Driver per il dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="1ee2c-255">A cui si fa riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="1ee2c-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-258">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-259">Indica il modo in cui il chiamato si connette alla rete.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="1ee2c-260">I valori vengono ottenuti dalla <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="1ee2c-261">I valori tipici sono 0 per una connessione cablata ' 1 per una connessione WiFi; e 3 per una connessione Ethernet.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-263">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-263">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-264">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-265">BSSID di chiamata se viene usato wireless.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="1ee2c-266">A cui si fa riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-268">po'</span><span class="sxs-lookup"><span data-stu-id="1ee2c-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ee2c-269">Collegamento del destinatario della chiamata; 1 è una rete privata virtuale (VPN), 0 non è VPN.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-271">decimale (18; 0)</span><span class="sxs-lookup"><span data-stu-id="1ee2c-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ee2c-272">Velocità di collegamento di rete, in bps, per l'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-274">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="1ee2c-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ee2c-275">Stretta MOS colloquiale delle sessioni audio (in base a entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="1ee2c-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-277">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ee2c-278">Si tratta della larghezza di banda effettiva applicata al flusso del lato di invio assegnato in base a varie impostazioni dei criteri (TURN, API, SDP, Policy Server e così via).</span><span class="sxs-lookup"><span data-stu-id="1ee2c-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="1ee2c-279">Questa operazione non deve essere confusa con la larghezza di banda effettiva, perché la larghezza di banda effettiva può essere inferiore in base alla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="1ee2c-280">Si tratta in pratica della larghezza di banda massima che il flusso di invio può bloccare i limiti imposti dalla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-282">smallint</span><span class="sxs-lookup"><span data-stu-id="1ee2c-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ee2c-283">Questa è l'origine del limite di larghezza di banda imposto.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="1ee2c-284">Descrive la posizione del limite di larghezza di banda ("Policy Server", "TURN server", "modality" e così via).</span><span class="sxs-lookup"><span data-stu-id="1ee2c-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="1ee2c-285">A cui si fa riferimento dalla <a href="lync-server-2013-appliedbandwidthsource-table.md">tabella AppliedBandwidthSource in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-286"><strong>Chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-287">po'</span><span class="sxs-lookup"><span data-stu-id="1ee2c-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ee2c-288">Indica se sono state ricevute metriche dal chiamante; 1 è sì, un valore null è no.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-289"><strong>Chiamato</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-290">po'</span><span class="sxs-lookup"><span data-stu-id="1ee2c-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ee2c-291">Indica se le metriche del destinatario della chiamata sono state ricevute; 1 è sì, un valore null è no.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-293">po'</span><span class="sxs-lookup"><span data-stu-id="1ee2c-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ee2c-294">Indica se il report è per una parte della sessione o per la sessione completa.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="1ee2c-295">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-297">po'</span><span class="sxs-lookup"><span data-stu-id="1ee2c-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ee2c-298">Indica se una chiamata è stata classificata come chiamata scadente (valore 1) o come buona chiamata (0).</span><span class="sxs-lookup"><span data-stu-id="1ee2c-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="1ee2c-299">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="1ee2c-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ee2c-302">Indica se il chiamante è connesso alla rete usando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="1ee2c-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="1ee2c-303">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="1ee2c-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ee2c-306">Indica se il chiamante è connesso alla rete usando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="1ee2c-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="1ee2c-307">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-309">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-309">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-310">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-311">Indirizzo IP riflessivo dell'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="1ee2c-312">Nelle organizzazioni che usano NAT (Network Address Translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="1ee2c-313">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-315">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-315">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-316">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-317">Descrizione del dispositivo per il driver WiFi impiegato dall'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="1ee2c-318">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-320">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-320">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-321">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-322">Numero di versione per il driver WiFi impiegato dall'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="1ee2c-323">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-325">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-325">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-326">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-327">Indirizzo IP riflessivo dell'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="1ee2c-328">Nelle organizzazioni che usano NAT (Network Address Translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="1ee2c-329">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ee2c-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-331">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-331">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-332">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-333">Descrizione del dispositivo per il driver WiFi impiegato dall'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="1ee2c-334">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ee2c-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="1ee2c-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="1ee2c-336">int</span><span class="sxs-lookup"><span data-stu-id="1ee2c-336">int</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-337">Esterna</span><span class="sxs-lookup"><span data-stu-id="1ee2c-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ee2c-338">Numero di versione per il driver WiFi impiegato dall'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="1ee2c-339">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ee2c-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

