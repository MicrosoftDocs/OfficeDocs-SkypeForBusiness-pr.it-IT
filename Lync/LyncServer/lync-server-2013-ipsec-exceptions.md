---
title: Eccezioni IPsec di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae9061036c91793800fd744338347196d60494c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="bdc33-102">Eccezioni IPsec in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdc33-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdc33-103">_**Argomento Ultima modifica:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="bdc33-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="bdc33-104">Per le reti aziendali in cui è stato distribuito Internet Protocol Security (IPsec) (Vedi IETF RFC 4301-4309), IPsec deve essere disabilitato tramite l'intervallo di porte usate per il recapito di audio, video e video panoramico.</span><span class="sxs-lookup"><span data-stu-id="bdc33-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="bdc33-105">La raccomandazione è motivata dalla necessità di evitare qualsiasi ritardo nell'allocazione delle porte multimediali a causa della negoziazione IPsec.</span><span class="sxs-lookup"><span data-stu-id="bdc33-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="bdc33-106">La tabella seguente illustra le impostazioni di eccezione IPsec consigliate.</span><span class="sxs-lookup"><span data-stu-id="bdc33-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="bdc33-107">Eccezioni IPsec consigliate</span><span class="sxs-lookup"><span data-stu-id="bdc33-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="bdc33-108">Nome regola</span><span class="sxs-lookup"><span data-stu-id="bdc33-108">Rule name</span></span></th>
<th><span data-ttu-id="bdc33-109">IP di origine</span><span class="sxs-lookup"><span data-stu-id="bdc33-109">Source IP</span></span></th>
<th><span data-ttu-id="bdc33-110">IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-110">Destination IP</span></span></th>
<th><span data-ttu-id="bdc33-111">Protocollo</span><span class="sxs-lookup"><span data-stu-id="bdc33-111">Protocol</span></span></th>
<th><span data-ttu-id="bdc33-112">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="bdc33-112">Source port</span></span></th>
<th><span data-ttu-id="bdc33-113">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-113">Destination port</span></span></th>
<th><span data-ttu-id="bdc33-114">Requisito di autenticazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdc33-115">A/V Edge Server Internal in ingresso</span><span class="sxs-lookup"><span data-stu-id="bdc33-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="bdc33-116">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-116">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-117">A/V Edge Server interno</span><span class="sxs-lookup"><span data-stu-id="bdc33-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="bdc33-118">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="bdc33-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bdc33-119">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-119">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-120">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-120">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-121">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc33-122">A/V Edge Server esterno in ingresso</span><span class="sxs-lookup"><span data-stu-id="bdc33-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="bdc33-123">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-123">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-124">A/V Edge Server esterno</span><span class="sxs-lookup"><span data-stu-id="bdc33-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="bdc33-125">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="bdc33-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bdc33-126">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-126">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-127">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-127">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-128">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc33-129">A/V Edge Server in uscita interna</span><span class="sxs-lookup"><span data-stu-id="bdc33-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="bdc33-130">A/V Edge Server interno</span><span class="sxs-lookup"><span data-stu-id="bdc33-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="bdc33-131">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-131">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-132">TCP &amp; UDP</span><span class="sxs-lookup"><span data-stu-id="bdc33-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="bdc33-133">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-133">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-134">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-134">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-135">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc33-136">A/V Edge Server in uscita esterna</span><span class="sxs-lookup"><span data-stu-id="bdc33-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="bdc33-137">A/V Edge Server esterno</span><span class="sxs-lookup"><span data-stu-id="bdc33-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="bdc33-138">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-138">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-139">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="bdc33-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bdc33-140">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-140">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-141">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-141">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-142">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc33-143">Mediation Server in ingresso</span><span class="sxs-lookup"><span data-stu-id="bdc33-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="bdc33-144">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-144">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-145">Pubblicitari</span><span class="sxs-lookup"><span data-stu-id="bdc33-145">Mediation</span></span></p>
<p><span data-ttu-id="bdc33-146">Server (s)</span><span class="sxs-lookup"><span data-stu-id="bdc33-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="bdc33-147">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="bdc33-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bdc33-148">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-148">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-149">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-149">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-150">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc33-151">Mediation Server in uscita</span><span class="sxs-lookup"><span data-stu-id="bdc33-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="bdc33-152">Pubblicitari</span><span class="sxs-lookup"><span data-stu-id="bdc33-152">Mediation</span></span></p>
<p><span data-ttu-id="bdc33-153">Server (s)</span><span class="sxs-lookup"><span data-stu-id="bdc33-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="bdc33-154">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-154">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-155">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="bdc33-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bdc33-156">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-156">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-157">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-157">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-158">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc33-159">Operatore di conferenza in ingresso</span><span class="sxs-lookup"><span data-stu-id="bdc33-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="bdc33-160">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-160">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-161">Server front-end con l'operatore di conferenza</span><span class="sxs-lookup"><span data-stu-id="bdc33-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="bdc33-162">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="bdc33-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bdc33-163">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-163">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-164">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-164">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-165">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc33-166">Operatore di conferenza in uscita</span><span class="sxs-lookup"><span data-stu-id="bdc33-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="bdc33-167">Server front-end con l'operatore di conferenza</span><span class="sxs-lookup"><span data-stu-id="bdc33-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="bdc33-168">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-168">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-169">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="bdc33-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bdc33-170">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-170">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-171">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-171">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-172">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc33-173">A/V Conferencing in ingresso</span><span class="sxs-lookup"><span data-stu-id="bdc33-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="bdc33-174">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-174">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-175">Server front-end</span><span class="sxs-lookup"><span data-stu-id="bdc33-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bdc33-176">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="bdc33-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bdc33-177">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-177">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-178">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-178">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-179">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc33-180">A/V Conferencing in uscita</span><span class="sxs-lookup"><span data-stu-id="bdc33-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="bdc33-181">Server front-end</span><span class="sxs-lookup"><span data-stu-id="bdc33-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bdc33-182">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-182">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-183">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="bdc33-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bdc33-184">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-184">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-185">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-185">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-186">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc33-187">Exchange in ingresso</span><span class="sxs-lookup"><span data-stu-id="bdc33-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="bdc33-188">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-188">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-189">Messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="bdc33-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="bdc33-190">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="bdc33-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bdc33-191">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-191">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-192">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-192">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-193">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc33-194">Server di condivisione applicazioni in ingresso</span><span class="sxs-lookup"><span data-stu-id="bdc33-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="bdc33-195">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-195">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-196">Server di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="bdc33-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="bdc33-197">TCP</span><span class="sxs-lookup"><span data-stu-id="bdc33-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="bdc33-198">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-198">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-199">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-199">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-200">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc33-201">Server di condivisione applicazioni in uscita</span><span class="sxs-lookup"><span data-stu-id="bdc33-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="bdc33-202">Server di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="bdc33-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="bdc33-203">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-203">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-204">TCP</span><span class="sxs-lookup"><span data-stu-id="bdc33-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="bdc33-205">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-205">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-206">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-206">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-207">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc33-208">Exchange in uscita</span><span class="sxs-lookup"><span data-stu-id="bdc33-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="bdc33-209">Messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="bdc33-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="bdc33-210">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-210">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-211">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="bdc33-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="bdc33-212">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-212">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-213">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-213">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-214">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc33-215">Client</span><span class="sxs-lookup"><span data-stu-id="bdc33-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="bdc33-216">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-216">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-217">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-217">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-218">UDP</span><span class="sxs-lookup"><span data-stu-id="bdc33-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="bdc33-219">Intervallo di porte multimediali specificato</span><span class="sxs-lookup"><span data-stu-id="bdc33-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="bdc33-220">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="bdc33-220">Any</span></span></p></td>
<td><p><span data-ttu-id="bdc33-221">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="bdc33-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

