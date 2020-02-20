---
title: Eccezioni IPsec di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 665e97359af930614c2f7e2b251317f34e46ef0e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="7c88d-102">Eccezioni IPsec in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c88d-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c88d-103">_**Ultimo argomento modificato:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="7c88d-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="7c88d-p101">Per le reti aziendali in cui è stato distribuito IPsec (Internet Protocol Security) (vedere IETF RFC 4301-4309), è necessario disabilitare tale protocollo per l'intervallo delle porte utilizzate per l'invio del traffico audio, video e panorama video. Questa richiesta nasce dall'esigenza di evitare ritardi nell'allocazione delle porte multimediali a causa della negoziazione IPsec.</span><span class="sxs-lookup"><span data-stu-id="7c88d-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="7c88d-106">Nella tabella riportata di seguito vengono illustrate le impostazioni di eccezione IPsec consigliate.</span><span class="sxs-lookup"><span data-stu-id="7c88d-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="7c88d-107">Eccezioni IPsec consigliate</span><span class="sxs-lookup"><span data-stu-id="7c88d-107">Recommended IPsec Exceptions</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c88d-108">Nome regola</span><span class="sxs-lookup"><span data-stu-id="7c88d-108">Rule name</span></span></th>
<th><span data-ttu-id="7c88d-109">IP origine</span><span class="sxs-lookup"><span data-stu-id="7c88d-109">Source IP</span></span></th>
<th><span data-ttu-id="7c88d-110">IP destinazione</span><span class="sxs-lookup"><span data-stu-id="7c88d-110">Destination IP</span></span></th>
<th><span data-ttu-id="7c88d-111">Protocol</span><span class="sxs-lookup"><span data-stu-id="7c88d-111">Protocol</span></span></th>
<th><span data-ttu-id="7c88d-112">Porta origine</span><span class="sxs-lookup"><span data-stu-id="7c88d-112">Source port</span></span></th>
<th><span data-ttu-id="7c88d-113">Porta destinazione</span><span class="sxs-lookup"><span data-stu-id="7c88d-113">Destination port</span></span></th>
<th><span data-ttu-id="7c88d-114">Requisito di autenticazione</span><span class="sxs-lookup"><span data-stu-id="7c88d-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c88d-115">A/V Edge Server in ingresso interno</span><span class="sxs-lookup"><span data-stu-id="7c88d-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="7c88d-116">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-116">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-117">A/V Edge Server interno</span><span class="sxs-lookup"><span data-stu-id="7c88d-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="7c88d-118">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="7c88d-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7c88d-119">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-119">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-120">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-120">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-121">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="7c88d-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c88d-122">A/V Edge Server in ingresso esterno</span><span class="sxs-lookup"><span data-stu-id="7c88d-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="7c88d-123">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-123">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-124">A/V Edge Server esterno</span><span class="sxs-lookup"><span data-stu-id="7c88d-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="7c88d-125">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="7c88d-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7c88d-126">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-126">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-127">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-127">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-128">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="7c88d-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c88d-129">A/V Edge Server interno in uscita</span><span class="sxs-lookup"><span data-stu-id="7c88d-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="7c88d-130">A/V Edge Server interno</span><span class="sxs-lookup"><span data-stu-id="7c88d-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="7c88d-131">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-131">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-132">TCP &amp; UDP</span><span class="sxs-lookup"><span data-stu-id="7c88d-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="7c88d-133">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-133">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-134">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-134">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-135">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="7c88d-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c88d-136">A/V Edge Server esterno in uscita</span><span class="sxs-lookup"><span data-stu-id="7c88d-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="7c88d-137">A/V Edge Server esterno</span><span class="sxs-lookup"><span data-stu-id="7c88d-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="7c88d-138">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-138">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-139">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="7c88d-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7c88d-140">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-140">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-141">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-141">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-142">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="7c88d-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c88d-143">Mediation Server in ingresso</span><span class="sxs-lookup"><span data-stu-id="7c88d-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="7c88d-144">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-144">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-145">Mediation</span><span class="sxs-lookup"><span data-stu-id="7c88d-145">Mediation</span></span></p>
<p><span data-ttu-id="7c88d-146">Server (s)</span><span class="sxs-lookup"><span data-stu-id="7c88d-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="7c88d-147">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="7c88d-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7c88d-148">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-148">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-149">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-149">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-150">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="7c88d-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c88d-151">Mediation Server in uscita</span><span class="sxs-lookup"><span data-stu-id="7c88d-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="7c88d-152">Mediation</span><span class="sxs-lookup"><span data-stu-id="7c88d-152">Mediation</span></span></p>
<p><span data-ttu-id="7c88d-153">Server (s)</span><span class="sxs-lookup"><span data-stu-id="7c88d-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="7c88d-154">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-154">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-155">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="7c88d-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7c88d-156">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-156">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-157">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-157">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-158">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="7c88d-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c88d-159">Operatore Conferenza in ingresso</span><span class="sxs-lookup"><span data-stu-id="7c88d-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="7c88d-160">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-160">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-161">Front End Server con Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="7c88d-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="7c88d-162">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="7c88d-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7c88d-163">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-163">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-164">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-164">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-165">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="7c88d-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c88d-166">Operatore Conferenza in uscita</span><span class="sxs-lookup"><span data-stu-id="7c88d-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="7c88d-167">Front End Server con Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="7c88d-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="7c88d-168">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-168">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-169">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="7c88d-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7c88d-170">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-170">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-171">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-171">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-172">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="7c88d-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c88d-173">A/V Conferencing Server in ingresso</span><span class="sxs-lookup"><span data-stu-id="7c88d-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="7c88d-174">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-174">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-175">Front End Server</span><span class="sxs-lookup"><span data-stu-id="7c88d-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="7c88d-176">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="7c88d-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7c88d-177">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-177">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-178">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-178">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-179">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="7c88d-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c88d-180">A/V Conferencing in uscita</span><span class="sxs-lookup"><span data-stu-id="7c88d-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="7c88d-181">Front End Server</span><span class="sxs-lookup"><span data-stu-id="7c88d-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="7c88d-182">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-182">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-183">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="7c88d-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7c88d-184">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-184">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-185">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-185">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-186">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="7c88d-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c88d-187">Exchange in ingresso</span><span class="sxs-lookup"><span data-stu-id="7c88d-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="7c88d-188">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-188">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-189">Messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="7c88d-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="7c88d-190">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="7c88d-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7c88d-191">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-191">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-192">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-192">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-193">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="7c88d-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c88d-194">Server di condivisione applicazioni in ingresso</span><span class="sxs-lookup"><span data-stu-id="7c88d-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="7c88d-195">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-195">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-196">Server di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="7c88d-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="7c88d-197">TCP</span><span class="sxs-lookup"><span data-stu-id="7c88d-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="7c88d-198">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-198">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-199">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-199">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-200">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="7c88d-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c88d-201">Server di condivisione applicazioni in uscita</span><span class="sxs-lookup"><span data-stu-id="7c88d-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="7c88d-202">Server di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="7c88d-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="7c88d-203">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-203">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-204">TCP</span><span class="sxs-lookup"><span data-stu-id="7c88d-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="7c88d-205">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-205">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-206">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-206">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-207">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="7c88d-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c88d-208">Exchange in uscita</span><span class="sxs-lookup"><span data-stu-id="7c88d-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="7c88d-209">Messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="7c88d-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="7c88d-210">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-210">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-211">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="7c88d-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="7c88d-212">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-212">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-213">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-213">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-214">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="7c88d-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c88d-215">Client</span><span class="sxs-lookup"><span data-stu-id="7c88d-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="7c88d-216">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-216">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-217">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-217">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-218">UDP</span><span class="sxs-lookup"><span data-stu-id="7c88d-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="7c88d-219">Intervallo porte multimediali specificato</span><span class="sxs-lookup"><span data-stu-id="7c88d-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="7c88d-220">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="7c88d-220">Any</span></span></p></td>
<td><p><span data-ttu-id="7c88d-221">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="7c88d-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

