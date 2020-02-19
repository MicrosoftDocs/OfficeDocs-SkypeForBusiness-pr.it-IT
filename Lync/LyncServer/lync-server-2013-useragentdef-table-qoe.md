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
ms.openlocfilehash: a37ea828dfe633ca8a685feb61311d59f443ae14
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="8ba77-102">Tabella UserAgentDef (QoE) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ba77-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ba77-103">_**Ultimo argomento modificato:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="8ba77-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="8ba77-104">Nella tabella UserAgentDef viene eseguito il mapping tra gli identificatori degli agenti utente e i nomi descrittivi degli agenti.</span><span class="sxs-lookup"><span data-stu-id="8ba77-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="8ba77-105">Gli agenti utente sono client software utilizzati per la connessione a Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ba77-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ba77-106">UAType</span><span class="sxs-lookup"><span data-stu-id="8ba77-106">UAType</span></span></th>
<th><span data-ttu-id="8ba77-107">UAName</span><span class="sxs-lookup"><span data-stu-id="8ba77-107">UAName</span></span></th>
<th><span data-ttu-id="8ba77-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="8ba77-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-109">1</span><span class="sxs-lookup"><span data-stu-id="8ba77-109">1</span></span></p></td>
<td><p><span data-ttu-id="8ba77-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="8ba77-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="8ba77-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="8ba77-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-112">2</span><span class="sxs-lookup"><span data-stu-id="8ba77-112">2</span></span></p></td>
<td><p><span data-ttu-id="8ba77-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="8ba77-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="8ba77-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="8ba77-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-115">4</span><span class="sxs-lookup"><span data-stu-id="8ba77-115">4</span></span></p></td>
<td><p><span data-ttu-id="8ba77-116">OC</span><span class="sxs-lookup"><span data-stu-id="8ba77-116">OC</span></span></p></td>
<td><p><span data-ttu-id="8ba77-117">OC</span><span class="sxs-lookup"><span data-stu-id="8ba77-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-118">8 </span><span class="sxs-lookup"><span data-stu-id="8ba77-118">8</span></span></p></td>
<td><p><span data-ttu-id="8ba77-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="8ba77-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="8ba77-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="8ba77-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-121">16 </span><span class="sxs-lookup"><span data-stu-id="8ba77-121">16</span></span></p></td>
<td><p><span data-ttu-id="8ba77-122">LMC</span><span class="sxs-lookup"><span data-stu-id="8ba77-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="8ba77-123">LMC</span><span class="sxs-lookup"><span data-stu-id="8ba77-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-124">32</span><span class="sxs-lookup"><span data-stu-id="8ba77-124">32</span></span></p></td>
<td><p><span data-ttu-id="8ba77-125">DVT</span><span class="sxs-lookup"><span data-stu-id="8ba77-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="8ba77-126">DVT</span><span class="sxs-lookup"><span data-stu-id="8ba77-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-127">64</span><span class="sxs-lookup"><span data-stu-id="8ba77-127">64</span></span></p></td>
<td><p><span data-ttu-id="8ba77-128">MM</span><span class="sxs-lookup"><span data-stu-id="8ba77-128">MM</span></span></p></td>
<td><p><span data-ttu-id="8ba77-129">MM</span><span class="sxs-lookup"><span data-stu-id="8ba77-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-130">64</span><span class="sxs-lookup"><span data-stu-id="8ba77-130">64</span></span></p></td>
<td><p><span data-ttu-id="8ba77-131">MC</span><span class="sxs-lookup"><span data-stu-id="8ba77-131">MC</span></span></p></td>
<td><p><span data-ttu-id="8ba77-132">MM</span><span class="sxs-lookup"><span data-stu-id="8ba77-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-133">128</span><span class="sxs-lookup"><span data-stu-id="8ba77-133">128</span></span></p></td>
<td><p><span data-ttu-id="8ba77-134">Operatore</span><span class="sxs-lookup"><span data-stu-id="8ba77-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="8ba77-135">Operatore</span><span class="sxs-lookup"><span data-stu-id="8ba77-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-136">256</span><span class="sxs-lookup"><span data-stu-id="8ba77-136">256</span></span></p></td>
<td><p><span data-ttu-id="8ba77-137">Conferencing_Announcement_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="8ba77-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="8ba77-138">CAS</span><span class="sxs-lookup"><span data-stu-id="8ba77-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-139">512</span><span class="sxs-lookup"><span data-stu-id="8ba77-139">512</span></span></p></td>
<td><p><span data-ttu-id="8ba77-140">Conferencing_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="8ba77-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="8ba77-141">CAA</span><span class="sxs-lookup"><span data-stu-id="8ba77-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-142">512</span><span class="sxs-lookup"><span data-stu-id="8ba77-142">512</span></span></p></td>
<td><p><span data-ttu-id="8ba77-143">Conference_Auto_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="8ba77-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="8ba77-144">CAA</span><span class="sxs-lookup"><span data-stu-id="8ba77-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-145">1024</span><span class="sxs-lookup"><span data-stu-id="8ba77-145">1024</span></span></p></td>
<td><p><span data-ttu-id="8ba77-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="8ba77-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="8ba77-147">RGS</span><span class="sxs-lookup"><span data-stu-id="8ba77-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-148">1032</span><span class="sxs-lookup"><span data-stu-id="8ba77-148">1032</span></span></p></td>
<td><p><span data-ttu-id="8ba77-149">Call_Park_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="8ba77-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="8ba77-150">CPS</span><span class="sxs-lookup"><span data-stu-id="8ba77-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-151">1040</span><span class="sxs-lookup"><span data-stu-id="8ba77-151">1040</span></span></p></td>
<td><p><span data-ttu-id="8ba77-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="8ba77-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="8ba77-153">COME</span><span class="sxs-lookup"><span data-stu-id="8ba77-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-154">2048</span><span class="sxs-lookup"><span data-stu-id="8ba77-154">2048</span></span></p></td>
<td><p><span data-ttu-id="8ba77-155">Microsoft. Rtc. Applications. CCS</span><span class="sxs-lookup"><span data-stu-id="8ba77-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="8ba77-156">CCS</span><span class="sxs-lookup"><span data-stu-id="8ba77-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-157">16386</span><span class="sxs-lookup"><span data-stu-id="8ba77-157">16386</span></span></p></td>
<td><p><span data-ttu-id="8ba77-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="8ba77-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="8ba77-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="8ba77-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-160">16387</span><span class="sxs-lookup"><span data-stu-id="8ba77-160">16387</span></span></p></td>
<td><p><span data-ttu-id="8ba77-161">CWA</span><span class="sxs-lookup"><span data-stu-id="8ba77-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="8ba77-162">CWA</span><span class="sxs-lookup"><span data-stu-id="8ba77-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-163">16388</span><span class="sxs-lookup"><span data-stu-id="8ba77-163">16388</span></span></p></td>
<td><p><span data-ttu-id="8ba77-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="8ba77-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="8ba77-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="8ba77-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-166">16389</span><span class="sxs-lookup"><span data-stu-id="8ba77-166">16389</span></span></p></td>
<td><p><span data-ttu-id="8ba77-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="8ba77-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="8ba77-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="8ba77-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-169">16393</span><span class="sxs-lookup"><span data-stu-id="8ba77-169">16393</span></span></p></td>
<td><p><span data-ttu-id="8ba77-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="8ba77-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="8ba77-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="8ba77-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-172">16395</span><span class="sxs-lookup"><span data-stu-id="8ba77-172">16395</span></span></p></td>
<td><p><span data-ttu-id="8ba77-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="8ba77-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="8ba77-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="8ba77-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-175">16396</span><span class="sxs-lookup"><span data-stu-id="8ba77-175">16396</span></span></p></td>
<td><p><span data-ttu-id="8ba77-176">ST</span><span class="sxs-lookup"><span data-stu-id="8ba77-176">ST</span></span></p></td>
<td><p><span data-ttu-id="8ba77-177">ST</span><span class="sxs-lookup"><span data-stu-id="8ba77-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-178">16397</span><span class="sxs-lookup"><span data-stu-id="8ba77-178">16397</span></span></p></td>
<td><p><span data-ttu-id="8ba77-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="8ba77-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="8ba77-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="8ba77-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-181">16398</span><span class="sxs-lookup"><span data-stu-id="8ba77-181">16398</span></span></p></td>
<td><p><span data-ttu-id="8ba77-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="8ba77-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="8ba77-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="8ba77-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-184">16399</span><span class="sxs-lookup"><span data-stu-id="8ba77-184">16399</span></span></p></td>
<td><p><span data-ttu-id="8ba77-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="8ba77-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="8ba77-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="8ba77-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-187">16400</span><span class="sxs-lookup"><span data-stu-id="8ba77-187">16400</span></span></p></td>
<td><p><span data-ttu-id="8ba77-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="8ba77-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="8ba77-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="8ba77-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-190">16401</span><span class="sxs-lookup"><span data-stu-id="8ba77-190">16401</span></span></p></td>
<td><p><span data-ttu-id="8ba77-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="8ba77-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="8ba77-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="8ba77-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-193">16402</span><span class="sxs-lookup"><span data-stu-id="8ba77-193">16402</span></span></p></td>
<td><p><span data-ttu-id="8ba77-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="8ba77-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="8ba77-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="8ba77-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-196">16403</span><span class="sxs-lookup"><span data-stu-id="8ba77-196">16403</span></span></p></td>
<td><p><span data-ttu-id="8ba77-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="8ba77-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="8ba77-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="8ba77-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-199">16404</span><span class="sxs-lookup"><span data-stu-id="8ba77-199">16404</span></span></p></td>
<td><p><span data-ttu-id="8ba77-200">PC</span><span class="sxs-lookup"><span data-stu-id="8ba77-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="8ba77-201">PC</span><span class="sxs-lookup"><span data-stu-id="8ba77-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-202">16405</span><span class="sxs-lookup"><span data-stu-id="8ba77-202">16405</span></span></p></td>
<td><p><span data-ttu-id="8ba77-203">LWA</span><span class="sxs-lookup"><span data-stu-id="8ba77-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="8ba77-204">LWA</span><span class="sxs-lookup"><span data-stu-id="8ba77-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-205">16406</span><span class="sxs-lookup"><span data-stu-id="8ba77-205">16406</span></span></p></td>
<td><p><span data-ttu-id="8ba77-206">OWA</span><span class="sxs-lookup"><span data-stu-id="8ba77-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="8ba77-207">OWA</span><span class="sxs-lookup"><span data-stu-id="8ba77-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-208">16407</span><span class="sxs-lookup"><span data-stu-id="8ba77-208">16407</span></span></p></td>
<td><p><span data-ttu-id="8ba77-209">AOC</span><span class="sxs-lookup"><span data-stu-id="8ba77-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="8ba77-210">AOC</span><span class="sxs-lookup"><span data-stu-id="8ba77-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-211">16408</span><span class="sxs-lookup"><span data-stu-id="8ba77-211">16408</span></span></p></td>
<td><p><span data-ttu-id="8ba77-212">GCC</span><span class="sxs-lookup"><span data-stu-id="8ba77-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="8ba77-213">GCC</span><span class="sxs-lookup"><span data-stu-id="8ba77-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-214">16409</span><span class="sxs-lookup"><span data-stu-id="8ba77-214">16409</span></span></p></td>
<td><p><span data-ttu-id="8ba77-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="8ba77-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="8ba77-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="8ba77-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-217">16410</span><span class="sxs-lookup"><span data-stu-id="8ba77-217">16410</span></span></p></td>
<td><p><span data-ttu-id="8ba77-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="8ba77-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="8ba77-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="8ba77-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba77-220">32769</span><span class="sxs-lookup"><span data-stu-id="8ba77-220">32769</span></span></p></td>
<td><p><span data-ttu-id="8ba77-221">Gateway</span><span class="sxs-lookup"><span data-stu-id="8ba77-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="8ba77-222">Gateway</span><span class="sxs-lookup"><span data-stu-id="8ba77-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba77-223">32770</span><span class="sxs-lookup"><span data-stu-id="8ba77-223">32770</span></span></p></td>
<td><p><span data-ttu-id="8ba77-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="8ba77-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="8ba77-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="8ba77-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

