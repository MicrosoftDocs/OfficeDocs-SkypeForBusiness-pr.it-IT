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
ms.openlocfilehash: 37d5becaab996d6fe4889086d3a68a45ffc1f6d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="07c4b-102">Eccezioni IPsec in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07c4b-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07c4b-103">_**Argomento Ultima modifica:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="07c4b-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="07c4b-104">Per le reti aziendali in cui è stato distribuito Internet Protocol Security (IPsec) (Vedi IETF RFC 4301-4309), IPsec deve essere disabilitato tramite l'intervallo di porte usate per il recapito di audio, video e video panoramico.</span><span class="sxs-lookup"><span data-stu-id="07c4b-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="07c4b-105">La raccomandazione è motivata dalla necessità di evitare qualsiasi ritardo nell'allocazione delle porte multimediali a causa della negoziazione IPsec.</span><span class="sxs-lookup"><span data-stu-id="07c4b-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="07c4b-106">La tabella seguente illustra le impostazioni di eccezione IPsec consigliate.</span><span class="sxs-lookup"><span data-stu-id="07c4b-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="07c4b-107">Eccezioni IPsec consigliate</span><span class="sxs-lookup"><span data-stu-id="07c4b-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="07c4b-108">Nome regola</span><span class="sxs-lookup"><span data-stu-id="07c4b-108">Rule name</span></span></th>
<th><span data-ttu-id="07c4b-109">IP di origine</span><span class="sxs-lookup"><span data-stu-id="07c4b-109">Source IP</span></span></th>
<th><span data-ttu-id="07c4b-110">IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-110">Destination IP</span></span></th>
<th><span data-ttu-id="07c4b-111">Protocollo</span><span class="sxs-lookup"><span data-stu-id="07c4b-111">Protocol</span></span></th>
<th><span data-ttu-id="07c4b-112">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="07c4b-112">Source port</span></span></th>
<th><span data-ttu-id="07c4b-113">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-113">Destination port</span></span></th>
<th><span data-ttu-id="07c4b-114">Requisito di autenticazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07c4b-115">A/V Edge Server Internal in ingresso</span><span class="sxs-lookup"><span data-stu-id="07c4b-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="07c4b-116">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-116">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-117">A/V Edge Server interno</span><span class="sxs-lookup"><span data-stu-id="07c4b-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="07c4b-118">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="07c4b-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="07c4b-119">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-119">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-120">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-120">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-121">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4b-122">A/V Edge Server esterno in ingresso</span><span class="sxs-lookup"><span data-stu-id="07c4b-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="07c4b-123">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-123">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-124">A/V Edge Server esterno</span><span class="sxs-lookup"><span data-stu-id="07c4b-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="07c4b-125">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="07c4b-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="07c4b-126">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-126">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-127">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-127">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-128">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4b-129">A/V Edge Server in uscita interna</span><span class="sxs-lookup"><span data-stu-id="07c4b-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="07c4b-130">A/V Edge Server interno</span><span class="sxs-lookup"><span data-stu-id="07c4b-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="07c4b-131">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-131">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-132">TCP &amp; UDP</span><span class="sxs-lookup"><span data-stu-id="07c4b-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="07c4b-133">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-133">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-134">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-134">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-135">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4b-136">A/V Edge Server in uscita esterna</span><span class="sxs-lookup"><span data-stu-id="07c4b-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="07c4b-137">A/V Edge Server esterno</span><span class="sxs-lookup"><span data-stu-id="07c4b-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="07c4b-138">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-138">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-139">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="07c4b-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="07c4b-140">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-140">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-141">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-141">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-142">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4b-143">Mediation Server in ingresso</span><span class="sxs-lookup"><span data-stu-id="07c4b-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="07c4b-144">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-144">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-145">Pubblicitari</span><span class="sxs-lookup"><span data-stu-id="07c4b-145">Mediation</span></span></p>
<p><span data-ttu-id="07c4b-146">Server (s)</span><span class="sxs-lookup"><span data-stu-id="07c4b-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="07c4b-147">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="07c4b-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="07c4b-148">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-148">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-149">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-149">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-150">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4b-151">Mediation Server in uscita</span><span class="sxs-lookup"><span data-stu-id="07c4b-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="07c4b-152">Pubblicitari</span><span class="sxs-lookup"><span data-stu-id="07c4b-152">Mediation</span></span></p>
<p><span data-ttu-id="07c4b-153">Server (s)</span><span class="sxs-lookup"><span data-stu-id="07c4b-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="07c4b-154">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-154">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-155">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="07c4b-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="07c4b-156">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-156">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-157">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-157">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-158">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4b-159">Operatore di conferenza in ingresso</span><span class="sxs-lookup"><span data-stu-id="07c4b-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="07c4b-160">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-160">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-161">Server front-end con l'operatore di conferenza</span><span class="sxs-lookup"><span data-stu-id="07c4b-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="07c4b-162">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="07c4b-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="07c4b-163">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-163">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-164">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-164">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-165">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4b-166">Operatore di conferenza in uscita</span><span class="sxs-lookup"><span data-stu-id="07c4b-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="07c4b-167">Server front-end con l'operatore di conferenza</span><span class="sxs-lookup"><span data-stu-id="07c4b-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="07c4b-168">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-168">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-169">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="07c4b-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="07c4b-170">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-170">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-171">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-171">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-172">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4b-173">A/V Conferencing in ingresso</span><span class="sxs-lookup"><span data-stu-id="07c4b-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="07c4b-174">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-174">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-175">Server front-end</span><span class="sxs-lookup"><span data-stu-id="07c4b-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="07c4b-176">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="07c4b-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="07c4b-177">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-177">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-178">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-178">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-179">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4b-180">A/V Conferencing in uscita</span><span class="sxs-lookup"><span data-stu-id="07c4b-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="07c4b-181">Server front-end</span><span class="sxs-lookup"><span data-stu-id="07c4b-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="07c4b-182">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-182">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-183">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="07c4b-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="07c4b-184">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-184">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-185">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-185">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-186">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4b-187">Exchange in ingresso</span><span class="sxs-lookup"><span data-stu-id="07c4b-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="07c4b-188">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-188">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-189">Messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="07c4b-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="07c4b-190">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="07c4b-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="07c4b-191">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-191">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-192">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-192">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-193">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4b-194">Server di condivisione applicazioni in ingresso</span><span class="sxs-lookup"><span data-stu-id="07c4b-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="07c4b-195">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-195">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-196">Server di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="07c4b-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="07c4b-197">TCP</span><span class="sxs-lookup"><span data-stu-id="07c4b-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="07c4b-198">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-198">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-199">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-199">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-200">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4b-201">Server di condivisione applicazioni in uscita</span><span class="sxs-lookup"><span data-stu-id="07c4b-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="07c4b-202">Server di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="07c4b-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="07c4b-203">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-203">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-204">TCP</span><span class="sxs-lookup"><span data-stu-id="07c4b-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="07c4b-205">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-205">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-206">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-206">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-207">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4b-208">Exchange in uscita</span><span class="sxs-lookup"><span data-stu-id="07c4b-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="07c4b-209">Messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="07c4b-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="07c4b-210">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-210">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-211">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="07c4b-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="07c4b-212">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-212">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-213">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-213">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-214">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4b-215">Client</span><span class="sxs-lookup"><span data-stu-id="07c4b-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="07c4b-216">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-216">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-217">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-217">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-218">UDP</span><span class="sxs-lookup"><span data-stu-id="07c4b-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="07c4b-219">Intervallo di porte multimediali specificato</span><span class="sxs-lookup"><span data-stu-id="07c4b-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="07c4b-220">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="07c4b-220">Any</span></span></p></td>
<td><p><span data-ttu-id="07c4b-221">Non eseguire l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="07c4b-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

