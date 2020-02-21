---
title: 'Lync Server 2013: Visualizzazione MediaLine'
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
ms.openlocfilehash: 21fa89b5afe53937ee515dac45053dbd84ae12ef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="1ca48-102">Visualizzazione MediaLine in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ca48-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ca48-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="1ca48-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="1ca48-104">Nella visualizzazione MediaLine vengono archiviate informazioni su ogni linea multimediale nel database.</span><span class="sxs-lookup"><span data-stu-id="1ca48-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="1ca48-105">Una sessione audio in genere contiene una linea multimediale audio.</span><span class="sxs-lookup"><span data-stu-id="1ca48-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="1ca48-106">Una sessione audio e video (A/V) in genere contiene una linea multimediale audio e una video; la sessione, tuttavia, contiene due linee multimediali video se si utilizza un dispositivo per conferenze o la visualizzazione Raccolta.</span><span class="sxs-lookup"><span data-stu-id="1ca48-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="1ca48-107">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ca48-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ca48-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="1ca48-108">Column</span></span></th>
<th><span data-ttu-id="1ca48-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="1ca48-109">Data Type</span></span></th>
<th><span data-ttu-id="1ca48-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1ca48-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="1ca48-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="1ca48-112">datetime</span><span class="sxs-lookup"><span data-stu-id="1ca48-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="1ca48-113">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ca48-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="1ca48-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="1ca48-115">int</span><span class="sxs-lookup"><span data-stu-id="1ca48-115">int</span></span></p></td>
<td><p><span data-ttu-id="1ca48-116">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ca48-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="1ca48-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="1ca48-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="1ca48-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1ca48-119">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1ca48-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="1ca48-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="1ca48-121">int</span><span class="sxs-lookup"><span data-stu-id="1ca48-121">int</span></span></p></td>
<td><p><span data-ttu-id="1ca48-p102">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il chiamante. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.</span><span class="sxs-lookup"><span data-stu-id="1ca48-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="1ca48-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="1ca48-125">int</span><span class="sxs-lookup"><span data-stu-id="1ca48-125">int</span></span></p></td>
<td><p><span data-ttu-id="1ca48-p103">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il destinatario della chiamata. Per informazioni dettagliate, vedere la Specifica del protocollo Quality of Experience Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="1ca48-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-128">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1ca48-128">Security</span></span></p></td>
<td><p><span data-ttu-id="1ca48-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="1ca48-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1ca48-p104">Profilo di sicurezza in uso. 0 per NESSUNA, 1 per SRTP, 2 per V1.</span><span class="sxs-lookup"><span data-stu-id="1ca48-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-132">Trasporto</span><span class="sxs-lookup"><span data-stu-id="1ca48-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="1ca48-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="1ca48-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1ca48-p105">Tipo di trasporto. 0 per UDP, 1 per TCP.</span><span class="sxs-lookup"><span data-stu-id="1ca48-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="1ca48-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="1ca48-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="1ca48-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-p106">Indirizzo IP del chiamante. Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="1ca48-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="1ca48-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="1ca48-141">int</span><span class="sxs-lookup"><span data-stu-id="1ca48-141">int</span></span></p></td>
<td><p><span data-ttu-id="1ca48-142">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ca48-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="1ca48-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="1ca48-144">po'</span><span class="sxs-lookup"><span data-stu-id="1ca48-144">bit</span></span></p></td>
<td><p><span data-ttu-id="1ca48-p107">Indica se il chiamante si trova nella rete dell'organizzazione. 1 significa che il chiamante è all'interno della rete dell'organizzazione. 0 significa che il chiamante è all'esterno della rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1ca48-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="1ca48-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="1ca48-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ca48-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-150">Indirizzo MAC dell'interfaccia di rete utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ca48-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="1ca48-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="1ca48-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="1ca48-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-153">Indirizzo IP del servizio A/V Edge utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ca48-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="1ca48-154">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ca48-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="1ca48-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="1ca48-156">int</span><span class="sxs-lookup"><span data-stu-id="1ca48-156">int</span></span></p></td>
<td><p><span data-ttu-id="1ca48-157">Porta utilizzata nel servizio A/V Edge utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ca48-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="1ca48-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="1ca48-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="1ca48-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-160">Indirizzo IP del chiamante segnalato dal servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="1ca48-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="1ca48-161">Questo indirizzo può essere diverso rispetto al CallerIPAddr se il client si trova dietro un sistema NAT, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="1ca48-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="1ca48-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="1ca48-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ca48-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-164">Nome del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ca48-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="1ca48-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="1ca48-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ca48-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-167">Nome del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ca48-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="1ca48-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="1ca48-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ca48-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-170">Nome del driver del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ca48-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="1ca48-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="1ca48-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ca48-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-173">Nome del driver del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ca48-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="1ca48-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="1ca48-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="1ca48-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="1ca48-176">Descrizione del driver WiFi del chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ca48-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="1ca48-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="1ca48-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ca48-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-179">Versione del driver WiFi del chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ca48-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="1ca48-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="1ca48-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ca48-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-182">Dettagli della connessione di rete del chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ca48-182">Details of caller’s network connection.</span></span> <span data-ttu-id="1ca48-183">Per ulteriori informazioni, vedere la <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ca48-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="1ca48-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="1ca48-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ca48-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-186">BSSI (Basic Service Set Identifier) utilizzato dalla connessione WiFi del chiamante.</span><span class="sxs-lookup"><span data-stu-id="1ca48-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="1ca48-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="1ca48-188">po'</span><span class="sxs-lookup"><span data-stu-id="1ca48-188">bit</span></span></p></td>
<td><p><span data-ttu-id="1ca48-p111">Indica se il chiamante ha eseguito la connessione su una rete privata virtuale. 1 indica una VPN, 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="1ca48-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="1ca48-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="1ca48-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="1ca48-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-193">Indirizzo IP del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ca48-193">IP address of the callee.</span></span> <span data-ttu-id="1ca48-194">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="1ca48-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="1ca48-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="1ca48-196">int</span><span class="sxs-lookup"><span data-stu-id="1ca48-196">int</span></span></p></td>
<td><p><span data-ttu-id="1ca48-197">Porta utilizzata dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ca48-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="1ca48-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="1ca48-199">po'</span><span class="sxs-lookup"><span data-stu-id="1ca48-199">bit</span></span></p></td>
<td><p><span data-ttu-id="1ca48-p113">Indica se il destinatario della chiamata si trova all'interno della rete aziendale. 1 indica che il destinatario della chiamata è all'interno della rete aziendale, mentre 0 indica che è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="1ca48-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="1ca48-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="1ca48-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ca48-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-204">Indirizzo MAC dell'interfaccia di rete utilizzata dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ca48-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="1ca48-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="1ca48-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="1ca48-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-207">Indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ca48-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="1ca48-208">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ca48-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="1ca48-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="1ca48-210">int</span><span class="sxs-lookup"><span data-stu-id="1ca48-210">int</span></span></p></td>
<td><p><span data-ttu-id="1ca48-211">Porta utilizzata nel servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ca48-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="1ca48-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="1ca48-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="1ca48-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-214">Indirizzo IP del destinatario della chiamata segnalato dal servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="1ca48-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="1ca48-215">Questo indirizzo può essere diverso rispetto al CalleeIPAddr se il client si trova dietro un sistema NAT, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="1ca48-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="1ca48-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="1ca48-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="1ca48-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-218">Nome del dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ca48-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="1ca48-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="1ca48-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ca48-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-221">Nome del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ca48-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="1ca48-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="1ca48-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ca48-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-224">Nome del driver del dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ca48-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="1ca48-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="1ca48-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ca48-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-227">Nome del driver del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ca48-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="1ca48-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="1ca48-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ca48-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-230">Descrizione del driver WiFi del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ca48-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="1ca48-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="1ca48-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="1ca48-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="1ca48-233">Versione del driver WiFi del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ca48-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="1ca48-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="1ca48-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ca48-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-236">Dettagli della connessione di rete del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ca48-236">Details of callee’s network connection.</span></span> <span data-ttu-id="1ca48-237">Per ulteriori informazioni, vedere la <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ca48-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="1ca48-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="1ca48-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ca48-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-240">BSSI (Basic Service Set Identifier) utilizzato dalla connessione WiFi del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ca48-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="1ca48-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="1ca48-242">po'</span><span class="sxs-lookup"><span data-stu-id="1ca48-242">bit</span></span></p></td>
<td><p><span data-ttu-id="1ca48-p117">Indica se il destinatario della chiamata ha eseguito la connessione su una rete privata virtuale. 1 indica una VPN, 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="1ca48-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="1ca48-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="1ca48-246">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="1ca48-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-247">Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="1ca48-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="1ca48-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="1ca48-249">int</span><span class="sxs-lookup"><span data-stu-id="1ca48-249">int</span></span></p></td>
<td><p><span data-ttu-id="1ca48-p118">Questa è la larghezza di banda effettivamente applicata al flusso sul lato dell'invio secondo diverse impostazioni di criteri (TURN, API, SDP, server dei criteri e così via). Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="1ca48-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="1ca48-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="1ca48-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ca48-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ca48-p119">Origine del limite della larghezza di banda imposto. Descrive l'origine del limite della larghezza di banda, ad esempio "Policy Server", "TURN Server" o "Modality".</span><span class="sxs-lookup"><span data-stu-id="1ca48-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-257">Chiamante</span><span class="sxs-lookup"><span data-stu-id="1ca48-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="1ca48-258">po'</span><span class="sxs-lookup"><span data-stu-id="1ca48-258">bit</span></span></p></td>
<td><p><span data-ttu-id="1ca48-259">Indica se è stata ricevuta la metrica del chiamante. 1 indica sì e 0 indica no.</span><span class="sxs-lookup"><span data-stu-id="1ca48-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-260">Destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="1ca48-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="1ca48-261">po'</span><span class="sxs-lookup"><span data-stu-id="1ca48-261">bit</span></span></p></td>
<td><p><span data-ttu-id="1ca48-262">Indica se è stata ricevuta la metrica del destinatario della chiamata. 1 indica sì e 0 indica no.</span><span class="sxs-lookup"><span data-stu-id="1ca48-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="1ca48-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="1ca48-264">po'</span><span class="sxs-lookup"><span data-stu-id="1ca48-264">bit</span></span></p></td>
<td><p><span data-ttu-id="1ca48-265">Indica se il report riguarda una parte della chiamata o l'intera chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ca48-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="1ca48-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="1ca48-267">po'</span><span class="sxs-lookup"><span data-stu-id="1ca48-267">bit</span></span></p></td>
<td><p><span data-ttu-id="1ca48-268">Indica se una chiamata è stata classificata come di livello insufficiente (1) o buono (0).</span><span class="sxs-lookup"><span data-stu-id="1ca48-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca48-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="1ca48-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="1ca48-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="1ca48-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1ca48-271">Indica se il chiamante ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="1ca48-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca48-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="1ca48-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="1ca48-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="1ca48-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1ca48-274">Indica se il destinatario della chiamata ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="1ca48-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

