---
title: 'Lync Server 2013: Visualizzazione MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d930f3beeeddb5c5582f41c44f1c68ff7f21f18d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="3230a-102">Visualizzazione MediaLine in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3230a-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3230a-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="3230a-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="3230a-104">La Visualizzazione MediaLine archivia le informazioni su ogni riga multimediale nel database.</span><span class="sxs-lookup"><span data-stu-id="3230a-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="3230a-105">Una sessione audio in genere contiene una linea media audio.</span><span class="sxs-lookup"><span data-stu-id="3230a-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="3230a-106">Una sessione audio e video (A/V) in genere contiene una linea media audio e una linea media video; Tuttavia, la sessione può contenere due linee multimediali video se viene usato un dispositivo per i servizi di conferenza o se viene usata la visualizzazione raccolta.</span><span class="sxs-lookup"><span data-stu-id="3230a-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="3230a-107">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3230a-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3230a-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="3230a-108">Column</span></span></th>
<th><span data-ttu-id="3230a-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="3230a-109">Data Type</span></span></th>
<th><span data-ttu-id="3230a-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3230a-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3230a-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="3230a-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="3230a-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="3230a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="3230a-113">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3230a-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="3230a-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="3230a-115">int</span><span class="sxs-lookup"><span data-stu-id="3230a-115">int</span></span></p></td>
<td><p><span data-ttu-id="3230a-116">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3230a-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="3230a-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="3230a-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="3230a-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3230a-119">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3230a-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="3230a-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="3230a-121">int</span><span class="sxs-lookup"><span data-stu-id="3230a-121">int</span></span></p></td>
<td><p><span data-ttu-id="3230a-122">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamante.</span><span class="sxs-lookup"><span data-stu-id="3230a-122">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="3230a-123">Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.</span><span class="sxs-lookup"><span data-stu-id="3230a-123">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="3230a-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="3230a-125">int</span><span class="sxs-lookup"><span data-stu-id="3230a-125">int</span></span></p></td>
<td><p><span data-ttu-id="3230a-126">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamato.</span><span class="sxs-lookup"><span data-stu-id="3230a-126">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="3230a-127">Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.</span><span class="sxs-lookup"><span data-stu-id="3230a-127">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-128">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3230a-128">Security</span></span></p></td>
<td><p><span data-ttu-id="3230a-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="3230a-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3230a-130">Profilo di sicurezza in uso.</span><span class="sxs-lookup"><span data-stu-id="3230a-130">Security profile in use.</span></span> <span data-ttu-id="3230a-131">0 è NONE, 1 è SRTP, 2 è V1.</span><span class="sxs-lookup"><span data-stu-id="3230a-131">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-132">Transport</span><span class="sxs-lookup"><span data-stu-id="3230a-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="3230a-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="3230a-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3230a-134">Tipo di trasporto.</span><span class="sxs-lookup"><span data-stu-id="3230a-134">Transport type.</span></span> <span data-ttu-id="3230a-135">0 è UDP, 1 è TCP.</span><span class="sxs-lookup"><span data-stu-id="3230a-135">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="3230a-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3230a-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="3230a-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3230a-138">Indirizzo IP del chiamante.</span><span class="sxs-lookup"><span data-stu-id="3230a-138">IP address of the caller.</span></span> <span data-ttu-id="3230a-139">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="3230a-139">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="3230a-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="3230a-141">int</span><span class="sxs-lookup"><span data-stu-id="3230a-141">int</span></span></p></td>
<td><p><span data-ttu-id="3230a-142">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="3230a-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="3230a-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="3230a-144">po'</span><span class="sxs-lookup"><span data-stu-id="3230a-144">bit</span></span></p></td>
<td><p><span data-ttu-id="3230a-145">Indica se il chiamante si trova all'interno della rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3230a-145">Indicates whether or not the caller is inside the organization network.</span></span> <span data-ttu-id="3230a-146">1 indica che il chiamante si trova all'interno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="3230a-146">1 means that the caller is inside the enterprise network.</span></span> <span data-ttu-id="3230a-147">0 indica che il chiamante si trova all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="3230a-147">0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="3230a-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="3230a-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3230a-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3230a-150">Indirizzo MAC dell'interfaccia di rete usata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="3230a-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="3230a-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3230a-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="3230a-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3230a-153">Indirizzo IP del servizio A/V Edge usato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="3230a-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="3230a-154">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3230a-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="3230a-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="3230a-156">int</span><span class="sxs-lookup"><span data-stu-id="3230a-156">int</span></span></p></td>
<td><p><span data-ttu-id="3230a-157">Porta usata nel servizio A/V Edge usato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="3230a-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="3230a-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3230a-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="3230a-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3230a-160">Indirizzo IP del chiamante segnalato dal servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="3230a-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="3230a-161">Questo indirizzo può essere diverso da quello di CallerIPAddr se il client si trova dietro a un NAT, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="3230a-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="3230a-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="3230a-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3230a-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3230a-164">Nome del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="3230a-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="3230a-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="3230a-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3230a-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3230a-167">Nome del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="3230a-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="3230a-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="3230a-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3230a-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3230a-170">Nome del driver del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="3230a-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="3230a-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="3230a-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3230a-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3230a-173">Nome del driver del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="3230a-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="3230a-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="3230a-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="3230a-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="3230a-176">Descrizione del driver WiFi del chiamante.</span><span class="sxs-lookup"><span data-stu-id="3230a-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="3230a-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="3230a-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3230a-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3230a-179">Versione del driver WiFi del chiamante.</span><span class="sxs-lookup"><span data-stu-id="3230a-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="3230a-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="3230a-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3230a-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3230a-182">Dettagli della connessione di rete del chiamante.</span><span class="sxs-lookup"><span data-stu-id="3230a-182">Details of caller’s network connection.</span></span> <span data-ttu-id="3230a-183">Per altre informazioni, vedere la <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3230a-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="3230a-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="3230a-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3230a-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3230a-186">ID set di servizi di base usato dalla connessione WiFi dei chiamanti.</span><span class="sxs-lookup"><span data-stu-id="3230a-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="3230a-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="3230a-188">po'</span><span class="sxs-lookup"><span data-stu-id="3230a-188">bit</span></span></p></td>
<td><p><span data-ttu-id="3230a-189">Indica se il chiamante è connesso tramite una rete privata virtuale.</span><span class="sxs-lookup"><span data-stu-id="3230a-189">Indicates whether the caller connected over a virtual private network.</span></span> <span data-ttu-id="3230a-190">1 è una rete privata virtuale (VPN), 0 non è VPN.</span><span class="sxs-lookup"><span data-stu-id="3230a-190">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="3230a-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3230a-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="3230a-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3230a-193">Indirizzo IP del destinatario.</span><span class="sxs-lookup"><span data-stu-id="3230a-193">IP address of the callee.</span></span> <span data-ttu-id="3230a-194">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="3230a-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="3230a-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="3230a-196">int</span><span class="sxs-lookup"><span data-stu-id="3230a-196">int</span></span></p></td>
<td><p><span data-ttu-id="3230a-197">Porta utilizzata dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="3230a-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="3230a-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="3230a-199">po'</span><span class="sxs-lookup"><span data-stu-id="3230a-199">bit</span></span></p></td>
<td><p><span data-ttu-id="3230a-200">Indica se il chiamato si trova all'interno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="3230a-200">Indicates whether the callee is inside the enterprise network.</span></span> <span data-ttu-id="3230a-201">1 significa che il chiamato si trova all'interno della rete aziendale, 0 indica che il chiamato è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="3230a-201">1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="3230a-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="3230a-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3230a-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3230a-204">Indirizzo MAC dell'interfaccia di rete usata dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="3230a-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="3230a-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3230a-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="3230a-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3230a-207">Indirizzo IP del servizio A/V Edge usato dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="3230a-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="3230a-208">Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3230a-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="3230a-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="3230a-210">int</span><span class="sxs-lookup"><span data-stu-id="3230a-210">int</span></span></p></td>
<td><p><span data-ttu-id="3230a-211">Porta usata nel servizio A/V Edge usato dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="3230a-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="3230a-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3230a-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="3230a-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3230a-214">Indirizzo IP del destinatario segnalato dal servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="3230a-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="3230a-215">Questo indirizzo può essere diverso da quello di CalleeIPAddr se il client si trova dietro a un NAT, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="3230a-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="3230a-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="3230a-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="3230a-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3230a-218">Nome del dispositivo di acquisizione del chiamato.</span><span class="sxs-lookup"><span data-stu-id="3230a-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="3230a-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="3230a-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3230a-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3230a-221">Nome del dispositivo di rendering del destinatario.</span><span class="sxs-lookup"><span data-stu-id="3230a-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="3230a-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="3230a-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3230a-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3230a-224">Nome del driver del dispositivo di acquisizione del destinatario.</span><span class="sxs-lookup"><span data-stu-id="3230a-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="3230a-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="3230a-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3230a-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3230a-227">Nome del driver del dispositivo di rendering del destinatario.</span><span class="sxs-lookup"><span data-stu-id="3230a-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="3230a-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="3230a-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3230a-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3230a-230">Descrizione del driver WiFi del chiamato.</span><span class="sxs-lookup"><span data-stu-id="3230a-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="3230a-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="3230a-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="3230a-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="3230a-233">Versione del driver WiFi del chiamato.</span><span class="sxs-lookup"><span data-stu-id="3230a-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="3230a-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="3230a-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3230a-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3230a-236">Dettagli della connessione di rete del chiamato.</span><span class="sxs-lookup"><span data-stu-id="3230a-236">Details of callee’s network connection.</span></span> <span data-ttu-id="3230a-237">Per altre informazioni, vedere la <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3230a-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="3230a-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="3230a-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3230a-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3230a-240">Identificatore del set di servizi di base usato dalla connessione Wi-Fi del chiamato.</span><span class="sxs-lookup"><span data-stu-id="3230a-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="3230a-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="3230a-242">po'</span><span class="sxs-lookup"><span data-stu-id="3230a-242">bit</span></span></p></td>
<td><p><span data-ttu-id="3230a-243">Indica se il chiamato è connesso tramite una rete privata virtuale.</span><span class="sxs-lookup"><span data-stu-id="3230a-243">Indicates whether the callee connected over a virtual private network.</span></span> <span data-ttu-id="3230a-244">1 è una rete privata virtuale (VPN), 0 non è VPN.</span><span class="sxs-lookup"><span data-stu-id="3230a-244">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="3230a-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="3230a-246">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="3230a-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="3230a-247">Stretta MOS colloquiale delle sessioni audio (in base a entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="3230a-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="3230a-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="3230a-249">int</span><span class="sxs-lookup"><span data-stu-id="3230a-249">int</span></span></p></td>
<td><p><span data-ttu-id="3230a-250">Questa è la larghezza di banda effettiva applicata al flusso del lato di invio assegnato in base a varie impostazioni dei criteri (TURN, API, SDP, Policy Server e così via).</span><span class="sxs-lookup"><span data-stu-id="3230a-250">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.).</span></span> <span data-ttu-id="3230a-251">Questa operazione non deve essere confusa con la larghezza di banda effettiva, in quanto la larghezza di banda effettiva può essere inferiore in base alla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="3230a-251">This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="3230a-252">Si tratta in pratica della larghezza di banda massima che il flusso di invio può bloccare i limiti imposti dalla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="3230a-252">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="3230a-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="3230a-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3230a-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3230a-255">Origine del limite di larghezza di banda imposto.</span><span class="sxs-lookup"><span data-stu-id="3230a-255">Source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="3230a-256">Descrive la posizione in cui proviene il limite di larghezza di banda, ad esempio "Policy Server", "TURN server" o "modality".</span><span class="sxs-lookup"><span data-stu-id="3230a-256">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-257">Chiamante</span><span class="sxs-lookup"><span data-stu-id="3230a-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="3230a-258">po'</span><span class="sxs-lookup"><span data-stu-id="3230a-258">bit</span></span></p></td>
<td><p><span data-ttu-id="3230a-259">Indica se sono state ricevute metriche dal chiamante; 1 è sì, 0 è no.</span><span class="sxs-lookup"><span data-stu-id="3230a-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-260">Chiamato</span><span class="sxs-lookup"><span data-stu-id="3230a-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="3230a-261">po'</span><span class="sxs-lookup"><span data-stu-id="3230a-261">bit</span></span></p></td>
<td><p><span data-ttu-id="3230a-262">Indica se le metriche del destinatario della chiamata sono state ricevute; 1 è sì, 0 è no.</span><span class="sxs-lookup"><span data-stu-id="3230a-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="3230a-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="3230a-264">po'</span><span class="sxs-lookup"><span data-stu-id="3230a-264">bit</span></span></p></td>
<td><p><span data-ttu-id="3230a-265">Indica se il report è per una parte della chiamata o per la chiamata completa.</span><span class="sxs-lookup"><span data-stu-id="3230a-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="3230a-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="3230a-267">po'</span><span class="sxs-lookup"><span data-stu-id="3230a-267">bit</span></span></p></td>
<td><p><span data-ttu-id="3230a-268">Indica se una chiamata è stata classificata come chiamata scadente (1) o come buona chiamata (0).</span><span class="sxs-lookup"><span data-stu-id="3230a-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3230a-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="3230a-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="3230a-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="3230a-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3230a-271">Indica se il chiamante è connesso alla rete usando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="3230a-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3230a-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="3230a-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="3230a-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="3230a-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3230a-274">Indica se l'utente ha chiamato connesso alla rete usando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="3230a-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

