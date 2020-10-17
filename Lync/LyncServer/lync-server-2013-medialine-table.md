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
ms.openlocfilehash: 03f967b50c2fa9eae4f2599ce96dc9c592a57006
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516143"
---
# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="736b6-102">Tabella MediaLine in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="736b6-102">MediaLine table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="736b6-103">_**Ultimo argomento modificato:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="736b6-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="736b6-104">Ogni record rappresenta una linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="736b6-104">Each record represents one media line.</span></span> <span data-ttu-id="736b6-105">(Una sessione audio di solito contiene una linea media audio.</span><span class="sxs-lookup"><span data-stu-id="736b6-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="736b6-106">Una sessione audio e video (A/V) solitamente contiene una linea media audio e una linea multimediale video, anche se la sessione potrebbe contenere due linee multimediali video se viene utilizzato un dispositivo per conferenze o se viene utilizzata la visualizzazione raccolta.</span><span class="sxs-lookup"><span data-stu-id="736b6-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="736b6-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="736b6-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="736b6-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="736b6-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="736b6-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-112">datetime</span><span class="sxs-lookup"><span data-stu-id="736b6-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="736b6-113">Principale</span><span class="sxs-lookup"><span data-stu-id="736b6-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="736b6-114">A cui viene fatto riferimento dalla <a href="lync-server-2013-session-table.md">tabella Session in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-116">int</span><span class="sxs-lookup"><span data-stu-id="736b6-116">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-117">Principale</span><span class="sxs-lookup"><span data-stu-id="736b6-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="736b6-118">A cui viene fatto riferimento dalla <a href="lync-server-2013-session-table.md">tabella Session in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="736b6-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="736b6-121">Principale</span><span class="sxs-lookup"><span data-stu-id="736b6-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="736b6-122">0 è l'audio principale, 1 è il video principale e 2 è un video panoramico, 3 è la condivisione di applicazioni/desktop.</span><span class="sxs-lookup"><span data-stu-id="736b6-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="736b6-123">Questa etichetta deve essere univoca all'interno di una singola sessione.</span><span class="sxs-lookup"><span data-stu-id="736b6-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="736b6-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="736b6-126">Questa colonna è presente ma non utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="736b6-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="736b6-127">Le informazioni sulla connettività utilizzata per una linea multimediale vengono acquisite nelle colonne CallerConnectivityICE e CalleeConnectivityICE.</span><span class="sxs-lookup"><span data-stu-id="736b6-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-129">int</span><span class="sxs-lookup"><span data-stu-id="736b6-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="736b6-130">Informazioni sul processo di creazione di connettività interattive (ICE) descritto in flag di bit.</span><span class="sxs-lookup"><span data-stu-id="736b6-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="736b6-131">Per informazioni dettagliate, vedere la sezione relativa alla <em>qualità delle specifiche del protocollo di monitoraggio del server</em>, disponibile per il download.</span><span class="sxs-lookup"><span data-stu-id="736b6-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-133">int</span><span class="sxs-lookup"><span data-stu-id="736b6-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="736b6-134">Uguale a CallerIceWarningFlags, ma da parte del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="736b6-135">Per informazioni dettagliate, vedere la sezione relativa alla <em>qualità delle specifiche del protocollo di monitoraggio del server</em>, disponibile per il download.</span><span class="sxs-lookup"><span data-stu-id="736b6-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-136"><strong>Sicurezza</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="736b6-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="736b6-138">Il profilo di sicurezza in uso.</span><span class="sxs-lookup"><span data-stu-id="736b6-138">The security profile in use.</span></span> <span data-ttu-id="736b6-139">0 per NESSUNA, 1 per SRTP, 2 per V1.</span><span class="sxs-lookup"><span data-stu-id="736b6-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-140"><strong>Trasporto</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="736b6-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="736b6-142">0 per UDP, 1 per TCP.</span><span class="sxs-lookup"><span data-stu-id="736b6-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-144">int</span><span class="sxs-lookup"><span data-stu-id="736b6-144">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-145">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-146">Indirizzo IP del chiamante.</span><span class="sxs-lookup"><span data-stu-id="736b6-146">IP Address of the caller.</span></span> <span data-ttu-id="736b6-147">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="736b6-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-149">int</span><span class="sxs-lookup"><span data-stu-id="736b6-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="736b6-150">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="736b6-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-152">int</span><span class="sxs-lookup"><span data-stu-id="736b6-152">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-153"> Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-154">La subnet del chiamante.</span><span class="sxs-lookup"><span data-stu-id="736b6-154">The subnet of the caller.</span></span> <span data-ttu-id="736b6-155">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="736b6-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-157">po'</span><span class="sxs-lookup"><span data-stu-id="736b6-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="736b6-158">1 indica che il chiamante è all'interno della rete aziendale, 0 invece indica che è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="736b6-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-160">int</span><span class="sxs-lookup"><span data-stu-id="736b6-160">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-161">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-162">Indirizzo MAC del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-164">int</span><span class="sxs-lookup"><span data-stu-id="736b6-164">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-165">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-166">Indirizzo IP del servizio A/V Edge di Lync Server utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="736b6-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="736b6-167">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="736b6-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-169">int</span><span class="sxs-lookup"><span data-stu-id="736b6-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="736b6-170">Porta utilizzata nel servizio A/V Edge dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="736b6-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-172">int</span><span class="sxs-lookup"><span data-stu-id="736b6-172">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-173">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-174">Dispositivo di acquisizione utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="736b6-174">Capture device used by the caller.</span></span> <span data-ttu-id="736b6-175">A cui viene fatto riferimento dalla <a href="lync-server-2013-device-table.md">tabella Device in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-177">int</span><span class="sxs-lookup"><span data-stu-id="736b6-177">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-178">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-179">Dispositivo di rendering utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="736b6-179">Render device used by caller.</span></span> <span data-ttu-id="736b6-180">A cui viene fatto riferimento dalla <a href="lync-server-2013-device-table.md">tabella Device in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-182">int</span><span class="sxs-lookup"><span data-stu-id="736b6-182">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-183">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-184">Driver per il dispositivo di acquisizione del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-186">int</span><span class="sxs-lookup"><span data-stu-id="736b6-186">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-187">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-188">Driver per il dispositivo di rendering del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="736b6-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="736b6-191">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-192">Indica il modo in cui il chiamante si è connesso alla rete.</span><span class="sxs-lookup"><span data-stu-id="736b6-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="736b6-193">I valori vengono ottenuti dalla <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="736b6-194">I valori tipici sono 0 per una connessione cablata ' 1 per una connessione WiFi; e 3 per una connessione Ethernet.</span><span class="sxs-lookup"><span data-stu-id="736b6-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-196">int</span><span class="sxs-lookup"><span data-stu-id="736b6-196">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-197">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-198">BSSID del chiamante se viene utilizzata la tecnologia wireless.</span><span class="sxs-lookup"><span data-stu-id="736b6-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="736b6-199">Riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-201">po'</span><span class="sxs-lookup"><span data-stu-id="736b6-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="736b6-202">Il collegamento del chiamante.</span><span class="sxs-lookup"><span data-stu-id="736b6-202">The caller's link.</span></span> <span data-ttu-id="736b6-203">1 indica una rete privata virtuale (VPN), 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="736b6-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-205">decimale (18,0)</span><span class="sxs-lookup"><span data-stu-id="736b6-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="736b6-206">Velocità del collegamento di rete, in bps, per l'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="736b6-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-208">int</span><span class="sxs-lookup"><span data-stu-id="736b6-208">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-209">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-210">Indirizzo IP del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-210">IP Address of the call receiver.</span></span> <span data-ttu-id="736b6-211">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="736b6-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-213">po'</span><span class="sxs-lookup"><span data-stu-id="736b6-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="736b6-214">Porta utilizzata dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-216">int</span><span class="sxs-lookup"><span data-stu-id="736b6-216">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-217">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-218">Subnet del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-218">Subnet of callee.</span></span> <span data-ttu-id="736b6-219">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="736b6-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-221">po'</span><span class="sxs-lookup"><span data-stu-id="736b6-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="736b6-222">1 indica che il destinatario della chiamata è all'interno della rete aziendale, 0 indica che il destinatario della chiamata è esterno alla rete.</span><span class="sxs-lookup"><span data-stu-id="736b6-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-224">int</span><span class="sxs-lookup"><span data-stu-id="736b6-224">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-225">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-226">Indirizzo MAC del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-226">Callee Mac address.</span></span> <span data-ttu-id="736b6-227">A cui viene fatto riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-229">int</span><span class="sxs-lookup"><span data-stu-id="736b6-229">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-230">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-231">Indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="736b6-232">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="736b6-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-234">int</span><span class="sxs-lookup"><span data-stu-id="736b6-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="736b6-235">Porta utilizzata nel servizio A/V Edge dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-237">int</span><span class="sxs-lookup"><span data-stu-id="736b6-237">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-238">stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-239">Dispositivo di acquisizione utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="736b6-240">A cui viene fatto riferimento dalla <a href="lync-server-2013-device-table.md">tabella Device in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-242">int</span><span class="sxs-lookup"><span data-stu-id="736b6-242">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-243">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-244">Dispositivo di rendering utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-244">Render device used by the call receiver.</span></span> <span data-ttu-id="736b6-245">A cui viene fatto riferimento dalla <a href="lync-server-2013-device-table.md">tabella Device in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-247">int</span><span class="sxs-lookup"><span data-stu-id="736b6-247">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-248">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-249">Driver per il dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="736b6-250">Riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="736b6-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="736b6-253">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-254">Driver del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="736b6-255">Riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="736b6-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="736b6-258">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-259">Indica il modo in cui il destinatario della chiamata è connesso alla rete.</span><span class="sxs-lookup"><span data-stu-id="736b6-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="736b6-260">I valori vengono ottenuti dalla <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="736b6-261">I valori tipici sono 0 per una connessione cablata ' 1 per una connessione WiFi; e 3 per una connessione Ethernet.</span><span class="sxs-lookup"><span data-stu-id="736b6-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-263">int</span><span class="sxs-lookup"><span data-stu-id="736b6-263">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-264">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-265">BSSID del destinatario della chiamata se viene utilizzato wireless.</span><span class="sxs-lookup"><span data-stu-id="736b6-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="736b6-266">Riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-268">po'</span><span class="sxs-lookup"><span data-stu-id="736b6-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="736b6-269">Il collegamento del destinatario della chiamata; 1 è la rete privata virtuale (VPN), 0 non è VPN.</span><span class="sxs-lookup"><span data-stu-id="736b6-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-271">decimale (18,0)</span><span class="sxs-lookup"><span data-stu-id="736b6-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="736b6-272">Velocità del collegamento di rete, in bps, per l'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-274">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="736b6-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="736b6-275">Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="736b6-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-277">int</span><span class="sxs-lookup"><span data-stu-id="736b6-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="736b6-278">Si tratta della larghezza di banda effettiva applicata al flusso del server di invio specificato, in cui sono disponibili diverse impostazioni di criteri (attiva, API, SDP, criteri e così via).</span><span class="sxs-lookup"><span data-stu-id="736b6-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="736b6-279">Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="736b6-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="736b6-280">Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="736b6-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-282">smallint</span><span class="sxs-lookup"><span data-stu-id="736b6-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="736b6-283">Origine del limite della larghezza di banda imposto.</span><span class="sxs-lookup"><span data-stu-id="736b6-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="736b6-284">Descrive la posizione del limite della larghezza di banda ("server criteri", "Attiva server", "modalità" e così via).</span><span class="sxs-lookup"><span data-stu-id="736b6-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="736b6-285">A cui viene fatto riferimento dalla <a href="lync-server-2013-appliedbandwidthsource-table.md">tabella AppliedBandwidthSource in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="736b6-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-286"><strong>Chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-287">po'</span><span class="sxs-lookup"><span data-stu-id="736b6-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="736b6-288">Indica se le metriche del chiamante sono state ricevute; 1 è sì, un valore null è no.</span><span class="sxs-lookup"><span data-stu-id="736b6-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-289"><strong>Destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-290">po'</span><span class="sxs-lookup"><span data-stu-id="736b6-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="736b6-291">Indica se le metriche provenienti dal destinatario della chiamata sono state ricevute; 1 è sì, un valore null è no.</span><span class="sxs-lookup"><span data-stu-id="736b6-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-293">po'</span><span class="sxs-lookup"><span data-stu-id="736b6-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="736b6-294">Indica se il report è per una parte della sessione o per la sessione completa.</span><span class="sxs-lookup"><span data-stu-id="736b6-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="736b6-295">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="736b6-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-297">po'</span><span class="sxs-lookup"><span data-stu-id="736b6-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="736b6-298">Indica se una chiamata è stata classificata come chiamata scadente (valore 1) o come buona chiamata (0).</span><span class="sxs-lookup"><span data-stu-id="736b6-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="736b6-299">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="736b6-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="736b6-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="736b6-302">Indica se il chiamante ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="736b6-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="736b6-303">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="736b6-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="736b6-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="736b6-306">Indica se il chiamante ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="736b6-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="736b6-307">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="736b6-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-309">int</span><span class="sxs-lookup"><span data-stu-id="736b6-309">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-310">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-311">Indirizzo IP riflessivo dell'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="736b6-312">Nelle organizzazioni che utilizzano NAT (Network Address Translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.</span><span class="sxs-lookup"><span data-stu-id="736b6-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="736b6-313">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="736b6-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-315">int</span><span class="sxs-lookup"><span data-stu-id="736b6-315">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-316">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-317">Descrizione del dispositivo per il driver WiFi impiegato dall'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="736b6-318">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="736b6-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-320">int</span><span class="sxs-lookup"><span data-stu-id="736b6-320">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-321">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-322">Numero di versione del driver WiFi impiegato dall'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="736b6-323">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="736b6-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-325">int</span><span class="sxs-lookup"><span data-stu-id="736b6-325">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-326">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-327">Indirizzo IP riflessivo dell'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="736b6-328">Nelle organizzazioni che utilizzano NAT (Network Address Translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.</span><span class="sxs-lookup"><span data-stu-id="736b6-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="736b6-329">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="736b6-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="736b6-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-331">int</span><span class="sxs-lookup"><span data-stu-id="736b6-331">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-332">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-333">Descrizione del dispositivo per il driver WiFi impiegato dall'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="736b6-334">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="736b6-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="736b6-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="736b6-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="736b6-336">int</span><span class="sxs-lookup"><span data-stu-id="736b6-336">int</span></span></p></td>
<td><p><span data-ttu-id="736b6-337">Stranieri</span><span class="sxs-lookup"><span data-stu-id="736b6-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="736b6-338">Numero di versione del driver WiFi impiegato dall'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="736b6-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="736b6-339">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="736b6-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

