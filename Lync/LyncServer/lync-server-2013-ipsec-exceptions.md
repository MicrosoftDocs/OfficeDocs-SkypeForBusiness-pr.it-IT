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
ms.openlocfilehash: 4ee06e4b7f3cabc606a612cd0f332aed47b46823
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514153"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="254f8-102">Eccezioni IPsec in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="254f8-102">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="254f8-103">_**Ultimo argomento modificato:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="254f8-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="254f8-p101">Per le reti aziendali in cui è stato distribuito IPsec (Internet Protocol Security) (vedere IETF RFC 4301-4309), è necessario disabilitare tale protocollo per l'intervallo delle porte utilizzate per l'invio del traffico audio, video e panorama video. Questa richiesta nasce dall'esigenza di evitare ritardi nell'allocazione delle porte multimediali a causa della negoziazione IPsec.</span><span class="sxs-lookup"><span data-stu-id="254f8-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="254f8-106">Nella tabella riportata di seguito vengono illustrate le impostazioni di eccezione IPsec consigliate.</span><span class="sxs-lookup"><span data-stu-id="254f8-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="254f8-107">Eccezioni IPsec consigliate</span><span class="sxs-lookup"><span data-stu-id="254f8-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="254f8-108">Nome regola</span><span class="sxs-lookup"><span data-stu-id="254f8-108">Rule name</span></span></th>
<th><span data-ttu-id="254f8-109">IP origine</span><span class="sxs-lookup"><span data-stu-id="254f8-109">Source IP</span></span></th>
<th><span data-ttu-id="254f8-110">IP destinazione</span><span class="sxs-lookup"><span data-stu-id="254f8-110">Destination IP</span></span></th>
<th><span data-ttu-id="254f8-111">Protocollo</span><span class="sxs-lookup"><span data-stu-id="254f8-111">Protocol</span></span></th>
<th><span data-ttu-id="254f8-112">Porta origine</span><span class="sxs-lookup"><span data-stu-id="254f8-112">Source port</span></span></th>
<th><span data-ttu-id="254f8-113">Porta destinazione</span><span class="sxs-lookup"><span data-stu-id="254f8-113">Destination port</span></span></th>
<th><span data-ttu-id="254f8-114">Requisito di autenticazione</span><span class="sxs-lookup"><span data-stu-id="254f8-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="254f8-115">A/V Edge Server in ingresso interno</span><span class="sxs-lookup"><span data-stu-id="254f8-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="254f8-116">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-116">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-117">A/V Edge Server interno</span><span class="sxs-lookup"><span data-stu-id="254f8-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="254f8-118">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="254f8-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="254f8-119">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-119">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-120">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-120">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-121">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="254f8-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="254f8-122">A/V Edge Server in ingresso esterno</span><span class="sxs-lookup"><span data-stu-id="254f8-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="254f8-123">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-123">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-124">A/V Edge Server esterno</span><span class="sxs-lookup"><span data-stu-id="254f8-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="254f8-125">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="254f8-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="254f8-126">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-126">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-127">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-127">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-128">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="254f8-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="254f8-129">A/V Edge Server interno in uscita</span><span class="sxs-lookup"><span data-stu-id="254f8-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="254f8-130">A/V Edge Server interno</span><span class="sxs-lookup"><span data-stu-id="254f8-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="254f8-131">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-131">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-132">&amp;TCP UDP</span><span class="sxs-lookup"><span data-stu-id="254f8-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="254f8-133">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-133">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-134">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-134">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-135">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="254f8-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="254f8-136">A/V Edge Server esterno in uscita</span><span class="sxs-lookup"><span data-stu-id="254f8-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="254f8-137">A/V Edge Server esterno</span><span class="sxs-lookup"><span data-stu-id="254f8-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="254f8-138">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-138">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-139">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="254f8-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="254f8-140">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-140">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-141">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-141">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-142">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="254f8-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="254f8-143">Mediation Server in ingresso</span><span class="sxs-lookup"><span data-stu-id="254f8-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="254f8-144">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-144">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-145">Mediation</span><span class="sxs-lookup"><span data-stu-id="254f8-145">Mediation</span></span></p>
<p><span data-ttu-id="254f8-146">Server (s)</span><span class="sxs-lookup"><span data-stu-id="254f8-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="254f8-147">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="254f8-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="254f8-148">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-148">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-149">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-149">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-150">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="254f8-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="254f8-151">Mediation Server in uscita</span><span class="sxs-lookup"><span data-stu-id="254f8-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="254f8-152">Mediation</span><span class="sxs-lookup"><span data-stu-id="254f8-152">Mediation</span></span></p>
<p><span data-ttu-id="254f8-153">Server (s)</span><span class="sxs-lookup"><span data-stu-id="254f8-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="254f8-154">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-154">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-155">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="254f8-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="254f8-156">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-156">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-157">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-157">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-158">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="254f8-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="254f8-159">Operatore Conferenza in ingresso</span><span class="sxs-lookup"><span data-stu-id="254f8-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="254f8-160">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-160">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-161">Front End Server con Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="254f8-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="254f8-162">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="254f8-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="254f8-163">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-163">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-164">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-164">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-165">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="254f8-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="254f8-166">Operatore Conferenza in uscita</span><span class="sxs-lookup"><span data-stu-id="254f8-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="254f8-167">Front End Server con Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="254f8-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="254f8-168">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-168">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-169">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="254f8-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="254f8-170">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-170">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-171">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-171">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-172">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="254f8-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="254f8-173">A/V Conferencing Server in ingresso</span><span class="sxs-lookup"><span data-stu-id="254f8-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="254f8-174">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-174">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-175">Front End Server</span><span class="sxs-lookup"><span data-stu-id="254f8-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="254f8-176">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="254f8-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="254f8-177">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-177">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-178">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-178">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-179">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="254f8-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="254f8-180">A/V Conferencing in uscita</span><span class="sxs-lookup"><span data-stu-id="254f8-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="254f8-181">Front End Server</span><span class="sxs-lookup"><span data-stu-id="254f8-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="254f8-182">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-182">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-183">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="254f8-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="254f8-184">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-184">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-185">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-185">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-186">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="254f8-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="254f8-187">Exchange in ingresso</span><span class="sxs-lookup"><span data-stu-id="254f8-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="254f8-188">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-188">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-189">Messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="254f8-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="254f8-190">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="254f8-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="254f8-191">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-191">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-192">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-192">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-193">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="254f8-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="254f8-194">Server di condivisione applicazioni in ingresso</span><span class="sxs-lookup"><span data-stu-id="254f8-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="254f8-195">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-195">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-196">Server di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="254f8-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="254f8-197">TCP</span><span class="sxs-lookup"><span data-stu-id="254f8-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="254f8-198">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-198">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-199">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-199">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-200">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="254f8-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="254f8-201">Server di condivisione applicazioni in uscita</span><span class="sxs-lookup"><span data-stu-id="254f8-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="254f8-202">Server di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="254f8-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="254f8-203">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-203">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-204">TCP</span><span class="sxs-lookup"><span data-stu-id="254f8-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="254f8-205">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-205">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-206">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-206">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-207">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="254f8-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="254f8-208">Exchange in uscita</span><span class="sxs-lookup"><span data-stu-id="254f8-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="254f8-209">Messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="254f8-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="254f8-210">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-210">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-211">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="254f8-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="254f8-212">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-212">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-213">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-213">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-214">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="254f8-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="254f8-215">Client</span><span class="sxs-lookup"><span data-stu-id="254f8-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="254f8-216">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-216">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-217">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-217">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-218">UDP</span><span class="sxs-lookup"><span data-stu-id="254f8-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="254f8-219">Intervallo porte multimediali specificato</span><span class="sxs-lookup"><span data-stu-id="254f8-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="254f8-220">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="254f8-220">Any</span></span></p></td>
<td><p><span data-ttu-id="254f8-221">Non autenticare</span><span class="sxs-lookup"><span data-stu-id="254f8-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

