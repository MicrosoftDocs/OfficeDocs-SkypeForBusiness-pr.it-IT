---
title: 'Lync Server 2013: Tabella MediaLine'
description: 'Lync Server 2013: Tabella MediaLine.'
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
ms.openlocfilehash: 2acea8e14ba0608d9ebf72a48f888bfc4501fae3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572112"
---
# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="7cb33-103">Tabella MediaLine in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cb33-103">MediaLine table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cb33-104">_**Ultimo argomento modificato:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="7cb33-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="7cb33-105">Ogni record rappresenta una linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="7cb33-105">Each record represents one media line.</span></span> <span data-ttu-id="7cb33-106">(Una sessione audio di solito contiene una linea media audio.</span><span class="sxs-lookup"><span data-stu-id="7cb33-106">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="7cb33-107">Una sessione audio e video (A/V) solitamente contiene una linea media audio e una linea multimediale video, anche se la sessione potrebbe contenere due linee multimediali video se viene utilizzato un dispositivo per conferenze o se viene utilizzata la visualizzazione raccolta.</span><span class="sxs-lookup"><span data-stu-id="7cb33-107">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cb33-108"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7cb33-109"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7cb33-110"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7cb33-111"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-112"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-113">datetime</span><span class="sxs-lookup"><span data-stu-id="7cb33-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="7cb33-114">Principale</span><span class="sxs-lookup"><span data-stu-id="7cb33-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="7cb33-115">A cui viene fatto riferimento dalla <a href="lync-server-2013-session-table.md">tabella Session in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-115">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-117">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-117">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-118">Principale</span><span class="sxs-lookup"><span data-stu-id="7cb33-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="7cb33-119">A cui viene fatto riferimento dalla <a href="lync-server-2013-session-table.md">tabella Session in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-119">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-120"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-120"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-121">tinyint</span><span class="sxs-lookup"><span data-stu-id="7cb33-121">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7cb33-122">Principale</span><span class="sxs-lookup"><span data-stu-id="7cb33-122">Primary</span></span></p></td>
<td><p><span data-ttu-id="7cb33-123">0 è l'audio principale, 1 è il video principale e 2 è un video panoramico, 3 è la condivisione di applicazioni/desktop.</span><span class="sxs-lookup"><span data-stu-id="7cb33-123">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="7cb33-124">Questa etichetta deve essere univoca all'interno di una singola sessione.</span><span class="sxs-lookup"><span data-stu-id="7cb33-124">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-125"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-125"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-126">tinyint</span><span class="sxs-lookup"><span data-stu-id="7cb33-126">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7cb33-127">Questa colonna è presente ma non utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7cb33-127">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="7cb33-128">Le informazioni sulla connettività utilizzata per una linea multimediale vengono acquisite nelle colonne CallerConnectivityICE e CalleeConnectivityICE.</span><span class="sxs-lookup"><span data-stu-id="7cb33-128">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-129"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-129"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-130">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7cb33-131">Informazioni sul processo di creazione di connettività interattive (ICE) descritto in flag di bit.</span><span class="sxs-lookup"><span data-stu-id="7cb33-131">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="7cb33-132">Per informazioni dettagliate, vedere la sezione relativa alla <em>qualità delle specifiche del protocollo di monitoraggio del server</em>, disponibile per il download.</span><span class="sxs-lookup"><span data-stu-id="7cb33-132">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-133"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-133"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-134">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7cb33-135">Uguale a CallerIceWarningFlags, ma da parte del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-135">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="7cb33-136">Per informazioni dettagliate, vedere la sezione relativa alla <em>qualità delle specifiche del protocollo di monitoraggio del server</em>, disponibile per il download.</span><span class="sxs-lookup"><span data-stu-id="7cb33-136">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-137"><strong>Sicurezza</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-137"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-138">tinyint</span><span class="sxs-lookup"><span data-stu-id="7cb33-138">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7cb33-139">Il profilo di sicurezza in uso.</span><span class="sxs-lookup"><span data-stu-id="7cb33-139">The security profile in use.</span></span> <span data-ttu-id="7cb33-140">0 per NESSUNA, 1 per SRTP, 2 per V1.</span><span class="sxs-lookup"><span data-stu-id="7cb33-140">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-141"><strong>Trasporto</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-141"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-142">tinyint</span><span class="sxs-lookup"><span data-stu-id="7cb33-142">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7cb33-143">0 per UDP, 1 per TCP.</span><span class="sxs-lookup"><span data-stu-id="7cb33-143">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-144"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-144"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-145">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-145">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-146">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-147">Indirizzo IP del chiamante.</span><span class="sxs-lookup"><span data-stu-id="7cb33-147">IP Address of the caller.</span></span> <span data-ttu-id="7cb33-148">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cb33-148">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-149"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-149"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-150">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7cb33-151">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="7cb33-151">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-152"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-152"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-153">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-153">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-154"> Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-154"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-155">La subnet del chiamante.</span><span class="sxs-lookup"><span data-stu-id="7cb33-155">The subnet of the caller.</span></span> <span data-ttu-id="7cb33-156">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cb33-156">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-157"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-157"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-158">po'</span><span class="sxs-lookup"><span data-stu-id="7cb33-158">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7cb33-159">1 indica che il chiamante è all'interno della rete aziendale, 0 invece indica che è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="7cb33-159">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-160"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-160"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-161">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-161">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-162">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-163">Indirizzo MAC del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-163">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-164"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-164"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-165">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-165">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-166">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-167">Indirizzo IP del servizio A/V Edge di Lync Server utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="7cb33-167">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="7cb33-168">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cb33-168">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-169"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-169"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-170">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7cb33-171">Porta utilizzata nel servizio A/V Edge dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="7cb33-171">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-172"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-172"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-173">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-173">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-174">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-175">Dispositivo di acquisizione utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="7cb33-175">Capture device used by the caller.</span></span> <span data-ttu-id="7cb33-176">A cui viene fatto riferimento dalla <a href="lync-server-2013-device-table.md">tabella Device in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-176">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-177"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-177"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-178">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-178">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-179">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-179">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-180">Dispositivo di rendering utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="7cb33-180">Render device used by caller.</span></span> <span data-ttu-id="7cb33-181">A cui viene fatto riferimento dalla <a href="lync-server-2013-device-table.md">tabella Device in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-181">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-182"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-182"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-183">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-183">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-184">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-185">Driver per il dispositivo di acquisizione del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-185">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-186"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-186"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-187">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-187">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-188">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-189">Driver per il dispositivo di rendering del chiamante, a cui viene fatto riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-189">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-190"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-190"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-191">tinyint</span><span class="sxs-lookup"><span data-stu-id="7cb33-191">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7cb33-192">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-193">Indica il modo in cui il chiamante si è connesso alla rete.</span><span class="sxs-lookup"><span data-stu-id="7cb33-193">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="7cb33-194">I valori vengono ottenuti dalla <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-194">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="7cb33-195">I valori tipici sono 0 per una connessione cablata ' 1 per una connessione WiFi; e 3 per una connessione Ethernet.</span><span class="sxs-lookup"><span data-stu-id="7cb33-195">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-196"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-196"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-197">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-197">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-198">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-199">BSSID del chiamante se viene utilizzata la tecnologia wireless.</span><span class="sxs-lookup"><span data-stu-id="7cb33-199">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="7cb33-200">Riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-200">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-201"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-201"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-202">po'</span><span class="sxs-lookup"><span data-stu-id="7cb33-202">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cb33-203">Il collegamento del chiamante.</span><span class="sxs-lookup"><span data-stu-id="7cb33-203">The caller's link.</span></span> <span data-ttu-id="7cb33-204">1 indica una rete privata virtuale (VPN), 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="7cb33-204">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-205"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-205"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-206">decimale (18,0)</span><span class="sxs-lookup"><span data-stu-id="7cb33-206">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cb33-207">Velocità del collegamento di rete, in bps, per l'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="7cb33-207">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-208"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-208"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-209">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-209">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-210">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-210">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-211">Indirizzo IP del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-211">IP Address of the call receiver.</span></span> <span data-ttu-id="7cb33-212">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cb33-212">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-213"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-213"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-214">po'</span><span class="sxs-lookup"><span data-stu-id="7cb33-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cb33-215">Porta utilizzata dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-215">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-216"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-216"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-217">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-217">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-218">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-219">Subnet del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-219">Subnet of callee.</span></span> <span data-ttu-id="7cb33-220">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cb33-220">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-221"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-221"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-222">po'</span><span class="sxs-lookup"><span data-stu-id="7cb33-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7cb33-223">1 indica che il destinatario della chiamata è all'interno della rete aziendale, 0 indica che il destinatario della chiamata è esterno alla rete.</span><span class="sxs-lookup"><span data-stu-id="7cb33-223">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-224"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-224"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-225">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-225">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-226">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-226">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-227">Indirizzo MAC del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-227">Callee Mac address.</span></span> <span data-ttu-id="7cb33-228">A cui viene fatto riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-228">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-229"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-229"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-230">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-230">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-231">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-231">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-232">Indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-232">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="7cb33-233">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cb33-233">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-234"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-234"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-235">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-235">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7cb33-236">Porta utilizzata nel servizio A/V Edge dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-236">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-237"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-237"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-238">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-238">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-239">stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-239">foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-240">Dispositivo di acquisizione utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-240">Capture device used by the call receiver.</span></span> <span data-ttu-id="7cb33-241">A cui viene fatto riferimento dalla <a href="lync-server-2013-device-table.md">tabella Device in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-241">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-242"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-242"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-243">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-243">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-244">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-244">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-245">Dispositivo di rendering utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-245">Render device used by the call receiver.</span></span> <span data-ttu-id="7cb33-246">A cui viene fatto riferimento dalla <a href="lync-server-2013-device-table.md">tabella Device in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-246">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-247"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-247"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-248">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-248">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-249">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-249">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-250">Driver per il dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-250">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="7cb33-251">Riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-251">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-252"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-252"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-253">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7cb33-253">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7cb33-254">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-254">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-255">Driver del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-255">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="7cb33-256">Riferimento dalla <a href="lync-server-2013-devicedriver-table.md">tabella QRTDDriver in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-256">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-257"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-257"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-258">tinyint</span><span class="sxs-lookup"><span data-stu-id="7cb33-258">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7cb33-259">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-259">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-260">Indica il modo in cui il destinatario della chiamata è connesso alla rete.</span><span class="sxs-lookup"><span data-stu-id="7cb33-260">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="7cb33-261">I valori vengono ottenuti dalla <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-261">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="7cb33-262">I valori tipici sono 0 per una connessione cablata ' 1 per una connessione WiFi; e 3 per una connessione Ethernet.</span><span class="sxs-lookup"><span data-stu-id="7cb33-262">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-263"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-263"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-264">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-264">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-265">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-265">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-266">BSSID del destinatario della chiamata se viene utilizzato wireless.</span><span class="sxs-lookup"><span data-stu-id="7cb33-266">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="7cb33-267">Riferimento dalla <a href="lync-server-2013-macaddress-table.md">tabella MacAddress in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-267">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-268"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-268"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-269">po'</span><span class="sxs-lookup"><span data-stu-id="7cb33-269">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7cb33-270">Il collegamento del destinatario della chiamata; 1 è la rete privata virtuale (VPN), 0 non è VPN.</span><span class="sxs-lookup"><span data-stu-id="7cb33-270">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-271"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-271"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-272">decimale (18,0)</span><span class="sxs-lookup"><span data-stu-id="7cb33-272">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7cb33-273">Velocità del collegamento di rete, in bps, per l'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-273">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-274"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-274"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-275">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="7cb33-275">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7cb33-276">Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="7cb33-276">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-277"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-277"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-278">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-278">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cb33-279">Si tratta della larghezza di banda effettiva applicata al flusso del server di invio specificato, in cui sono disponibili diverse impostazioni di criteri (attiva, API, SDP, criteri e così via).</span><span class="sxs-lookup"><span data-stu-id="7cb33-279">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="7cb33-280">Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="7cb33-280">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="7cb33-281">Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="7cb33-281">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-282"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-282"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-283">smallint</span><span class="sxs-lookup"><span data-stu-id="7cb33-283">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cb33-284">Origine del limite della larghezza di banda imposto.</span><span class="sxs-lookup"><span data-stu-id="7cb33-284">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="7cb33-285">Descrive la posizione del limite della larghezza di banda ("server criteri", "Attiva server", "modalità" e così via).</span><span class="sxs-lookup"><span data-stu-id="7cb33-285">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="7cb33-286">A cui viene fatto riferimento dalla <a href="lync-server-2013-appliedbandwidthsource-table.md">tabella AppliedBandwidthSource in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb33-286">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-287"><strong>Chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-287"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-288">po'</span><span class="sxs-lookup"><span data-stu-id="7cb33-288">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7cb33-289">Indica se le metriche del chiamante sono state ricevute; 1 è sì, un valore null è no.</span><span class="sxs-lookup"><span data-stu-id="7cb33-289">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-290"><strong>Destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-290"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-291">po'</span><span class="sxs-lookup"><span data-stu-id="7cb33-291">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7cb33-292">Indica se le metriche provenienti dal destinatario della chiamata sono state ricevute; 1 è sì, un valore null è no.</span><span class="sxs-lookup"><span data-stu-id="7cb33-292">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-293"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-293"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-294">po'</span><span class="sxs-lookup"><span data-stu-id="7cb33-294">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cb33-295">Indica se il report è per una parte della sessione o per la sessione completa.</span><span class="sxs-lookup"><span data-stu-id="7cb33-295">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="7cb33-296">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7cb33-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-297"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-297"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-298">po'</span><span class="sxs-lookup"><span data-stu-id="7cb33-298">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cb33-299">Indica se una chiamata è stata classificata come chiamata scadente (valore 1) o come buona chiamata (0).</span><span class="sxs-lookup"><span data-stu-id="7cb33-299">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="7cb33-300">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7cb33-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-301"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-301"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-302">tinyInt</span><span class="sxs-lookup"><span data-stu-id="7cb33-302">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cb33-303">Indica se il chiamante ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="7cb33-303">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="7cb33-304">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7cb33-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-305"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-305"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-306">tinyint</span><span class="sxs-lookup"><span data-stu-id="7cb33-306">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7cb33-307">Indica se il chiamante ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="7cb33-307">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="7cb33-308">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7cb33-308">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-309"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-309"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-310">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-310">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-311">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-311">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-312">Indirizzo IP riflessivo dell'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-312">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="7cb33-313">Nelle organizzazioni che utilizzano NAT (Network Address Translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.</span><span class="sxs-lookup"><span data-stu-id="7cb33-313">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="7cb33-314">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7cb33-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-315"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-315"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-316">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-316">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-317">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-317">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-318">Descrizione del dispositivo per il driver WiFi impiegato dall'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-318">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="7cb33-319">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7cb33-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-320"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-320"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-321">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-321">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-322">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-322">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-323">Numero di versione del driver WiFi impiegato dall'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-323">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="7cb33-324">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7cb33-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-325"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-325"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-326">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-326">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-327">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-327">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-328">Indirizzo IP riflessivo dell'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-328">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="7cb33-329">Nelle organizzazioni che utilizzano NAT (Network Address Translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.</span><span class="sxs-lookup"><span data-stu-id="7cb33-329">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="7cb33-330">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7cb33-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cb33-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-332">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-332">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-333">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-333">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-334">Descrizione del dispositivo per il driver WiFi impiegato dall'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-334">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="7cb33-335">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7cb33-335">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cb33-336"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="7cb33-336"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="7cb33-337">int</span><span class="sxs-lookup"><span data-stu-id="7cb33-337">int</span></span></p></td>
<td><p><span data-ttu-id="7cb33-338">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7cb33-338">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7cb33-339">Numero di versione del driver WiFi impiegato dall'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7cb33-339">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="7cb33-340">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7cb33-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

