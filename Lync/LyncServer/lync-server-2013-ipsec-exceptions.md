---
title: Eccezioni IPsec di Lync Server 2013
description: Eccezioni IPsec di Lync Server 2013.
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
ms.openlocfilehash: 9b01264171592ec352b778e1aa7eee5861801991
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575002"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="81cd3-103">Eccezioni IPsec in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81cd3-103">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81cd3-104">_**Ultimo argomento modificato:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="81cd3-104">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="81cd3-p101">Per le reti aziendali in cui è stato distribuito IPsec (Internet Protocol Security) (vedere IETF RFC 4301-4309), è necessario disabilitare tale protocollo per l'intervallo delle porte utilizzate per l'invio del traffico audio, video e panorama video. Questa richiesta nasce dall'esigenza di evitare ritardi nell'allocazione delle porte multimediali a causa della negoziazione IPsec.</span><span class="sxs-lookup"><span data-stu-id="81cd3-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="81cd3-107">Nella tabella riportata di seguito vengono illustrate le impostazioni di eccezione IPsec consigliate.</span><span class="sxs-lookup"><span data-stu-id="81cd3-107">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="81cd3-108">Eccezioni IPsec consigliate</span><span class="sxs-lookup"><span data-stu-id="81cd3-108">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="81cd3-109">Nome regola</span><span class="sxs-lookup"><span data-stu-id="81cd3-109">Rule name</span></span></th>
<th><span data-ttu-id="81cd3-110">IP origine</span><span class="sxs-lookup"><span data-stu-id="81cd3-110">Source IP</span></span></th>
<th><span data-ttu-id="81cd3-111">IP destinazione</span><span class="sxs-lookup"><span data-stu-id="81cd3-111">Destination IP</span></span></th>
<th><span data-ttu-id="81cd3-112">Protocollo</span><span class="sxs-lookup"><span data-stu-id="81cd3-112">Protocol</span></span></th>
<th><span data-ttu-id="81cd3-113">Porta origine</span><span class="sxs-lookup"><span data-stu-id="81cd3-113">Source port</span></span></th>
<th><span data-ttu-id="81cd3-114">Porta destinazione</span><span class="sxs-lookup"><span data-stu-id="81cd3-114">Destination port</span></span></th>
<th><span data-ttu-id="81cd3-115">Requisito di autenticazione</span><span class="sxs-lookup"><span data-stu-id="81cd3-115">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81cd3-116">A/V Edge Server in ingresso interno</span><span class="sxs-lookup"><span data-stu-id="81cd3-116">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="81cd3-117">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-117">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-118">A/V Edge Server interno</span><span class="sxs-lookup"><span data-stu-id="81cd3-118">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="81cd3-119">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="81cd3-119">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="81cd3-120">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-120">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-121">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-121">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-122">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="81cd3-122">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81cd3-123">A/V Edge Server in ingresso esterno</span><span class="sxs-lookup"><span data-stu-id="81cd3-123">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="81cd3-124">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-124">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-125">A/V Edge Server esterno</span><span class="sxs-lookup"><span data-stu-id="81cd3-125">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="81cd3-126">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="81cd3-126">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="81cd3-127">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-127">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-128">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-128">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-129">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="81cd3-129">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81cd3-130">A/V Edge Server interno in uscita</span><span class="sxs-lookup"><span data-stu-id="81cd3-130">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="81cd3-131">A/V Edge Server interno</span><span class="sxs-lookup"><span data-stu-id="81cd3-131">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="81cd3-132">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-132">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-133">&amp;TCP UDP</span><span class="sxs-lookup"><span data-stu-id="81cd3-133">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="81cd3-134">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-134">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-135">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-135">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-136">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="81cd3-136">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81cd3-137">A/V Edge Server esterno in uscita</span><span class="sxs-lookup"><span data-stu-id="81cd3-137">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="81cd3-138">A/V Edge Server esterno</span><span class="sxs-lookup"><span data-stu-id="81cd3-138">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="81cd3-139">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-139">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-140">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="81cd3-140">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="81cd3-141">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-141">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-142">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-142">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-143">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="81cd3-143">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81cd3-144">Mediation Server in ingresso</span><span class="sxs-lookup"><span data-stu-id="81cd3-144">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="81cd3-145">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-145">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-146">Mediation</span><span class="sxs-lookup"><span data-stu-id="81cd3-146">Mediation</span></span></p>
<p><span data-ttu-id="81cd3-147">Server (s)</span><span class="sxs-lookup"><span data-stu-id="81cd3-147">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="81cd3-148">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="81cd3-148">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="81cd3-149">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-149">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-150">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-150">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-151">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="81cd3-151">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81cd3-152">Mediation Server in uscita</span><span class="sxs-lookup"><span data-stu-id="81cd3-152">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="81cd3-153">Mediation</span><span class="sxs-lookup"><span data-stu-id="81cd3-153">Mediation</span></span></p>
<p><span data-ttu-id="81cd3-154">Server (s)</span><span class="sxs-lookup"><span data-stu-id="81cd3-154">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="81cd3-155">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-155">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-156">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="81cd3-156">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="81cd3-157">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-157">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-158">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-158">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-159">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="81cd3-159">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81cd3-160">Operatore Conferenza in ingresso</span><span class="sxs-lookup"><span data-stu-id="81cd3-160">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="81cd3-161">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-161">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-162">Front End Server con Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="81cd3-162">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="81cd3-163">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="81cd3-163">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="81cd3-164">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-164">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-165">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-165">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-166">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="81cd3-166">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81cd3-167">Operatore Conferenza in uscita</span><span class="sxs-lookup"><span data-stu-id="81cd3-167">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="81cd3-168">Front End Server con Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="81cd3-168">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="81cd3-169">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-169">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-170">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="81cd3-170">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="81cd3-171">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-171">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-172">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-172">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-173">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="81cd3-173">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81cd3-174">A/V Conferencing Server in ingresso</span><span class="sxs-lookup"><span data-stu-id="81cd3-174">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="81cd3-175">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-175">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-176">Front End Server</span><span class="sxs-lookup"><span data-stu-id="81cd3-176">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="81cd3-177">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="81cd3-177">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="81cd3-178">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-178">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-179">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-179">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-180">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="81cd3-180">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81cd3-181">A/V Conferencing in uscita</span><span class="sxs-lookup"><span data-stu-id="81cd3-181">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="81cd3-182">Front End Server</span><span class="sxs-lookup"><span data-stu-id="81cd3-182">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="81cd3-183">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-183">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-184">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="81cd3-184">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="81cd3-185">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-185">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-186">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-186">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-187">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="81cd3-187">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81cd3-188">Exchange in ingresso</span><span class="sxs-lookup"><span data-stu-id="81cd3-188">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="81cd3-189">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-189">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-190">Messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="81cd3-190">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="81cd3-191">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="81cd3-191">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="81cd3-192">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-192">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-193">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-193">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-194">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="81cd3-194">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81cd3-195">Server di condivisione applicazioni in ingresso</span><span class="sxs-lookup"><span data-stu-id="81cd3-195">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="81cd3-196">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-196">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-197">Server di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="81cd3-197">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="81cd3-198">TCP</span><span class="sxs-lookup"><span data-stu-id="81cd3-198">TCP</span></span></p></td>
<td><p><span data-ttu-id="81cd3-199">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-199">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-200">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-200">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-201">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="81cd3-201">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81cd3-202">Server di condivisione applicazioni in uscita</span><span class="sxs-lookup"><span data-stu-id="81cd3-202">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="81cd3-203">Server di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="81cd3-203">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="81cd3-204">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-204">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-205">TCP</span><span class="sxs-lookup"><span data-stu-id="81cd3-205">TCP</span></span></p></td>
<td><p><span data-ttu-id="81cd3-206">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-206">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-207">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-207">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-208">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="81cd3-208">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81cd3-209">Exchange in uscita</span><span class="sxs-lookup"><span data-stu-id="81cd3-209">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="81cd3-210">Messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="81cd3-210">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="81cd3-211">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-211">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-212">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="81cd3-212">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="81cd3-213">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-213">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-214">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-214">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-215">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="81cd3-215">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81cd3-216">Client</span><span class="sxs-lookup"><span data-stu-id="81cd3-216">Clients</span></span></p></td>
<td><p><span data-ttu-id="81cd3-217">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-217">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-218">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-218">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-219">UDP</span><span class="sxs-lookup"><span data-stu-id="81cd3-219">UDP</span></span></p></td>
<td><p><span data-ttu-id="81cd3-220">Intervallo porte multimediali specificato</span><span class="sxs-lookup"><span data-stu-id="81cd3-220">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="81cd3-221">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="81cd3-221">Any</span></span></p></td>
<td><p><span data-ttu-id="81cd3-222">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="81cd3-222">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

