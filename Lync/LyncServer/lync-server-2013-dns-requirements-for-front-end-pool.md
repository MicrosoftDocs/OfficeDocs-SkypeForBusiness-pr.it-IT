---
title: 'Lync Server 2013: requisiti DNS per il pool Front End'
description: 'Lync Server 2013: requisiti DNS per il pool Front end.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfce90eccb8c8dff94d4122c96c4ca68ea9150f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574332"
---
# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="fe576-103">Requisiti DNS per il pool Front end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe576-103">DNS requirements for Front End pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe576-104">_**Ultimo argomento modificato:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="fe576-104">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="fe576-105">Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio almeno come membro del gruppo Domain Admins o DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="fe576-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="fe576-106">È necessario configurare i record DNS (Domain Name System) necessari prima di pubblicare la topologia in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="fe576-106">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="fe576-107">Inoltre, alcuni dei nomi di dominio completi (FQDN) utilizzati per la configurazione di una distribuzione di Lync Server 2013 sono FQDN del server fisico e logico, pertanto è necessaria una configurazione DNS supplementare prima della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="fe576-107">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="fe576-108">Lync Server 2013 non supporta domini con etichetta singola.</span><span class="sxs-lookup"><span data-stu-id="fe576-108">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="fe576-109">Una foresta con un dominio radice denominato <STRONG>contoso.local</STRONG> ad esempio è supportata, ma un dominio radice denominato <STRONG>local</STRONG> non è supportato.</span><span class="sxs-lookup"><span data-stu-id="fe576-109">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="fe576-110">Per informazioni dettagliate, vedere l'articolo 300684 della Microsoft Knowledge Base "informazioni sulla configurazione di Windows per i domini con nomi DNS con etichetta singola," at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 300684</A>.</span><span class="sxs-lookup"><span data-stu-id="fe576-110">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fe576-111">Il nome specificato deve essere uguale al nome computer configurato nel server.</span><span class="sxs-lookup"><span data-stu-id="fe576-111">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="fe576-112">Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN.</span><span class="sxs-lookup"><span data-stu-id="fe576-112">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="fe576-113">Generatore di topologie utilizza gli FQDN e non i nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="fe576-113">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="fe576-114">Quando si assegnano FQDN dei server in cui sono in esecuzione Lync Server, server perimetrali e pool, <STRONG>utilizzare solo caratteri standard</STRONG> (tra cui a – z, a – z, 0 – 9 e segni meno).</span><span class="sxs-lookup"><span data-stu-id="fe576-114"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="fe576-115">Non usare i caratteri Unicode o i caratteri di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="fe576-115">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="fe576-116">I caratteri non standard di un FQDN spesso non sono supportati dalle autorità di certificazione (CA) pubbliche e DNS esterne (quando l'FQDN deve essere assegnato al nome soggetto nel certificato).</span><span class="sxs-lookup"><span data-stu-id="fe576-116">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="fe576-117">Prima di utilizzare la topologia dopo che è stata distribuita, verificare che siano stati creati i record DNS e Active Directory seguenti, in base alle esigenze per le caratteristiche specifiche:</span><span class="sxs-lookup"><span data-stu-id="fe576-117">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="fe576-118">Ogni ruolo del server che sarà presente nella topologia viene pubblicato come un oggetto Active Directory (l'aggiunta del computer al dominio lo otterrà).</span><span class="sxs-lookup"><span data-stu-id="fe576-118">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="fe576-119">Deve esistere un record A DNS per ogni server.</span><span class="sxs-lookup"><span data-stu-id="fe576-119">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="fe576-120">Un record SRV DNS esiste per ogni dominio SIP se si prevede di utilizzare l'accesso automatico per i client nel formato \_ sipinternaltls \_ TCP. \<SIP domain\> .</span><span class="sxs-lookup"><span data-stu-id="fe576-120">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="fe576-121">Se si userà la configurazione manuale per i client, questo record non è necessario.</span><span class="sxs-lookup"><span data-stu-id="fe576-121">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="fe576-122">Un record A DNS per ogni URL semplice configurato, di cui sono in genere quattro: Meet, dialin, LWA e Scheduler.</span><span class="sxs-lookup"><span data-stu-id="fe576-122">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="fe576-123">Inoltre, è disponibile l'URL semplice di amministrazione che è un URL speciale per accedere al pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe576-123">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="fe576-124">Il server che esegue SQL Server deve essere aggiunto al dominio e raggiungibile dal computer da cui viene eseguita la pubblicazione del generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="fe576-124">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="fe576-125">La tabella seguente è basata sulle architetture di riferimento presentate nella sezione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="fe576-125">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="fe576-126">Per ulteriori informazioni, vedere [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="fe576-126">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="fe576-127">Record DNS necessari per il pool Front End</span><span class="sxs-lookup"><span data-stu-id="fe576-127">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe576-128">Posizione</span><span class="sxs-lookup"><span data-stu-id="fe576-128">Location</span></span></th>
<th><span data-ttu-id="fe576-129">Tipo</span><span class="sxs-lookup"><span data-stu-id="fe576-129">Type</span></span></th>
<th><span data-ttu-id="fe576-130">FQDN</span><span class="sxs-lookup"><span data-stu-id="fe576-130">FQDN</span></span></th>
<th><span data-ttu-id="fe576-131">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="fe576-131">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe576-132">DNS interno</span><span class="sxs-lookup"><span data-stu-id="fe576-132">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="fe576-133">A</span><span class="sxs-lookup"><span data-stu-id="fe576-133">A</span></span></p></td>
<td><p><span data-ttu-id="fe576-134">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fe576-134">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="fe576-135">Pool01 (bilanciamento del carico DNS).</span><span class="sxs-lookup"><span data-stu-id="fe576-135">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="fe576-136">Richiede un record a DNS per l'indirizzo IP di ogni Front End Server all'interno del pool, eseguendo il mapping all'FQDN del pool.</span><span class="sxs-lookup"><span data-stu-id="fe576-136">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe576-137">DNS interno</span><span class="sxs-lookup"><span data-stu-id="fe576-137">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="fe576-138">A</span><span class="sxs-lookup"><span data-stu-id="fe576-138">A</span></span></p></td>
<td><p><span data-ttu-id="fe576-139">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fe576-139">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="fe576-140">Pool01 (IP virtuale (VIP) del dispositivo di bilanciamento del carico hardware).</span><span class="sxs-lookup"><span data-stu-id="fe576-140">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe576-141">DNS interno</span><span class="sxs-lookup"><span data-stu-id="fe576-141">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="fe576-142">A</span><span class="sxs-lookup"><span data-stu-id="fe576-142">A</span></span></p></td>
<td><p><span data-ttu-id="fe576-143">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fe576-143">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="fe576-144">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fe576-144">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="fe576-145">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fe576-145">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="fe576-146">…</span><span class="sxs-lookup"><span data-stu-id="fe576-146">…</span></span></p></td>
<td><p><span data-ttu-id="fe576-147">Pool01 Front End Server (nodo 1).</span><span class="sxs-lookup"><span data-stu-id="fe576-147">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="fe576-148">Pool01 Front End Server (nodo 2).</span><span class="sxs-lookup"><span data-stu-id="fe576-148">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="fe576-149">Pool01 Front End Server (nodo 3).</span><span class="sxs-lookup"><span data-stu-id="fe576-149">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="fe576-150">…</span><span class="sxs-lookup"><span data-stu-id="fe576-150">…</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe576-151">DNS interno</span><span class="sxs-lookup"><span data-stu-id="fe576-151">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="fe576-152">A</span><span class="sxs-lookup"><span data-stu-id="fe576-152">A</span></span></p></td>
<td><p><span data-ttu-id="fe576-153">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fe576-153">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="fe576-154">Pool01 Front End Server (nodo 2).</span><span class="sxs-lookup"><span data-stu-id="fe576-154">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe576-155">DNS interno</span><span class="sxs-lookup"><span data-stu-id="fe576-155">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="fe576-156">A</span><span class="sxs-lookup"><span data-stu-id="fe576-156">A</span></span></p></td>
<td><p><span data-ttu-id="fe576-157">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fe576-157">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="fe576-158">Pool01 (VIP) per traffico Web da client a server.</span><span class="sxs-lookup"><span data-stu-id="fe576-158">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe576-159">DNS interno</span><span class="sxs-lookup"><span data-stu-id="fe576-159">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="fe576-160">A</span><span class="sxs-lookup"><span data-stu-id="fe576-160">A</span></span></p></td>
<td><p><span data-ttu-id="fe576-161">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fe576-161">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="fe576-162">Pool01 back-end server che esegue SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="fe576-162">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe576-163">DNS interno</span><span class="sxs-lookup"><span data-stu-id="fe576-163">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="fe576-164">A</span><span class="sxs-lookup"><span data-stu-id="fe576-164">A</span></span></p></td>
<td><p><span data-ttu-id="fe576-165">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fe576-165">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fe576-166">Obbligatorio per Lync Phone Edition o per l'accesso automatico dei client senza record DNS SRV e per una corrispondenza di dominio rigorosa.</span><span class="sxs-lookup"><span data-stu-id="fe576-166">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="fe576-167">Non necessario in tutti i casi.</span><span class="sxs-lookup"><span data-stu-id="fe576-167">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe576-168">DNS interno</span><span class="sxs-lookup"><span data-stu-id="fe576-168">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="fe576-169">A</span><span class="sxs-lookup"><span data-stu-id="fe576-169">A</span></span></p></td>
<td><p><span data-ttu-id="fe576-170">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fe576-170">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="fe576-171">Presuppone un secondo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="fe576-171">Assumes a second SIP domain.</span></span> <span data-ttu-id="fe576-172">Obbligatorio per Lync Phone Edition, accesso automatico dei client senza record DNS SRV e per una corrispondenza di dominio rigorosa.</span><span class="sxs-lookup"><span data-stu-id="fe576-172">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="fe576-173">Non necessario in tutti i casi.</span><span class="sxs-lookup"><span data-stu-id="fe576-173">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe576-174">DNS interno</span><span class="sxs-lookup"><span data-stu-id="fe576-174">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="fe576-175">A</span><span class="sxs-lookup"><span data-stu-id="fe576-175">A</span></span></p></td>
<td><p><span data-ttu-id="fe576-176">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fe576-176">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fe576-177">URL semplice per le conferenze telefoniche con accesso esterno pubblicate internamente: Front End Server (o Director, se installato) risponde a query URL semplici.</span><span class="sxs-lookup"><span data-stu-id="fe576-177">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe576-178">DNS interno</span><span class="sxs-lookup"><span data-stu-id="fe576-178">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="fe576-179">A</span><span class="sxs-lookup"><span data-stu-id="fe576-179">A</span></span></p></td>
<td><p><span data-ttu-id="fe576-180">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fe576-180">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fe576-181">URL semplice per le conferenze pubblicate internamente: Front End Server (o Director, se installato) risponde a query URL semplici.</span><span class="sxs-lookup"><span data-stu-id="fe576-181">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe576-182">DNS interno</span><span class="sxs-lookup"><span data-stu-id="fe576-182">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="fe576-183">A</span><span class="sxs-lookup"><span data-stu-id="fe576-183">A</span></span></p></td>
<td><p><span data-ttu-id="fe576-184">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fe576-184">admin.contoso.com</span></span></p>
<p><span data-ttu-id="fe576-185">interfaccia amministrazione</span><span class="sxs-lookup"><span data-stu-id="fe576-185">admin</span></span></p></td>
<td><p><span data-ttu-id="fe576-186">Record facoltativo, URL semplice per il pannello di controllo di Lync Server 2013 pubblicato internamente-Front End Server (o Director, se installato) risponde a query URL semplici.</span><span class="sxs-lookup"><span data-stu-id="fe576-186">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="fe576-187">È consigliabile utilizzare solo il nome host (nessun nome di dominio).</span><span class="sxs-lookup"><span data-stu-id="fe576-187">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="fe576-188">VIP = indirizzo IP virtuale per il dispositivo di bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="fe576-188">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="fe576-189">Record SRV DNS per il pool Front End</span><span class="sxs-lookup"><span data-stu-id="fe576-189">DNS SRV Records for the Front End pool</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe576-190">Posizione</span><span class="sxs-lookup"><span data-stu-id="fe576-190">Location</span></span></th>
<th><span data-ttu-id="fe576-191">Tipo</span><span class="sxs-lookup"><span data-stu-id="fe576-191">Type</span></span></th>
<th><span data-ttu-id="fe576-192">FQDN</span><span class="sxs-lookup"><span data-stu-id="fe576-192">FQDN</span></span></th>
<th><span data-ttu-id="fe576-193">FQDN di destinazione</span><span class="sxs-lookup"><span data-stu-id="fe576-193">Target FQDN</span></span></th>
<th><span data-ttu-id="fe576-194">Porta</span><span class="sxs-lookup"><span data-stu-id="fe576-194">Port</span></span></th>
<th><span data-ttu-id="fe576-195">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="fe576-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe576-196">DNS interno</span><span class="sxs-lookup"><span data-stu-id="fe576-196">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="fe576-197">SRV</span><span class="sxs-lookup"><span data-stu-id="fe576-197">SRV</span></span></p></td>
<td><p><span data-ttu-id="fe576-198">_sipinternaltls _sipinternaltls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="fe576-198">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fe576-199">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fe576-199">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fe576-200">5061</span><span class="sxs-lookup"><span data-stu-id="fe576-200">5061</span></span></p></td>
<td><p><span data-ttu-id="fe576-201">Necessario per la configurazione automatica dei client di Lync 2013 per l'utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="fe576-201">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe576-202">DNS interno</span><span class="sxs-lookup"><span data-stu-id="fe576-202">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="fe576-203">SRV</span><span class="sxs-lookup"><span data-stu-id="fe576-203">SRV</span></span></p></td>
<td><p><span data-ttu-id="fe576-204">_sipinternaltls _sipinternaltls._tcp. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="fe576-204">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="fe576-205">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fe576-205">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="fe576-206">5061</span><span class="sxs-lookup"><span data-stu-id="fe576-206">5061</span></span></p></td>
<td><p><span data-ttu-id="fe576-207">Necessario per la configurazione automatica dei client di Lync 2013 per l'utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="fe576-207">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe576-208">DNS interno</span><span class="sxs-lookup"><span data-stu-id="fe576-208">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="fe576-209">SRV</span><span class="sxs-lookup"><span data-stu-id="fe576-209">SRV</span></span></p></td>
<td><p><span data-ttu-id="fe576-210">_ntp _ntp._udp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="fe576-210">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fe576-211">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fe576-211">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fe576-212">123</span><span class="sxs-lookup"><span data-stu-id="fe576-212">123</span></span></p></td>
<td><p><span data-ttu-id="fe576-213">Origine di protocollo Network Time Protocol (NTP) necessaria per i dispositivi che eseguono Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="fe576-213">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="fe576-214">Internamente deve puntare al controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="fe576-214">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="fe576-215">Se quest'ultimo non è definito, tenterà di usare il server NTP time.windows.com.</span><span class="sxs-lookup"><span data-stu-id="fe576-215">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

