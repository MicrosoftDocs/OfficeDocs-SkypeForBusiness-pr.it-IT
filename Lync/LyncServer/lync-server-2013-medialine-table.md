---
title: 'Lync Server 2013: Tabella MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7488aa258fd30c2f9b519806dc84f9d897a08656
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="71acb-102">Tabella MediaLine in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71acb-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71acb-103">_**Argomento Ultima modifica:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="71acb-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="71acb-104">Ogni record rappresenta una linea media.</span><span class="sxs-lookup"><span data-stu-id="71acb-104">Each record represents one media line.</span></span> <span data-ttu-id="71acb-105">(Una sessione audio in genere contiene una linea media audio.</span><span class="sxs-lookup"><span data-stu-id="71acb-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="71acb-106">Una sessione audio e video (A/V) in genere contiene una linea media audio e una linea media video, anche se la sessione può contenere due linee multimediali video se viene usato un dispositivo per conferenze o se viene usata la visualizzazione raccolta.</span><span class="sxs-lookup"><span data-stu-id="71acb-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71acb-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="71acb-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="71acb-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="71acb-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71acb-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="71acb-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="71acb-113">Principale</span><span class="sxs-lookup"><span data-stu-id="71acb-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="71acb-114">A cui si fa riferimento dalla <a href="lync-server-2013-session-table.md">tabella di sessione in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-116">int</span><span class="sxs-lookup"><span data-stu-id="71acb-116">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-117">Principale</span><span class="sxs-lookup"><span data-stu-id="71acb-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="71acb-118">A cui si fa riferimento dalla <a href="lync-server-2013-session-table.md">tabella di sessione in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="71acb-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="71acb-121">Principale</span><span class="sxs-lookup"><span data-stu-id="71acb-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="71acb-122">0 è l'audio principale, 1 è il video principale e 2 è un video panoramico, 3 è la condivisione di applicazioni/desktop.</span><span class="sxs-lookup"><span data-stu-id="71acb-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="71acb-123">Questa etichetta deve essere univoca all'interno di una singola sessione.</span><span class="sxs-lookup"><span data-stu-id="71acb-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="71acb-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71acb-126">Questa colonna è presente ma non viene usata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71acb-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="71acb-127">Le informazioni sulla connettività usata per una linea media vengono acquisite nelle colonne CallerConnectivityICE e CalleeConnectivityICE.</span><span class="sxs-lookup"><span data-stu-id="71acb-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-129">int</span><span class="sxs-lookup"><span data-stu-id="71acb-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71acb-130">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in flag di bit.</span><span class="sxs-lookup"><span data-stu-id="71acb-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="71acb-131">Per informazioni dettagliate, vedere la sezione relativa alla <em>qualità della specifica di protocollo di monitoraggio delle esperienze</em>disponibile per il download.</span><span class="sxs-lookup"><span data-stu-id="71acb-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-133">int</span><span class="sxs-lookup"><span data-stu-id="71acb-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71acb-134">Uguale a CallerIceWarningFlags, ma sul lato chiamato.</span><span class="sxs-lookup"><span data-stu-id="71acb-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="71acb-135">Per informazioni dettagliate, vedere la sezione relativa alla <em>qualità della specifica di protocollo di monitoraggio delle esperienze</em>disponibile per il download.</span><span class="sxs-lookup"><span data-stu-id="71acb-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-136"><strong>Sicurezza</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="71acb-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71acb-138">Profilo di sicurezza in uso.</span><span class="sxs-lookup"><span data-stu-id="71acb-138">The security profile in use.</span></span> <span data-ttu-id="71acb-139">0 è NONE, 1 è SRTP, 2 è V1.</span><span class="sxs-lookup"><span data-stu-id="71acb-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="71acb-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71acb-142">0 è UDP, 1 è TCP.</span><span class="sxs-lookup"><span data-stu-id="71acb-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-144">int</span><span class="sxs-lookup"><span data-stu-id="71acb-144">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-145">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-146">Indirizzo IP del chiamante.</span><span class="sxs-lookup"><span data-stu-id="71acb-146">IP Address of the caller.</span></span> <span data-ttu-id="71acb-147">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71acb-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-149">int</span><span class="sxs-lookup"><span data-stu-id="71acb-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71acb-150">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="71acb-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-152">int</span><span class="sxs-lookup"><span data-stu-id="71acb-152">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-153"> Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-154">Subnet del chiamante.</span><span class="sxs-lookup"><span data-stu-id="71acb-154">The subnet of the caller.</span></span> <span data-ttu-id="71acb-155">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71acb-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-157">po'</span><span class="sxs-lookup"><span data-stu-id="71acb-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71acb-158">1 indica che il chiamante si trova all'interno della rete aziendale, 0 indica che il chiamante si trova all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="71acb-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-160">int</span><span class="sxs-lookup"><span data-stu-id="71acb-160">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-161">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-162">Indirizzo MAC del chiamante, a cui si fa riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-164">int</span><span class="sxs-lookup"><span data-stu-id="71acb-164">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-165">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-166">Indirizzo IP del servizio A/V Edge di Lync Server usato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="71acb-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="71acb-167">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71acb-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-169">int</span><span class="sxs-lookup"><span data-stu-id="71acb-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71acb-170">Porta usata nel servizio A/V Edge dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="71acb-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-172">int</span><span class="sxs-lookup"><span data-stu-id="71acb-172">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-173">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-174">Dispositivo di acquisizione usato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="71acb-174">Capture device used by the caller.</span></span> <span data-ttu-id="71acb-175">A cui si fa riferimento dalla <a href="lync-server-2013-device-table.md">tabella dei dispositivi in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-177">int</span><span class="sxs-lookup"><span data-stu-id="71acb-177">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-178">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-179">Dispositivo di rendering usato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="71acb-179">Render device used by caller.</span></span> <span data-ttu-id="71acb-180">A cui si fa riferimento dalla <a href="lync-server-2013-device-table.md">tabella dei dispositivi in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-182">int</span><span class="sxs-lookup"><span data-stu-id="71acb-182">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-183">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-184">Driver per il dispositivo di acquisizione del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-186">int</span><span class="sxs-lookup"><span data-stu-id="71acb-186">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-187">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-188">Driver per il dispositivo di rendering del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="71acb-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="71acb-191">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-192">Indica il modo in cui il chiamante si connette alla rete.</span><span class="sxs-lookup"><span data-stu-id="71acb-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="71acb-193">I valori vengono ottenuti dalla <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="71acb-194">I valori tipici sono 0 per una connessione cablata ' 1 per una connessione WiFi; e 3 per una connessione Ethernet.</span><span class="sxs-lookup"><span data-stu-id="71acb-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-196">int</span><span class="sxs-lookup"><span data-stu-id="71acb-196">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-197">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-198">BSSID del chiamante se viene usato wireless.</span><span class="sxs-lookup"><span data-stu-id="71acb-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="71acb-199">A cui si fa riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-201">po'</span><span class="sxs-lookup"><span data-stu-id="71acb-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71acb-202">Collegamento del chiamante.</span><span class="sxs-lookup"><span data-stu-id="71acb-202">The caller's link.</span></span> <span data-ttu-id="71acb-203">1 è una rete privata virtuale (VPN), 0 non è VPN.</span><span class="sxs-lookup"><span data-stu-id="71acb-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-205">decimale (18; 0)</span><span class="sxs-lookup"><span data-stu-id="71acb-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71acb-206">Velocità di collegamento di rete, in bps, per l'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="71acb-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-208">int</span><span class="sxs-lookup"><span data-stu-id="71acb-208">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-209">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-210">Indirizzo IP del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="71acb-210">IP Address of the call receiver.</span></span> <span data-ttu-id="71acb-211">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71acb-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-213">po'</span><span class="sxs-lookup"><span data-stu-id="71acb-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71acb-214">Porta usata dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="71acb-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-216">int</span><span class="sxs-lookup"><span data-stu-id="71acb-216">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-217">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-218">Subnet del chiamato.</span><span class="sxs-lookup"><span data-stu-id="71acb-218">Subnet of callee.</span></span> <span data-ttu-id="71acb-219">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71acb-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-221">po'</span><span class="sxs-lookup"><span data-stu-id="71acb-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71acb-222">1 indica che il destinatario della chiamata si trova all'interno della rete aziendale, 0 indica che il destinatario della chiamata si trova all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="71acb-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-224">int</span><span class="sxs-lookup"><span data-stu-id="71acb-224">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-225">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-226">Indirizzo MAC del destinatario.</span><span class="sxs-lookup"><span data-stu-id="71acb-226">Callee Mac address.</span></span> <span data-ttu-id="71acb-227">A cui si fa riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-229">int</span><span class="sxs-lookup"><span data-stu-id="71acb-229">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-230">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-231">Indirizzo IP del servizio A/V Edge usato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="71acb-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="71acb-232">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71acb-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-234">int</span><span class="sxs-lookup"><span data-stu-id="71acb-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71acb-235">Porta usata nel servizio A/V Edge dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="71acb-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-237">int</span><span class="sxs-lookup"><span data-stu-id="71acb-237">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-238">esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-239">Dispositivo di acquisizione usato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="71acb-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="71acb-240">A cui si fa riferimento dalla <a href="lync-server-2013-device-table.md">tabella dei dispositivi in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-242">int</span><span class="sxs-lookup"><span data-stu-id="71acb-242">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-243">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-244">Dispositivo di rendering usato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="71acb-244">Render device used by the call receiver.</span></span> <span data-ttu-id="71acb-245">A cui si fa riferimento dalla <a href="lync-server-2013-device-table.md">tabella dei dispositivi in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-247">int</span><span class="sxs-lookup"><span data-stu-id="71acb-247">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-248">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-249">Driver per il dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="71acb-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="71acb-250">A cui si fa riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="71acb-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71acb-253">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-254">Driver per il dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="71acb-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="71acb-255">A cui si fa riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="71acb-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="71acb-258">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-259">Indica il modo in cui il chiamato si connette alla rete.</span><span class="sxs-lookup"><span data-stu-id="71acb-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="71acb-260">I valori vengono ottenuti dalla <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="71acb-261">I valori tipici sono 0 per una connessione cablata ' 1 per una connessione WiFi; e 3 per una connessione Ethernet.</span><span class="sxs-lookup"><span data-stu-id="71acb-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-263">int</span><span class="sxs-lookup"><span data-stu-id="71acb-263">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-264">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-265">BSSID di chiamata se viene usato wireless.</span><span class="sxs-lookup"><span data-stu-id="71acb-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="71acb-266">A cui si fa riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-268">po'</span><span class="sxs-lookup"><span data-stu-id="71acb-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71acb-269">Collegamento del destinatario della chiamata; 1 è una rete privata virtuale (VPN), 0 non è VPN.</span><span class="sxs-lookup"><span data-stu-id="71acb-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-271">decimale (18; 0)</span><span class="sxs-lookup"><span data-stu-id="71acb-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71acb-272">Velocità di collegamento di rete, in bps, per l'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="71acb-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-274">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="71acb-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71acb-275">Stretta MOS colloquiale delle sessioni audio (in base a entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="71acb-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-277">int</span><span class="sxs-lookup"><span data-stu-id="71acb-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71acb-278">Si tratta della larghezza di banda effettiva applicata al flusso del lato di invio assegnato in base a varie impostazioni dei criteri (TURN, API, SDP, Policy Server e così via).</span><span class="sxs-lookup"><span data-stu-id="71acb-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="71acb-279">Questa operazione non deve essere confusa con la larghezza di banda effettiva, perché la larghezza di banda effettiva può essere inferiore in base alla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="71acb-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="71acb-280">Si tratta in pratica della larghezza di banda massima che il flusso di invio può bloccare i limiti imposti dalla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="71acb-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-282">smallint</span><span class="sxs-lookup"><span data-stu-id="71acb-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71acb-283">Questa è l'origine del limite di larghezza di banda imposto.</span><span class="sxs-lookup"><span data-stu-id="71acb-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="71acb-284">Descrive la posizione del limite di larghezza di banda ("Policy Server", "TURN server", "modality" e così via).</span><span class="sxs-lookup"><span data-stu-id="71acb-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="71acb-285">A cui si fa riferimento dalla <a href="lync-server-2013-appliedbandwidthsource-table.md">tabella AppliedBandwidthSource in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="71acb-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-286"><strong>Chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-287">po'</span><span class="sxs-lookup"><span data-stu-id="71acb-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71acb-288">Indica se sono state ricevute metriche dal chiamante; 1 è sì, un valore null è no.</span><span class="sxs-lookup"><span data-stu-id="71acb-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-289"><strong>Chiamato</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-290">po'</span><span class="sxs-lookup"><span data-stu-id="71acb-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71acb-291">Indica se le metriche del destinatario della chiamata sono state ricevute; 1 è sì, un valore null è no.</span><span class="sxs-lookup"><span data-stu-id="71acb-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-293">po'</span><span class="sxs-lookup"><span data-stu-id="71acb-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71acb-294">Indica se il report è per una parte della sessione o per la sessione completa.</span><span class="sxs-lookup"><span data-stu-id="71acb-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="71acb-295">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71acb-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-297">po'</span><span class="sxs-lookup"><span data-stu-id="71acb-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71acb-298">Indica se una chiamata è stata classificata come chiamata scadente (valore 1) o come buona chiamata (0).</span><span class="sxs-lookup"><span data-stu-id="71acb-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="71acb-299">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71acb-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="71acb-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71acb-302">Indica se il chiamante è connesso alla rete usando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="71acb-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="71acb-303">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71acb-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="71acb-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71acb-306">Indica se il chiamante è connesso alla rete usando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="71acb-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="71acb-307">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71acb-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-309">int</span><span class="sxs-lookup"><span data-stu-id="71acb-309">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-310">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-311">Indirizzo IP riflessivo dell'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="71acb-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="71acb-312">Nelle organizzazioni che usano NAT (Network Address Translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.</span><span class="sxs-lookup"><span data-stu-id="71acb-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="71acb-313">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71acb-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-315">int</span><span class="sxs-lookup"><span data-stu-id="71acb-315">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-316">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-317">Descrizione del dispositivo per il driver WiFi impiegato dall'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="71acb-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="71acb-318">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71acb-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-320">int</span><span class="sxs-lookup"><span data-stu-id="71acb-320">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-321">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-322">Numero di versione per il driver WiFi impiegato dall'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="71acb-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="71acb-323">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71acb-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-325">int</span><span class="sxs-lookup"><span data-stu-id="71acb-325">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-326">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-327">Indirizzo IP riflessivo dell'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="71acb-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="71acb-328">Nelle organizzazioni che usano NAT (Network Address Translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.</span><span class="sxs-lookup"><span data-stu-id="71acb-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="71acb-329">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71acb-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71acb-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-331">int</span><span class="sxs-lookup"><span data-stu-id="71acb-331">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-332">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-333">Descrizione del dispositivo per il driver WiFi impiegato dall'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="71acb-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="71acb-334">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71acb-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71acb-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="71acb-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="71acb-336">int</span><span class="sxs-lookup"><span data-stu-id="71acb-336">int</span></span></p></td>
<td><p><span data-ttu-id="71acb-337">Esterna</span><span class="sxs-lookup"><span data-stu-id="71acb-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71acb-338">Numero di versione per il driver WiFi impiegato dall'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="71acb-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="71acb-339">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71acb-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

