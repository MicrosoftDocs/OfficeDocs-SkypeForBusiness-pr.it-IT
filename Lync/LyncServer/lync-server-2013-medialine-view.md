---
title: 'Lync Server 2013: Visualizzazione MediaLine'
description: 'Lync Server 2013: Visualizzazione MediaLine.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c61fcc15b46958622e6cddd66427255a6def154
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568682"
---
# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="651de-103">Visualizzazione MediaLine in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="651de-103">MediaLine view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="651de-104">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="651de-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="651de-105">Nella visualizzazione MediaLine vengono archiviate informazioni su ogni linea multimediale nel database.</span><span class="sxs-lookup"><span data-stu-id="651de-105">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="651de-106">Una sessione audio in genere contiene una linea multimediale audio.</span><span class="sxs-lookup"><span data-stu-id="651de-106">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="651de-107">Una sessione audio e video (A/V) in genere contiene una linea multimediale audio e una video; la sessione, tuttavia, contiene due linee multimediali video se si utilizza un dispositivo per conferenze o la visualizzazione Raccolta.</span><span class="sxs-lookup"><span data-stu-id="651de-107">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="651de-108">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="651de-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="651de-109">Colonna</span><span class="sxs-lookup"><span data-stu-id="651de-109">Column</span></span></th>
<th><span data-ttu-id="651de-110">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="651de-110">Data Type</span></span></th>
<th><span data-ttu-id="651de-111">Dettagli</span><span class="sxs-lookup"><span data-stu-id="651de-111">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="651de-112">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="651de-112">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="651de-113">datetime</span><span class="sxs-lookup"><span data-stu-id="651de-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="651de-114">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="651de-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-115">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="651de-115">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="651de-116">int</span><span class="sxs-lookup"><span data-stu-id="651de-116">int</span></span></p></td>
<td><p><span data-ttu-id="651de-117">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="651de-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-118">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="651de-118">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="651de-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="651de-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="651de-120">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="651de-120">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-121">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="651de-121">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="651de-122">int</span><span class="sxs-lookup"><span data-stu-id="651de-122">int</span></span></p></td>
<td><p><span data-ttu-id="651de-p102">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il chiamante. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.</span><span class="sxs-lookup"><span data-stu-id="651de-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-125">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="651de-125">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="651de-126">int</span><span class="sxs-lookup"><span data-stu-id="651de-126">int</span></span></p></td>
<td><p><span data-ttu-id="651de-p103">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il destinatario della chiamata. Per informazioni dettagliate, vedere la Specifica del protocollo Quality of Experience Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="651de-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-129">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="651de-129">Security</span></span></p></td>
<td><p><span data-ttu-id="651de-130">tinyint</span><span class="sxs-lookup"><span data-stu-id="651de-130">tinyint</span></span></p></td>
<td><p><span data-ttu-id="651de-p104">Profilo di sicurezza in uso. 0 per NESSUNA, 1 per SRTP, 2 per V1.</span><span class="sxs-lookup"><span data-stu-id="651de-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-133">Trasporto</span><span class="sxs-lookup"><span data-stu-id="651de-133">Transport</span></span></p></td>
<td><p><span data-ttu-id="651de-134">tinyint</span><span class="sxs-lookup"><span data-stu-id="651de-134">tinyint</span></span></p></td>
<td><p><span data-ttu-id="651de-p105">Tipo di trasporto. 0 per UDP, 1 per TCP.</span><span class="sxs-lookup"><span data-stu-id="651de-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-137">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="651de-137">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="651de-138">var (50)</span><span class="sxs-lookup"><span data-stu-id="651de-138">var(50)</span></span></p></td>
<td><p><span data-ttu-id="651de-p106">Indirizzo IP del chiamante. Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="651de-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-141">CallerPort</span><span class="sxs-lookup"><span data-stu-id="651de-141">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="651de-142">int</span><span class="sxs-lookup"><span data-stu-id="651de-142">int</span></span></p></td>
<td><p><span data-ttu-id="651de-143">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="651de-143">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-144">CallerInside</span><span class="sxs-lookup"><span data-stu-id="651de-144">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="651de-145">po'</span><span class="sxs-lookup"><span data-stu-id="651de-145">bit</span></span></p></td>
<td><p><span data-ttu-id="651de-p107">Indica se il chiamante si trova nella rete dell'organizzazione. 1 significa che il chiamante è all'interno della rete dell'organizzazione. 0 significa che il chiamante è all'esterno della rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="651de-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-149">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="651de-149">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="651de-150">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="651de-150">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="651de-151">Indirizzo MAC dell'interfaccia di rete utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="651de-151">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-152">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="651de-152">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="651de-153">var (50)</span><span class="sxs-lookup"><span data-stu-id="651de-153">var(50)</span></span></p></td>
<td><p><span data-ttu-id="651de-154">Indirizzo IP del servizio A/V Edge utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="651de-154">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="651de-155">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="651de-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-156">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="651de-156">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="651de-157">int</span><span class="sxs-lookup"><span data-stu-id="651de-157">int</span></span></p></td>
<td><p><span data-ttu-id="651de-158">Porta utilizzata nel servizio A/V Edge utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="651de-158">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-159">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="651de-159">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="651de-160">var (50)</span><span class="sxs-lookup"><span data-stu-id="651de-160">var(50)</span></span></p></td>
<td><p><span data-ttu-id="651de-161">Indirizzo IP del chiamante segnalato dal servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="651de-161">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="651de-162">Questo indirizzo può essere diverso rispetto al CallerIPAddr se il client si trova dietro un sistema NAT, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="651de-162">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-163">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="651de-163">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="651de-164">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="651de-164">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="651de-165">Nome del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="651de-165">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-166">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="651de-166">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="651de-167">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="651de-167">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="651de-168">Nome del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="651de-168">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-169">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="651de-169">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="651de-170">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="651de-170">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="651de-171">Nome del driver del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="651de-171">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-172">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="651de-172">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="651de-173">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="651de-173">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="651de-174">Nome del driver del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="651de-174">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-175">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="651de-175">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="651de-176">varchar (256</span><span class="sxs-lookup"><span data-stu-id="651de-176">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="651de-177">Descrizione del driver WiFi del chiamante.</span><span class="sxs-lookup"><span data-stu-id="651de-177">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-178">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="651de-178">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="651de-179">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="651de-179">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="651de-180">Versione del driver WiFi del chiamante.</span><span class="sxs-lookup"><span data-stu-id="651de-180">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-181">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="651de-181">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="651de-182">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="651de-182">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="651de-183">Dettagli della connessione di rete del chiamante.</span><span class="sxs-lookup"><span data-stu-id="651de-183">Details of caller’s network connection.</span></span> <span data-ttu-id="651de-184">Per ulteriori informazioni, vedere la <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="651de-184">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-185">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="651de-185">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="651de-186">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="651de-186">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="651de-187">BSSI (Basic Service Set Identifier) utilizzato dalla connessione WiFi del chiamante.</span><span class="sxs-lookup"><span data-stu-id="651de-187">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-188">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="651de-188">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="651de-189">po'</span><span class="sxs-lookup"><span data-stu-id="651de-189">bit</span></span></p></td>
<td><p><span data-ttu-id="651de-p111">Indica se il chiamante ha eseguito la connessione su una rete privata virtuale. 1 indica una VPN, 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="651de-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-192">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="651de-192">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="651de-193">var (50)</span><span class="sxs-lookup"><span data-stu-id="651de-193">var(50)</span></span></p></td>
<td><p><span data-ttu-id="651de-194">Indirizzo IP del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="651de-194">IP address of the callee.</span></span> <span data-ttu-id="651de-195">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="651de-195">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-196">CalleePort</span><span class="sxs-lookup"><span data-stu-id="651de-196">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="651de-197">int</span><span class="sxs-lookup"><span data-stu-id="651de-197">int</span></span></p></td>
<td><p><span data-ttu-id="651de-198">Porta utilizzata dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="651de-198">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-199">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="651de-199">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="651de-200">po'</span><span class="sxs-lookup"><span data-stu-id="651de-200">bit</span></span></p></td>
<td><p><span data-ttu-id="651de-p113">Indica se il destinatario della chiamata si trova all'interno della rete aziendale. 1 indica che il destinatario della chiamata è all'interno della rete aziendale, mentre 0 indica che è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="651de-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-203">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="651de-203">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="651de-204">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="651de-204">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="651de-205">Indirizzo MAC dell'interfaccia di rete utilizzata dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="651de-205">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-206">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="651de-206">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="651de-207">var (50)</span><span class="sxs-lookup"><span data-stu-id="651de-207">var(50)</span></span></p></td>
<td><p><span data-ttu-id="651de-208">Indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="651de-208">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="651de-209">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="651de-209">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-210">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="651de-210">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="651de-211">int</span><span class="sxs-lookup"><span data-stu-id="651de-211">int</span></span></p></td>
<td><p><span data-ttu-id="651de-212">Porta utilizzata nel servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="651de-212">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-213">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="651de-213">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="651de-214">var (50)</span><span class="sxs-lookup"><span data-stu-id="651de-214">var(50)</span></span></p></td>
<td><p><span data-ttu-id="651de-215">Indirizzo IP del destinatario della chiamata segnalato dal servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="651de-215">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="651de-216">Questo indirizzo può essere diverso rispetto al CalleeIPAddr se il client si trova dietro un sistema NAT, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="651de-216">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-217">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="651de-217">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="651de-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="651de-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="651de-219">Nome del dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="651de-219">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-220">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="651de-220">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="651de-221">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="651de-221">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="651de-222">Nome del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="651de-222">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-223">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="651de-223">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="651de-224">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="651de-224">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="651de-225">Nome del driver del dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="651de-225">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-226">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="651de-226">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="651de-227">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="651de-227">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="651de-228">Nome del driver del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="651de-228">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-229">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="651de-229">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="651de-230">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="651de-230">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="651de-231">Descrizione del driver WiFi del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="651de-231">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-232">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="651de-232">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="651de-233">varchar (256</span><span class="sxs-lookup"><span data-stu-id="651de-233">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="651de-234">Versione del driver WiFi del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="651de-234">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-235">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="651de-235">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="651de-236">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="651de-236">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="651de-237">Dettagli della connessione di rete del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="651de-237">Details of callee’s network connection.</span></span> <span data-ttu-id="651de-238">Per ulteriori informazioni, vedere la <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="651de-238">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-239">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="651de-239">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="651de-240">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="651de-240">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="651de-241">BSSI (Basic Service Set Identifier) utilizzato dalla connessione WiFi del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="651de-241">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-242">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="651de-242">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="651de-243">po'</span><span class="sxs-lookup"><span data-stu-id="651de-243">bit</span></span></p></td>
<td><p><span data-ttu-id="651de-p117">Indica se il destinatario della chiamata ha eseguito la connessione su una rete privata virtuale. 1 indica una VPN, 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="651de-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-246">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="651de-246">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="651de-247">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="651de-247">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="651de-248">Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="651de-248">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-249">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="651de-249">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="651de-250">int</span><span class="sxs-lookup"><span data-stu-id="651de-250">int</span></span></p></td>
<td><p><span data-ttu-id="651de-p118">Questa è la larghezza di banda effettivamente applicata al flusso sul lato dell'invio secondo diverse impostazioni di criteri (TURN, API, SDP, server dei criteri e così via). Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="651de-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-254">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="651de-254">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="651de-255">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="651de-255">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="651de-p119">Origine del limite della larghezza di banda imposto. Descrive l'origine del limite della larghezza di banda, ad esempio "Policy Server", "TURN Server" o "Modality".</span><span class="sxs-lookup"><span data-stu-id="651de-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-258">Chiamante</span><span class="sxs-lookup"><span data-stu-id="651de-258">Caller</span></span></p></td>
<td><p><span data-ttu-id="651de-259">po'</span><span class="sxs-lookup"><span data-stu-id="651de-259">bit</span></span></p></td>
<td><p><span data-ttu-id="651de-260">Indica se è stata ricevuta la metrica del chiamante. 1 indica sì e 0 indica no.</span><span class="sxs-lookup"><span data-stu-id="651de-260">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-261">Destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="651de-261">Callee</span></span></p></td>
<td><p><span data-ttu-id="651de-262">po'</span><span class="sxs-lookup"><span data-stu-id="651de-262">bit</span></span></p></td>
<td><p><span data-ttu-id="651de-263">Indica se è stata ricevuta la metrica del destinatario della chiamata. 1 indica sì e 0 indica no.</span><span class="sxs-lookup"><span data-stu-id="651de-263">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-264">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="651de-264">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="651de-265">po'</span><span class="sxs-lookup"><span data-stu-id="651de-265">bit</span></span></p></td>
<td><p><span data-ttu-id="651de-266">Indica se il report riguarda una parte della chiamata o l'intera chiamata.</span><span class="sxs-lookup"><span data-stu-id="651de-266">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-267">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="651de-267">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="651de-268">po'</span><span class="sxs-lookup"><span data-stu-id="651de-268">bit</span></span></p></td>
<td><p><span data-ttu-id="651de-269">Indica se una chiamata è stata classificata come di livello insufficiente (1) o buono (0).</span><span class="sxs-lookup"><span data-stu-id="651de-269">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="651de-270">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="651de-270">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="651de-271">tinyint</span><span class="sxs-lookup"><span data-stu-id="651de-271">tinyint</span></span></p></td>
<td><p><span data-ttu-id="651de-272">Indica se il chiamante ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="651de-272">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="651de-273">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="651de-273">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="651de-274">tinyint</span><span class="sxs-lookup"><span data-stu-id="651de-274">tinyint</span></span></p></td>
<td><p><span data-ttu-id="651de-275">Indica se il destinatario della chiamata ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="651de-275">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

