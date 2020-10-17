---
title: 'Lync Server 2013: Tabella UserAgentDef (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgentDef table (QoE)
ms:assetid: cfd8e3e0-4076-4162-9381-5276da8316d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205259(v=OCS.15)
ms:contentKeyID: 48185394
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7294c70a0ebfd49f954bbe911d2fccb81d79fa54
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530103"
---
# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="64dc3-102">Tabella UserAgentDef (QoE) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64dc3-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64dc3-103">_**Ultimo argomento modificato:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="64dc3-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="64dc3-104">Nella tabella UserAgentDef viene eseguito il mapping tra gli identificatori degli agenti utente e i nomi descrittivi degli agenti.</span><span class="sxs-lookup"><span data-stu-id="64dc3-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="64dc3-105">Gli agenti utente sono client software utilizzati per la connessione a Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64dc3-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64dc3-106">UAType</span><span class="sxs-lookup"><span data-stu-id="64dc3-106">UAType</span></span></th>
<th><span data-ttu-id="64dc3-107">UAName</span><span class="sxs-lookup"><span data-stu-id="64dc3-107">UAName</span></span></th>
<th><span data-ttu-id="64dc3-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="64dc3-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-109">1 </span><span class="sxs-lookup"><span data-stu-id="64dc3-109">1</span></span></p></td>
<td><p><span data-ttu-id="64dc3-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="64dc3-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="64dc3-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="64dc3-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-112">2</span><span class="sxs-lookup"><span data-stu-id="64dc3-112">2</span></span></p></td>
<td><p><span data-ttu-id="64dc3-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="64dc3-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="64dc3-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="64dc3-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-115">4 </span><span class="sxs-lookup"><span data-stu-id="64dc3-115">4</span></span></p></td>
<td><p><span data-ttu-id="64dc3-116">OC</span><span class="sxs-lookup"><span data-stu-id="64dc3-116">OC</span></span></p></td>
<td><p><span data-ttu-id="64dc3-117">OC</span><span class="sxs-lookup"><span data-stu-id="64dc3-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-118">8 </span><span class="sxs-lookup"><span data-stu-id="64dc3-118">8</span></span></p></td>
<td><p><span data-ttu-id="64dc3-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="64dc3-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="64dc3-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="64dc3-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-121">16 </span><span class="sxs-lookup"><span data-stu-id="64dc3-121">16</span></span></p></td>
<td><p><span data-ttu-id="64dc3-122">LMC</span><span class="sxs-lookup"><span data-stu-id="64dc3-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="64dc3-123">LMC</span><span class="sxs-lookup"><span data-stu-id="64dc3-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-124">32</span><span class="sxs-lookup"><span data-stu-id="64dc3-124">32</span></span></p></td>
<td><p><span data-ttu-id="64dc3-125">DVT</span><span class="sxs-lookup"><span data-stu-id="64dc3-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="64dc3-126">DVT</span><span class="sxs-lookup"><span data-stu-id="64dc3-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-127">64</span><span class="sxs-lookup"><span data-stu-id="64dc3-127">64</span></span></p></td>
<td><p><span data-ttu-id="64dc3-128">MM</span><span class="sxs-lookup"><span data-stu-id="64dc3-128">MM</span></span></p></td>
<td><p><span data-ttu-id="64dc3-129">MM</span><span class="sxs-lookup"><span data-stu-id="64dc3-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-130">64</span><span class="sxs-lookup"><span data-stu-id="64dc3-130">64</span></span></p></td>
<td><p><span data-ttu-id="64dc3-131">MC</span><span class="sxs-lookup"><span data-stu-id="64dc3-131">MC</span></span></p></td>
<td><p><span data-ttu-id="64dc3-132">MM</span><span class="sxs-lookup"><span data-stu-id="64dc3-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-133">128</span><span class="sxs-lookup"><span data-stu-id="64dc3-133">128</span></span></p></td>
<td><p><span data-ttu-id="64dc3-134">Attendant</span><span class="sxs-lookup"><span data-stu-id="64dc3-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="64dc3-135">Attendant</span><span class="sxs-lookup"><span data-stu-id="64dc3-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-136">256</span><span class="sxs-lookup"><span data-stu-id="64dc3-136">256</span></span></p></td>
<td><p><span data-ttu-id="64dc3-137">Conferencing_Announcement_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="64dc3-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="64dc3-138">CAS</span><span class="sxs-lookup"><span data-stu-id="64dc3-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-139">512</span><span class="sxs-lookup"><span data-stu-id="64dc3-139">512</span></span></p></td>
<td><p><span data-ttu-id="64dc3-140">Conferencing_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="64dc3-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="64dc3-141">CAA</span><span class="sxs-lookup"><span data-stu-id="64dc3-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-142">512</span><span class="sxs-lookup"><span data-stu-id="64dc3-142">512</span></span></p></td>
<td><p><span data-ttu-id="64dc3-143">Conference_Auto_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="64dc3-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="64dc3-144">CAA</span><span class="sxs-lookup"><span data-stu-id="64dc3-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-145">1024</span><span class="sxs-lookup"><span data-stu-id="64dc3-145">1024</span></span></p></td>
<td><p><span data-ttu-id="64dc3-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="64dc3-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="64dc3-147">RGS</span><span class="sxs-lookup"><span data-stu-id="64dc3-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-148">1032</span><span class="sxs-lookup"><span data-stu-id="64dc3-148">1032</span></span></p></td>
<td><p><span data-ttu-id="64dc3-149">Call_Park_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="64dc3-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="64dc3-150">CPS</span><span class="sxs-lookup"><span data-stu-id="64dc3-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-151">1040</span><span class="sxs-lookup"><span data-stu-id="64dc3-151">1040</span></span></p></td>
<td><p><span data-ttu-id="64dc3-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="64dc3-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="64dc3-153">COME</span><span class="sxs-lookup"><span data-stu-id="64dc3-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-154">2048</span><span class="sxs-lookup"><span data-stu-id="64dc3-154">2048</span></span></p></td>
<td><p><span data-ttu-id="64dc3-155">Microsoft. Rtc. Applications. CCS</span><span class="sxs-lookup"><span data-stu-id="64dc3-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="64dc3-156">CCS</span><span class="sxs-lookup"><span data-stu-id="64dc3-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-157">16386</span><span class="sxs-lookup"><span data-stu-id="64dc3-157">16386</span></span></p></td>
<td><p><span data-ttu-id="64dc3-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="64dc3-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="64dc3-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="64dc3-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-160">16387</span><span class="sxs-lookup"><span data-stu-id="64dc3-160">16387</span></span></p></td>
<td><p><span data-ttu-id="64dc3-161">CWA</span><span class="sxs-lookup"><span data-stu-id="64dc3-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="64dc3-162">CWA</span><span class="sxs-lookup"><span data-stu-id="64dc3-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-163">16388</span><span class="sxs-lookup"><span data-stu-id="64dc3-163">16388</span></span></p></td>
<td><p><span data-ttu-id="64dc3-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="64dc3-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="64dc3-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="64dc3-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-166">16389</span><span class="sxs-lookup"><span data-stu-id="64dc3-166">16389</span></span></p></td>
<td><p><span data-ttu-id="64dc3-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="64dc3-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="64dc3-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="64dc3-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-169">16393</span><span class="sxs-lookup"><span data-stu-id="64dc3-169">16393</span></span></p></td>
<td><p><span data-ttu-id="64dc3-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="64dc3-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="64dc3-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="64dc3-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-172">16395</span><span class="sxs-lookup"><span data-stu-id="64dc3-172">16395</span></span></p></td>
<td><p><span data-ttu-id="64dc3-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="64dc3-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="64dc3-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="64dc3-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-175">16396</span><span class="sxs-lookup"><span data-stu-id="64dc3-175">16396</span></span></p></td>
<td><p><span data-ttu-id="64dc3-176">ST</span><span class="sxs-lookup"><span data-stu-id="64dc3-176">ST</span></span></p></td>
<td><p><span data-ttu-id="64dc3-177">ST</span><span class="sxs-lookup"><span data-stu-id="64dc3-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-178">16397</span><span class="sxs-lookup"><span data-stu-id="64dc3-178">16397</span></span></p></td>
<td><p><span data-ttu-id="64dc3-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="64dc3-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="64dc3-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="64dc3-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-181">16398</span><span class="sxs-lookup"><span data-stu-id="64dc3-181">16398</span></span></p></td>
<td><p><span data-ttu-id="64dc3-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="64dc3-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="64dc3-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="64dc3-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-184">16399</span><span class="sxs-lookup"><span data-stu-id="64dc3-184">16399</span></span></p></td>
<td><p><span data-ttu-id="64dc3-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="64dc3-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="64dc3-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="64dc3-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-187">16400</span><span class="sxs-lookup"><span data-stu-id="64dc3-187">16400</span></span></p></td>
<td><p><span data-ttu-id="64dc3-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="64dc3-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="64dc3-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="64dc3-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-190">16401</span><span class="sxs-lookup"><span data-stu-id="64dc3-190">16401</span></span></p></td>
<td><p><span data-ttu-id="64dc3-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="64dc3-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="64dc3-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="64dc3-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-193">16402</span><span class="sxs-lookup"><span data-stu-id="64dc3-193">16402</span></span></p></td>
<td><p><span data-ttu-id="64dc3-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="64dc3-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="64dc3-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="64dc3-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-196">16403</span><span class="sxs-lookup"><span data-stu-id="64dc3-196">16403</span></span></p></td>
<td><p><span data-ttu-id="64dc3-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="64dc3-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="64dc3-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="64dc3-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-199">16404</span><span class="sxs-lookup"><span data-stu-id="64dc3-199">16404</span></span></p></td>
<td><p><span data-ttu-id="64dc3-200">PC</span><span class="sxs-lookup"><span data-stu-id="64dc3-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="64dc3-201">PC</span><span class="sxs-lookup"><span data-stu-id="64dc3-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-202">16405</span><span class="sxs-lookup"><span data-stu-id="64dc3-202">16405</span></span></p></td>
<td><p><span data-ttu-id="64dc3-203">LWA</span><span class="sxs-lookup"><span data-stu-id="64dc3-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="64dc3-204">LWA</span><span class="sxs-lookup"><span data-stu-id="64dc3-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-205">16406</span><span class="sxs-lookup"><span data-stu-id="64dc3-205">16406</span></span></p></td>
<td><p><span data-ttu-id="64dc3-206">OWA</span><span class="sxs-lookup"><span data-stu-id="64dc3-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="64dc3-207">OWA</span><span class="sxs-lookup"><span data-stu-id="64dc3-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-208">16407</span><span class="sxs-lookup"><span data-stu-id="64dc3-208">16407</span></span></p></td>
<td><p><span data-ttu-id="64dc3-209">AOC</span><span class="sxs-lookup"><span data-stu-id="64dc3-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="64dc3-210">AOC</span><span class="sxs-lookup"><span data-stu-id="64dc3-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-211">16408</span><span class="sxs-lookup"><span data-stu-id="64dc3-211">16408</span></span></p></td>
<td><p><span data-ttu-id="64dc3-212">GCC</span><span class="sxs-lookup"><span data-stu-id="64dc3-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="64dc3-213">GCC</span><span class="sxs-lookup"><span data-stu-id="64dc3-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-214">16409</span><span class="sxs-lookup"><span data-stu-id="64dc3-214">16409</span></span></p></td>
<td><p><span data-ttu-id="64dc3-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="64dc3-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="64dc3-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="64dc3-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-217">16410</span><span class="sxs-lookup"><span data-stu-id="64dc3-217">16410</span></span></p></td>
<td><p><span data-ttu-id="64dc3-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="64dc3-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="64dc3-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="64dc3-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dc3-220">32769</span><span class="sxs-lookup"><span data-stu-id="64dc3-220">32769</span></span></p></td>
<td><p><span data-ttu-id="64dc3-221">Gateway</span><span class="sxs-lookup"><span data-stu-id="64dc3-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="64dc3-222">Gateway</span><span class="sxs-lookup"><span data-stu-id="64dc3-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64dc3-223">32770</span><span class="sxs-lookup"><span data-stu-id="64dc3-223">32770</span></span></p></td>
<td><p><span data-ttu-id="64dc3-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="64dc3-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="64dc3-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="64dc3-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

