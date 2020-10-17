---
title: 'Lync Server 2013: requisiti DNS per il pool Front End'
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
ms.openlocfilehash: eff0ab4c6ee2f6582c8274345c15af681d242561
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532173"
---
# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="00130-102">Requisiti DNS per il pool Front end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00130-102">DNS requirements for Front End pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00130-103">_**Ultimo argomento modificato:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="00130-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="00130-104">Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio almeno come membro del gruppo Domain Admins o DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="00130-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="00130-105">È necessario configurare i record DNS (Domain Name System) necessari prima di pubblicare la topologia in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="00130-105">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="00130-106">Inoltre, alcuni dei nomi di dominio completi (FQDN) utilizzati per la configurazione di una distribuzione di Lync Server 2013 sono FQDN del server fisico e logico, pertanto è necessaria una configurazione DNS supplementare prima della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="00130-106">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="00130-107">Lync Server 2013 non supporta domini con etichetta singola.</span><span class="sxs-lookup"><span data-stu-id="00130-107">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="00130-108">Una foresta con un dominio radice denominato <STRONG>contoso.local</STRONG> ad esempio è supportata, ma un dominio radice denominato <STRONG>local</STRONG> non è supportato.</span><span class="sxs-lookup"><span data-stu-id="00130-108">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="00130-109">Per informazioni dettagliate, vedere l'articolo 300684 della Microsoft Knowledge Base "informazioni sulla configurazione di Windows per i domini con nomi DNS con etichetta singola," at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 300684</A>.</span><span class="sxs-lookup"><span data-stu-id="00130-109">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="00130-110">Il nome specificato deve essere uguale al nome computer configurato nel server.</span><span class="sxs-lookup"><span data-stu-id="00130-110">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="00130-111">Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN.</span><span class="sxs-lookup"><span data-stu-id="00130-111">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="00130-112">Generatore di topologie utilizza gli FQDN e non i nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="00130-112">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="00130-113">Quando si assegnano FQDN dei server in cui sono in esecuzione Lync Server, server perimetrali e pool, <STRONG>utilizzare solo caratteri standard</STRONG> (tra cui a – z, a – z, 0 – 9 e segni meno).</span><span class="sxs-lookup"><span data-stu-id="00130-113"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="00130-114">Non usare i caratteri Unicode o i caratteri di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="00130-114">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="00130-115">I caratteri non standard di un FQDN spesso non sono supportati dalle autorità di certificazione (CA) pubbliche e DNS esterne (quando l'FQDN deve essere assegnato al nome soggetto nel certificato).</span><span class="sxs-lookup"><span data-stu-id="00130-115">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="00130-116">Prima di utilizzare la topologia dopo che è stata distribuita, verificare che siano stati creati i record DNS e Active Directory seguenti, in base alle esigenze per le caratteristiche specifiche:</span><span class="sxs-lookup"><span data-stu-id="00130-116">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="00130-117">Ogni ruolo del server che sarà presente nella topologia viene pubblicato come un oggetto Active Directory (l'aggiunta del computer al dominio lo otterrà).</span><span class="sxs-lookup"><span data-stu-id="00130-117">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="00130-118">Deve esistere un record A DNS per ogni server.</span><span class="sxs-lookup"><span data-stu-id="00130-118">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="00130-119">Un record SRV DNS esiste per ogni dominio SIP se si prevede di utilizzare l'accesso automatico per i client nel formato \_ sipinternaltls \_ TCP. \<SIP domain\> .</span><span class="sxs-lookup"><span data-stu-id="00130-119">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="00130-120">Se si userà la configurazione manuale per i client, questo record non è necessario.</span><span class="sxs-lookup"><span data-stu-id="00130-120">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="00130-121">Un record A DNS per ogni URL semplice configurato, di cui sono in genere quattro: Meet, dialin, LWA e Scheduler.</span><span class="sxs-lookup"><span data-stu-id="00130-121">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="00130-122">Inoltre, è disponibile l'URL semplice di amministrazione che è un URL speciale per accedere al pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00130-122">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="00130-123">Il server che esegue SQL Server deve essere aggiunto al dominio e raggiungibile dal computer da cui viene eseguita la pubblicazione del generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="00130-123">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="00130-124">La tabella seguente è basata sulle architetture di riferimento presentate nella sezione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="00130-124">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="00130-125">Per ulteriori informazioni, vedere [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="00130-125">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="00130-126">Record DNS necessari per il pool Front End</span><span class="sxs-lookup"><span data-stu-id="00130-126">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00130-127">Posizione</span><span class="sxs-lookup"><span data-stu-id="00130-127">Location</span></span></th>
<th><span data-ttu-id="00130-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="00130-128">Type</span></span></th>
<th><span data-ttu-id="00130-129">FQDN</span><span class="sxs-lookup"><span data-stu-id="00130-129">FQDN</span></span></th>
<th><span data-ttu-id="00130-130">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="00130-130">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00130-131">DNS interno</span><span class="sxs-lookup"><span data-stu-id="00130-131">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="00130-132">A</span><span class="sxs-lookup"><span data-stu-id="00130-132">A</span></span></p></td>
<td><p><span data-ttu-id="00130-133">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="00130-133">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="00130-134">Pool01 (bilanciamento del carico DNS).</span><span class="sxs-lookup"><span data-stu-id="00130-134">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="00130-135">Richiede un record a DNS per l'indirizzo IP di ogni Front End Server all'interno del pool, eseguendo il mapping all'FQDN del pool.</span><span class="sxs-lookup"><span data-stu-id="00130-135">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00130-136">DNS interno</span><span class="sxs-lookup"><span data-stu-id="00130-136">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="00130-137">A</span><span class="sxs-lookup"><span data-stu-id="00130-137">A</span></span></p></td>
<td><p><span data-ttu-id="00130-138">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="00130-138">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="00130-139">Pool01 (IP virtuale (VIP) del dispositivo di bilanciamento del carico hardware).</span><span class="sxs-lookup"><span data-stu-id="00130-139">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00130-140">DNS interno</span><span class="sxs-lookup"><span data-stu-id="00130-140">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="00130-141">A</span><span class="sxs-lookup"><span data-stu-id="00130-141">A</span></span></p></td>
<td><p><span data-ttu-id="00130-142">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="00130-142">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="00130-143">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="00130-143">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="00130-144">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="00130-144">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="00130-145">…</span><span class="sxs-lookup"><span data-stu-id="00130-145">…</span></span></p></td>
<td><p><span data-ttu-id="00130-146">Pool01 Front End Server (nodo 1).</span><span class="sxs-lookup"><span data-stu-id="00130-146">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="00130-147">Pool01 Front End Server (nodo 2).</span><span class="sxs-lookup"><span data-stu-id="00130-147">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="00130-148">Pool01 Front End Server (nodo 3).</span><span class="sxs-lookup"><span data-stu-id="00130-148">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="00130-149">…</span><span class="sxs-lookup"><span data-stu-id="00130-149">…</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00130-150">DNS interno</span><span class="sxs-lookup"><span data-stu-id="00130-150">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="00130-151">A</span><span class="sxs-lookup"><span data-stu-id="00130-151">A</span></span></p></td>
<td><p><span data-ttu-id="00130-152">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="00130-152">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="00130-153">Pool01 Front End Server (nodo 2).</span><span class="sxs-lookup"><span data-stu-id="00130-153">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00130-154">DNS interno</span><span class="sxs-lookup"><span data-stu-id="00130-154">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="00130-155">A</span><span class="sxs-lookup"><span data-stu-id="00130-155">A</span></span></p></td>
<td><p><span data-ttu-id="00130-156">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="00130-156">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="00130-157">Pool01 (VIP) per traffico Web da client a server.</span><span class="sxs-lookup"><span data-stu-id="00130-157">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00130-158">DNS interno</span><span class="sxs-lookup"><span data-stu-id="00130-158">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="00130-159">A</span><span class="sxs-lookup"><span data-stu-id="00130-159">A</span></span></p></td>
<td><p><span data-ttu-id="00130-160">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="00130-160">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="00130-161">Pool01 back-end server che esegue SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="00130-161">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00130-162">DNS interno</span><span class="sxs-lookup"><span data-stu-id="00130-162">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="00130-163">A</span><span class="sxs-lookup"><span data-stu-id="00130-163">A</span></span></p></td>
<td><p><span data-ttu-id="00130-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="00130-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="00130-165">Obbligatorio per Lync Phone Edition o per l'accesso automatico dei client senza record DNS SRV e per una corrispondenza di dominio rigorosa.</span><span class="sxs-lookup"><span data-stu-id="00130-165">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="00130-166">Non necessario in tutti i casi.</span><span class="sxs-lookup"><span data-stu-id="00130-166">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00130-167">DNS interno</span><span class="sxs-lookup"><span data-stu-id="00130-167">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="00130-168">A</span><span class="sxs-lookup"><span data-stu-id="00130-168">A</span></span></p></td>
<td><p><span data-ttu-id="00130-169">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="00130-169">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="00130-170">Presuppone un secondo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="00130-170">Assumes a second SIP domain.</span></span> <span data-ttu-id="00130-171">Obbligatorio per Lync Phone Edition, accesso automatico dei client senza record DNS SRV e per una corrispondenza di dominio rigorosa.</span><span class="sxs-lookup"><span data-stu-id="00130-171">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="00130-172">Non necessario in tutti i casi.</span><span class="sxs-lookup"><span data-stu-id="00130-172">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00130-173">DNS interno</span><span class="sxs-lookup"><span data-stu-id="00130-173">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="00130-174">A</span><span class="sxs-lookup"><span data-stu-id="00130-174">A</span></span></p></td>
<td><p><span data-ttu-id="00130-175">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="00130-175">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="00130-176">URL semplice per le conferenze telefoniche con accesso esterno pubblicate internamente: Front End Server (o Director, se installato) risponde a query URL semplici.</span><span class="sxs-lookup"><span data-stu-id="00130-176">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00130-177">DNS interno</span><span class="sxs-lookup"><span data-stu-id="00130-177">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="00130-178">A</span><span class="sxs-lookup"><span data-stu-id="00130-178">A</span></span></p></td>
<td><p><span data-ttu-id="00130-179">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="00130-179">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="00130-180">URL semplice per le conferenze pubblicate internamente: Front End Server (o Director, se installato) risponde a query URL semplici.</span><span class="sxs-lookup"><span data-stu-id="00130-180">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00130-181">DNS interno</span><span class="sxs-lookup"><span data-stu-id="00130-181">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="00130-182">A</span><span class="sxs-lookup"><span data-stu-id="00130-182">A</span></span></p></td>
<td><p><span data-ttu-id="00130-183">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="00130-183">admin.contoso.com</span></span></p>
<p><span data-ttu-id="00130-184">interfaccia amministrazione</span><span class="sxs-lookup"><span data-stu-id="00130-184">admin</span></span></p></td>
<td><p><span data-ttu-id="00130-185">Record facoltativo, URL semplice per il pannello di controllo di Lync Server 2013 pubblicato internamente-Front End Server (o Director, se installato) risponde a query URL semplici.</span><span class="sxs-lookup"><span data-stu-id="00130-185">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="00130-186">È consigliabile utilizzare solo il nome host (nessun nome di dominio).</span><span class="sxs-lookup"><span data-stu-id="00130-186">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="00130-187">VIP = indirizzo IP virtuale per il dispositivo di bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="00130-187">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="00130-188">Record SRV DNS per il pool Front End</span><span class="sxs-lookup"><span data-stu-id="00130-188">DNS SRV Records for the Front End pool</span></span>


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
<th><span data-ttu-id="00130-189">Posizione</span><span class="sxs-lookup"><span data-stu-id="00130-189">Location</span></span></th>
<th><span data-ttu-id="00130-190">Tipo</span><span class="sxs-lookup"><span data-stu-id="00130-190">Type</span></span></th>
<th><span data-ttu-id="00130-191">FQDN</span><span class="sxs-lookup"><span data-stu-id="00130-191">FQDN</span></span></th>
<th><span data-ttu-id="00130-192">FQDN di destinazione</span><span class="sxs-lookup"><span data-stu-id="00130-192">Target FQDN</span></span></th>
<th><span data-ttu-id="00130-193">Porta</span><span class="sxs-lookup"><span data-stu-id="00130-193">Port</span></span></th>
<th><span data-ttu-id="00130-194">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="00130-194">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00130-195">DNS interno</span><span class="sxs-lookup"><span data-stu-id="00130-195">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="00130-196">SRV</span><span class="sxs-lookup"><span data-stu-id="00130-196">SRV</span></span></p></td>
<td><p><span data-ttu-id="00130-197">_sipinternaltls _sipinternaltls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="00130-197">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="00130-198">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="00130-198">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="00130-199">5061</span><span class="sxs-lookup"><span data-stu-id="00130-199">5061</span></span></p></td>
<td><p><span data-ttu-id="00130-200">Necessario per la configurazione automatica dei client di Lync 2013 per l'utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="00130-200">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00130-201">DNS interno</span><span class="sxs-lookup"><span data-stu-id="00130-201">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="00130-202">SRV</span><span class="sxs-lookup"><span data-stu-id="00130-202">SRV</span></span></p></td>
<td><p><span data-ttu-id="00130-203">_sipinternaltls _sipinternaltls._tcp. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="00130-203">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="00130-204">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="00130-204">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="00130-205">5061</span><span class="sxs-lookup"><span data-stu-id="00130-205">5061</span></span></p></td>
<td><p><span data-ttu-id="00130-206">Necessario per la configurazione automatica dei client di Lync 2013 per l'utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="00130-206">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00130-207">DNS interno</span><span class="sxs-lookup"><span data-stu-id="00130-207">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="00130-208">SRV</span><span class="sxs-lookup"><span data-stu-id="00130-208">SRV</span></span></p></td>
<td><p><span data-ttu-id="00130-209">_ntp _ntp._udp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="00130-209">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="00130-210">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="00130-210">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="00130-211">123</span><span class="sxs-lookup"><span data-stu-id="00130-211">123</span></span></p></td>
<td><p><span data-ttu-id="00130-212">Origine di protocollo Network Time Protocol (NTP) necessaria per i dispositivi che eseguono Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="00130-212">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="00130-213">Internamente deve puntare al controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="00130-213">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="00130-214">Se quest'ultimo non è definito, tenterà di usare il server NTP time.windows.com.</span><span class="sxs-lookup"><span data-stu-id="00130-214">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

