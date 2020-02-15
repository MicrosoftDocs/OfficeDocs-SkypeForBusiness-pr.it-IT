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
ms.openlocfilehash: 3496b8fe96e2bdfcbb49ec0155d66ad4eeb106fa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="22423-102">Tabella MediaLine in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22423-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22423-103">_**Ultimo argomento modificato:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="22423-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="22423-104">Ogni record rappresenta una linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="22423-104">Each record represents one media line.</span></span> <span data-ttu-id="22423-105">(Una sessione audio di solito contiene una linea media audio.</span><span class="sxs-lookup"><span data-stu-id="22423-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="22423-106">Una sessione audio e video (A/V) solitamente contiene una linea media audio e una linea multimediale video, anche se la sessione potrebbe contenere due linee multimediali video se viene utilizzato un dispositivo per conferenze o se viene utilizzata la visualizzazione raccolta.</span><span class="sxs-lookup"><span data-stu-id="22423-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22423-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="22423-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="22423-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="22423-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="22423-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="22423-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="22423-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="22423-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22423-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="22423-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-112">datetime</span><span class="sxs-lookup"><span data-stu-id="22423-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="22423-113">Principale</span><span class="sxs-lookup"><span data-stu-id="22423-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="22423-114">A cui viene fatto riferimento dalla <a href="lync-server-2013-session-table.md">tabella Session in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="22423-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-116">int</span><span class="sxs-lookup"><span data-stu-id="22423-116">int</span></span></p></td>
<td><p><span data-ttu-id="22423-117">Principale</span><span class="sxs-lookup"><span data-stu-id="22423-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="22423-118">A cui viene fatto riferimento dalla <a href="lync-server-2013-session-table.md">tabella Session in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="22423-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="22423-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="22423-121">Principale</span><span class="sxs-lookup"><span data-stu-id="22423-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="22423-122">0 è l'audio principale, 1 è il video principale e 2 è un video panoramico, 3 è la condivisione di applicazioni/desktop.</span><span class="sxs-lookup"><span data-stu-id="22423-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="22423-123">Questa etichetta deve essere univoca all'interno di una singola sessione.</span><span class="sxs-lookup"><span data-stu-id="22423-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="22423-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="22423-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22423-126">Questa colonna è presente ma non utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22423-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="22423-127">Le informazioni sulla connettività utilizzata per una linea multimediale vengono acquisite nelle colonne CallerConnectivityICE e CalleeConnectivityICE.</span><span class="sxs-lookup"><span data-stu-id="22423-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="22423-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-129">int</span><span class="sxs-lookup"><span data-stu-id="22423-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22423-130">Informazioni sul processo di creazione di connettività interattive (ICE) descritto in flag di bit.</span><span class="sxs-lookup"><span data-stu-id="22423-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="22423-131">Per informazioni dettagliate, vedere la sezione relativa alla <em>qualità delle specifiche del protocollo di monitoraggio del server</em>, disponibile per il download.</span><span class="sxs-lookup"><span data-stu-id="22423-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="22423-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-133">int</span><span class="sxs-lookup"><span data-stu-id="22423-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22423-134">Uguale a CallerIceWarningFlags, ma da parte del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="22423-135">Per informazioni dettagliate, vedere la sezione relativa alla <em>qualità delle specifiche del protocollo di monitoraggio del server</em>, disponibile per il download.</span><span class="sxs-lookup"><span data-stu-id="22423-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-136"><strong>Sicurezza</strong></span><span class="sxs-lookup"><span data-stu-id="22423-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="22423-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22423-138">Il profilo di sicurezza in uso.</span><span class="sxs-lookup"><span data-stu-id="22423-138">The security profile in use.</span></span> <span data-ttu-id="22423-139">0 per NESSUNA, 1 per SRTP, 2 per V1.</span><span class="sxs-lookup"><span data-stu-id="22423-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-140"><strong>Trasporto</strong></span><span class="sxs-lookup"><span data-stu-id="22423-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="22423-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22423-142">0 per UDP, 1 per TCP.</span><span class="sxs-lookup"><span data-stu-id="22423-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="22423-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-144">int</span><span class="sxs-lookup"><span data-stu-id="22423-144">int</span></span></p></td>
<td><p><span data-ttu-id="22423-145">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-146">Indirizzo IP del chiamante.</span><span class="sxs-lookup"><span data-stu-id="22423-146">IP Address of the caller.</span></span> <span data-ttu-id="22423-147">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="22423-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="22423-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-149">int</span><span class="sxs-lookup"><span data-stu-id="22423-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22423-150">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="22423-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="22423-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-152">int</span><span class="sxs-lookup"><span data-stu-id="22423-152">int</span></span></p></td>
<td><p><span data-ttu-id="22423-153"> Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-154">La subnet del chiamante.</span><span class="sxs-lookup"><span data-stu-id="22423-154">The subnet of the caller.</span></span> <span data-ttu-id="22423-155">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="22423-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="22423-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-157">po'</span><span class="sxs-lookup"><span data-stu-id="22423-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22423-158">1 indica che il chiamante è all'interno della rete aziendale, 0 invece indica che è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="22423-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="22423-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-160">int</span><span class="sxs-lookup"><span data-stu-id="22423-160">int</span></span></p></td>
<td><p><span data-ttu-id="22423-161">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-162">Indirizzo MAC del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="22423-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-164">int</span><span class="sxs-lookup"><span data-stu-id="22423-164">int</span></span></p></td>
<td><p><span data-ttu-id="22423-165">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-166">Indirizzo IP del servizio A/V Edge di Lync Server utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="22423-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="22423-167">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="22423-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="22423-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-169">int</span><span class="sxs-lookup"><span data-stu-id="22423-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22423-170">Porta utilizzata nel servizio A/V Edge dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="22423-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="22423-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-172">int</span><span class="sxs-lookup"><span data-stu-id="22423-172">int</span></span></p></td>
<td><p><span data-ttu-id="22423-173">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-174">Dispositivo di acquisizione utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="22423-174">Capture device used by the caller.</span></span> <span data-ttu-id="22423-175">A cui viene fatto riferimento dalla <a href="lync-server-2013-device-table.md">tabella Device in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="22423-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-177">int</span><span class="sxs-lookup"><span data-stu-id="22423-177">int</span></span></p></td>
<td><p><span data-ttu-id="22423-178">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-179">Dispositivo di rendering utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="22423-179">Render device used by caller.</span></span> <span data-ttu-id="22423-180">A cui viene fatto riferimento dalla <a href="lync-server-2013-device-table.md">tabella Device in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="22423-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-182">int</span><span class="sxs-lookup"><span data-stu-id="22423-182">int</span></span></p></td>
<td><p><span data-ttu-id="22423-183">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-184">Driver per il dispositivo di acquisizione del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="22423-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-186">int</span><span class="sxs-lookup"><span data-stu-id="22423-186">int</span></span></p></td>
<td><p><span data-ttu-id="22423-187">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-188">Driver per il dispositivo di rendering del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="22423-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="22423-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="22423-191">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-192">Indica il modo in cui il chiamante si è connesso alla rete.</span><span class="sxs-lookup"><span data-stu-id="22423-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="22423-193">I valori vengono ottenuti dalla <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="22423-194">I valori tipici sono 0 per una connessione cablata ' 1 per una connessione WiFi; e 3 per una connessione Ethernet.</span><span class="sxs-lookup"><span data-stu-id="22423-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="22423-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-196">int</span><span class="sxs-lookup"><span data-stu-id="22423-196">int</span></span></p></td>
<td><p><span data-ttu-id="22423-197">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-198">BSSID del chiamante se viene utilizzata la tecnologia wireless.</span><span class="sxs-lookup"><span data-stu-id="22423-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="22423-199">Riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="22423-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-201">po'</span><span class="sxs-lookup"><span data-stu-id="22423-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="22423-202">Il collegamento del chiamante.</span><span class="sxs-lookup"><span data-stu-id="22423-202">The caller's link.</span></span> <span data-ttu-id="22423-203">1 indica una rete privata virtuale (VPN), 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="22423-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="22423-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-205">decimale (18,0)</span><span class="sxs-lookup"><span data-stu-id="22423-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="22423-206">Velocità del collegamento di rete, in bps, per l'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="22423-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="22423-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-208">int</span><span class="sxs-lookup"><span data-stu-id="22423-208">int</span></span></p></td>
<td><p><span data-ttu-id="22423-209">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-210">Indirizzo IP del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-210">IP Address of the call receiver.</span></span> <span data-ttu-id="22423-211">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="22423-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="22423-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-213">po'</span><span class="sxs-lookup"><span data-stu-id="22423-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="22423-214">Porta utilizzata dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="22423-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-216">int</span><span class="sxs-lookup"><span data-stu-id="22423-216">int</span></span></p></td>
<td><p><span data-ttu-id="22423-217">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-218">Subnet del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-218">Subnet of callee.</span></span> <span data-ttu-id="22423-219">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="22423-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="22423-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-221">po'</span><span class="sxs-lookup"><span data-stu-id="22423-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22423-222">1 indica che il destinatario della chiamata è all'interno della rete aziendale, 0 indica che il destinatario della chiamata è esterno alla rete.</span><span class="sxs-lookup"><span data-stu-id="22423-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="22423-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-224">int</span><span class="sxs-lookup"><span data-stu-id="22423-224">int</span></span></p></td>
<td><p><span data-ttu-id="22423-225">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-226">Indirizzo MAC del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-226">Callee Mac address.</span></span> <span data-ttu-id="22423-227">A cui viene fatto riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="22423-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-229">int</span><span class="sxs-lookup"><span data-stu-id="22423-229">int</span></span></p></td>
<td><p><span data-ttu-id="22423-230">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-231">Indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="22423-232">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="22423-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="22423-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-234">int</span><span class="sxs-lookup"><span data-stu-id="22423-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22423-235">Porta utilizzata nel servizio A/V Edge dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="22423-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-237">int</span><span class="sxs-lookup"><span data-stu-id="22423-237">int</span></span></p></td>
<td><p><span data-ttu-id="22423-238">stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-239">Dispositivo di acquisizione utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="22423-240">A cui viene fatto riferimento dalla <a href="lync-server-2013-device-table.md">tabella Device in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="22423-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-242">int</span><span class="sxs-lookup"><span data-stu-id="22423-242">int</span></span></p></td>
<td><p><span data-ttu-id="22423-243">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-244">Dispositivo di rendering utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-244">Render device used by the call receiver.</span></span> <span data-ttu-id="22423-245">A cui viene fatto riferimento dalla <a href="lync-server-2013-device-table.md">tabella Device in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="22423-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-247">int</span><span class="sxs-lookup"><span data-stu-id="22423-247">int</span></span></p></td>
<td><p><span data-ttu-id="22423-248">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-249">Driver per il dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="22423-250">Riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="22423-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="22423-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="22423-253">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-254">Driver del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="22423-255">Riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="22423-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="22423-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="22423-258">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-259">Indica il modo in cui il destinatario della chiamata è connesso alla rete.</span><span class="sxs-lookup"><span data-stu-id="22423-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="22423-260">I valori vengono ottenuti dalla <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="22423-261">I valori tipici sono 0 per una connessione cablata ' 1 per una connessione WiFi; e 3 per una connessione Ethernet.</span><span class="sxs-lookup"><span data-stu-id="22423-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="22423-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-263">int</span><span class="sxs-lookup"><span data-stu-id="22423-263">int</span></span></p></td>
<td><p><span data-ttu-id="22423-264">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-265">BSSID del destinatario della chiamata se viene utilizzato wireless.</span><span class="sxs-lookup"><span data-stu-id="22423-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="22423-266">Riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="22423-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-268">po'</span><span class="sxs-lookup"><span data-stu-id="22423-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22423-269">Il collegamento del destinatario della chiamata; 1 è la rete privata virtuale (VPN), 0 non è VPN.</span><span class="sxs-lookup"><span data-stu-id="22423-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="22423-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-271">decimale (18,0)</span><span class="sxs-lookup"><span data-stu-id="22423-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22423-272">Velocità del collegamento di rete, in bps, per l'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="22423-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-274">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="22423-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22423-275">Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="22423-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="22423-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-277">int</span><span class="sxs-lookup"><span data-stu-id="22423-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="22423-278">Si tratta della larghezza di banda effettiva applicata al flusso del server di invio specificato, in cui sono disponibili diverse impostazioni di criteri (attiva, API, SDP, criteri e così via).</span><span class="sxs-lookup"><span data-stu-id="22423-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="22423-279">Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="22423-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="22423-280">Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="22423-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="22423-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-282">smallint</span><span class="sxs-lookup"><span data-stu-id="22423-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="22423-283">Origine del limite della larghezza di banda imposto.</span><span class="sxs-lookup"><span data-stu-id="22423-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="22423-284">Descrive la posizione del limite della larghezza di banda ("server criteri", "Attiva server", "modalità" e così via).</span><span class="sxs-lookup"><span data-stu-id="22423-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="22423-285">A cui viene fatto riferimento dalla <a href="lync-server-2013-appliedbandwidthsource-table.md">tabella AppliedBandwidthSource in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="22423-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-286"><strong>Chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="22423-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-287">po'</span><span class="sxs-lookup"><span data-stu-id="22423-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22423-288">Indica se le metriche del chiamante sono state ricevute; 1 è sì, un valore null è no.</span><span class="sxs-lookup"><span data-stu-id="22423-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-289"><strong>Destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="22423-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-290">po'</span><span class="sxs-lookup"><span data-stu-id="22423-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22423-291">Indica se le metriche provenienti dal destinatario della chiamata sono state ricevute; 1 è sì, un valore null è no.</span><span class="sxs-lookup"><span data-stu-id="22423-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="22423-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-293">po'</span><span class="sxs-lookup"><span data-stu-id="22423-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="22423-294">Indica se il report è per una parte della sessione o per la sessione completa.</span><span class="sxs-lookup"><span data-stu-id="22423-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="22423-295">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22423-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="22423-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-297">po'</span><span class="sxs-lookup"><span data-stu-id="22423-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="22423-298">Indica se una chiamata è stata classificata come chiamata scadente (valore 1) o come buona chiamata (0).</span><span class="sxs-lookup"><span data-stu-id="22423-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="22423-299">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22423-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="22423-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="22423-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="22423-302">Indica se il chiamante ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="22423-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="22423-303">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22423-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="22423-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="22423-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="22423-306">Indica se il chiamante ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="22423-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="22423-307">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22423-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="22423-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-309">int</span><span class="sxs-lookup"><span data-stu-id="22423-309">int</span></span></p></td>
<td><p><span data-ttu-id="22423-310">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-311">Indirizzo IP riflessivo dell'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="22423-312">Nelle organizzazioni che utilizzano NAT (Network Address Translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.</span><span class="sxs-lookup"><span data-stu-id="22423-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="22423-313">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22423-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="22423-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-315">int</span><span class="sxs-lookup"><span data-stu-id="22423-315">int</span></span></p></td>
<td><p><span data-ttu-id="22423-316">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-317">Descrizione del dispositivo per il driver WiFi impiegato dall'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="22423-318">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22423-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="22423-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-320">int</span><span class="sxs-lookup"><span data-stu-id="22423-320">int</span></span></p></td>
<td><p><span data-ttu-id="22423-321">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-322">Numero di versione del driver WiFi impiegato dall'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="22423-323">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22423-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="22423-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-325">int</span><span class="sxs-lookup"><span data-stu-id="22423-325">int</span></span></p></td>
<td><p><span data-ttu-id="22423-326">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-327">Indirizzo IP riflessivo dell'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="22423-328">Nelle organizzazioni che utilizzano NAT (Network Address Translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.</span><span class="sxs-lookup"><span data-stu-id="22423-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="22423-329">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22423-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22423-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="22423-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-331">int</span><span class="sxs-lookup"><span data-stu-id="22423-331">int</span></span></p></td>
<td><p><span data-ttu-id="22423-332">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-333">Descrizione del dispositivo per il driver WiFi impiegato dall'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="22423-334">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22423-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22423-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="22423-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="22423-336">int</span><span class="sxs-lookup"><span data-stu-id="22423-336">int</span></span></p></td>
<td><p><span data-ttu-id="22423-337">Stranieri</span><span class="sxs-lookup"><span data-stu-id="22423-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22423-338">Numero di versione del driver WiFi impiegato dall'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="22423-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="22423-339">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22423-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

