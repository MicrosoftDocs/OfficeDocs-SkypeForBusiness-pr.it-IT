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
ms.openlocfilehash: 5c6e5fd3c1afe27bc1baa8790527ee239bdba990
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="9f734-102">Visualizzazione MediaLine in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f734-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f734-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9f734-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9f734-104">Nella visualizzazione MediaLine vengono archiviate informazioni su ogni linea multimediale nel database.</span><span class="sxs-lookup"><span data-stu-id="9f734-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="9f734-105">Una sessione audio in genere contiene una linea multimediale audio.</span><span class="sxs-lookup"><span data-stu-id="9f734-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="9f734-106">Una sessione audio e video (A/V) in genere contiene una linea multimediale audio e una video; la sessione, tuttavia, contiene due linee multimediali video se si utilizza un dispositivo per conferenze o la visualizzazione Raccolta.</span><span class="sxs-lookup"><span data-stu-id="9f734-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="9f734-107">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9f734-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f734-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="9f734-108">Column</span></span></th>
<th><span data-ttu-id="9f734-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9f734-109">Data Type</span></span></th>
<th><span data-ttu-id="9f734-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9f734-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f734-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="9f734-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="9f734-112">datetime</span><span class="sxs-lookup"><span data-stu-id="9f734-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="9f734-113">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9f734-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="9f734-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="9f734-115">int</span><span class="sxs-lookup"><span data-stu-id="9f734-115">int</span></span></p></td>
<td><p><span data-ttu-id="9f734-116">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9f734-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="9f734-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="9f734-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="9f734-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9f734-119">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9f734-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="9f734-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="9f734-121">int</span><span class="sxs-lookup"><span data-stu-id="9f734-121">int</span></span></p></td>
<td><p><span data-ttu-id="9f734-p102">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il chiamante. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.</span><span class="sxs-lookup"><span data-stu-id="9f734-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="9f734-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="9f734-125">int</span><span class="sxs-lookup"><span data-stu-id="9f734-125">int</span></span></p></td>
<td><p><span data-ttu-id="9f734-p103">Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il destinatario della chiamata. Per informazioni dettagliate, vedere la Specifica del protocollo Quality of Experience Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="9f734-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-128">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="9f734-128">Security</span></span></p></td>
<td><p><span data-ttu-id="9f734-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="9f734-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9f734-p104">Profilo di sicurezza in uso. 0 per NESSUNA, 1 per SRTP, 2 per V1.</span><span class="sxs-lookup"><span data-stu-id="9f734-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-132">Trasporto</span><span class="sxs-lookup"><span data-stu-id="9f734-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="9f734-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="9f734-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9f734-p105">Tipo di trasporto. 0 per UDP, 1 per TCP.</span><span class="sxs-lookup"><span data-stu-id="9f734-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="9f734-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="9f734-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="9f734-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="9f734-p106">Indirizzo IP del chiamante. Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="9f734-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="9f734-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="9f734-141">int</span><span class="sxs-lookup"><span data-stu-id="9f734-141">int</span></span></p></td>
<td><p><span data-ttu-id="9f734-142">Porta utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="9f734-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="9f734-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="9f734-144">po'</span><span class="sxs-lookup"><span data-stu-id="9f734-144">bit</span></span></p></td>
<td><p><span data-ttu-id="9f734-p107">Indica se il chiamante si trova nella rete dell'organizzazione. 1 significa che il chiamante è all'interno della rete dell'organizzazione. 0 significa che il chiamante è all'esterno della rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9f734-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="9f734-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="9f734-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f734-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f734-150">Indirizzo MAC dell'interfaccia di rete utilizzata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="9f734-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="9f734-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="9f734-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="9f734-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="9f734-153">Indirizzo IP del servizio A/V Edge utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="9f734-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="9f734-154">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9f734-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="9f734-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="9f734-156">int</span><span class="sxs-lookup"><span data-stu-id="9f734-156">int</span></span></p></td>
<td><p><span data-ttu-id="9f734-157">Porta utilizzata nel servizio A/V Edge utilizzato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="9f734-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="9f734-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="9f734-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="9f734-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="9f734-160">Indirizzo IP del chiamante segnalato dal servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="9f734-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="9f734-161">Questo indirizzo può essere diverso rispetto al CallerIPAddr se il client si trova dietro un sistema NAT, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="9f734-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="9f734-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="9f734-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f734-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f734-164">Nome del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9f734-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="9f734-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="9f734-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f734-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f734-167">Nome del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9f734-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="9f734-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="9f734-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f734-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f734-170">Nome del driver del dispositivo di acquisizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9f734-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="9f734-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="9f734-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f734-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f734-173">Nome del driver del dispositivo di rendering del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9f734-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="9f734-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="9f734-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="9f734-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="9f734-176">Descrizione del driver WiFi del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9f734-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="9f734-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="9f734-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f734-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f734-179">Versione del driver WiFi del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9f734-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="9f734-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="9f734-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f734-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f734-182">Dettagli della connessione di rete del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9f734-182">Details of caller’s network connection.</span></span> <span data-ttu-id="9f734-183">Per ulteriori informazioni, vedere la <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9f734-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="9f734-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="9f734-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f734-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f734-186">BSSI (Basic Service Set Identifier) utilizzato dalla connessione WiFi del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9f734-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="9f734-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="9f734-188">po'</span><span class="sxs-lookup"><span data-stu-id="9f734-188">bit</span></span></p></td>
<td><p><span data-ttu-id="9f734-p111">Indica se il chiamante ha eseguito la connessione su una rete privata virtuale. 1 indica una VPN, 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="9f734-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="9f734-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="9f734-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="9f734-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="9f734-193">Indirizzo IP del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f734-193">IP address of the callee.</span></span> <span data-ttu-id="9f734-194">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="9f734-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="9f734-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="9f734-196">int</span><span class="sxs-lookup"><span data-stu-id="9f734-196">int</span></span></p></td>
<td><p><span data-ttu-id="9f734-197">Porta utilizzata dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f734-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="9f734-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="9f734-199">po'</span><span class="sxs-lookup"><span data-stu-id="9f734-199">bit</span></span></p></td>
<td><p><span data-ttu-id="9f734-p113">Indica se il destinatario della chiamata si trova all'interno della rete aziendale. 1 indica che il destinatario della chiamata è all'interno della rete aziendale, mentre 0 indica che è all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="9f734-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="9f734-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="9f734-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f734-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f734-204">Indirizzo MAC dell'interfaccia di rete utilizzata dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f734-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="9f734-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="9f734-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="9f734-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="9f734-207">Indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f734-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="9f734-208">Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9f734-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="9f734-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="9f734-210">int</span><span class="sxs-lookup"><span data-stu-id="9f734-210">int</span></span></p></td>
<td><p><span data-ttu-id="9f734-211">Porta utilizzata nel servizio A/V Edge utilizzato dal destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f734-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="9f734-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="9f734-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="9f734-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="9f734-214">Indirizzo IP del destinatario della chiamata segnalato dal servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="9f734-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="9f734-215">Questo indirizzo può essere diverso rispetto al CalleeIPAddr se il client si trova dietro un sistema NAT, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="9f734-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="9f734-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="9f734-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="9f734-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="9f734-218">Nome del dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f734-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="9f734-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="9f734-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f734-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f734-221">Nome del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f734-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="9f734-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="9f734-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f734-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f734-224">Nome del driver del dispositivo di acquisizione del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f734-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="9f734-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="9f734-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f734-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f734-227">Nome del driver del dispositivo di rendering del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f734-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="9f734-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="9f734-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f734-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f734-230">Descrizione del driver WiFi del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f734-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="9f734-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="9f734-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="9f734-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="9f734-233">Versione del driver WiFi del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f734-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="9f734-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="9f734-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f734-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f734-236">Dettagli della connessione di rete del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f734-236">Details of callee’s network connection.</span></span> <span data-ttu-id="9f734-237">Per ulteriori informazioni, vedere la <a href="lync-server-2013-networkconnectiondetail-table.md">tabella NetworkConnectionDetail in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9f734-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="9f734-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="9f734-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f734-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f734-240">BSSI (Basic Service Set Identifier) utilizzato dalla connessione WiFi del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f734-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="9f734-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="9f734-242">po'</span><span class="sxs-lookup"><span data-stu-id="9f734-242">bit</span></span></p></td>
<td><p><span data-ttu-id="9f734-p117">Indica se il destinatario della chiamata ha eseguito la connessione su una rete privata virtuale. 1 indica una VPN, 0 indica una rete non VPN.</span><span class="sxs-lookup"><span data-stu-id="9f734-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="9f734-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="9f734-246">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="9f734-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="9f734-247">Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).</span><span class="sxs-lookup"><span data-stu-id="9f734-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="9f734-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="9f734-249">int</span><span class="sxs-lookup"><span data-stu-id="9f734-249">int</span></span></p></td>
<td><p><span data-ttu-id="9f734-p118">Questa è la larghezza di banda effettivamente applicata al flusso sul lato dell'invio secondo diverse impostazioni di criteri (TURN, API, SDP, server dei criteri e così via). Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="9f734-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="9f734-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="9f734-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9f734-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f734-p119">Origine del limite della larghezza di banda imposto. Descrive l'origine del limite della larghezza di banda, ad esempio "Policy Server", "TURN Server" o "Modality".</span><span class="sxs-lookup"><span data-stu-id="9f734-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-257">Chiamante</span><span class="sxs-lookup"><span data-stu-id="9f734-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="9f734-258">po'</span><span class="sxs-lookup"><span data-stu-id="9f734-258">bit</span></span></p></td>
<td><p><span data-ttu-id="9f734-259">Indica se è stata ricevuta la metrica del chiamante. 1 indica sì e 0 indica no.</span><span class="sxs-lookup"><span data-stu-id="9f734-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-260">Destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="9f734-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="9f734-261">po'</span><span class="sxs-lookup"><span data-stu-id="9f734-261">bit</span></span></p></td>
<td><p><span data-ttu-id="9f734-262">Indica se è stata ricevuta la metrica del destinatario della chiamata. 1 indica sì e 0 indica no.</span><span class="sxs-lookup"><span data-stu-id="9f734-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="9f734-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="9f734-264">po'</span><span class="sxs-lookup"><span data-stu-id="9f734-264">bit</span></span></p></td>
<td><p><span data-ttu-id="9f734-265">Indica se il report riguarda una parte della chiamata o l'intera chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f734-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="9f734-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="9f734-267">po'</span><span class="sxs-lookup"><span data-stu-id="9f734-267">bit</span></span></p></td>
<td><p><span data-ttu-id="9f734-268">Indica se una chiamata è stata classificata come di livello insufficiente (1) o buono (0).</span><span class="sxs-lookup"><span data-stu-id="9f734-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f734-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="9f734-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="9f734-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="9f734-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9f734-271">Indica se il chiamante ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="9f734-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f734-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="9f734-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="9f734-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="9f734-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9f734-274">Indica se il destinatario della chiamata ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="9f734-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

