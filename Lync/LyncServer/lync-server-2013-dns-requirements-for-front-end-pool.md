---
title: 'Lync Server 2013: Requisiti di DNS per il pool Front End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c033d8f1a4167e423d5663b0c9b0b7dbfb2d760
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="a3f4a-102">Requisiti di DNS per il pool Front End in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3f4a-102">DNS requirements for Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3f4a-103">_**Argomento Ultima modifica:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="a3f4a-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="a3f4a-104">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="a3f4a-105">È necessario configurare i record DNS (Domain Name System) necessari prima di pubblicare la topologia in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-105">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="a3f4a-106">Inoltre, alcuni dei nomi di dominio completi (FQDN) usati nella configurazione di una distribuzione di Lync Server 2013 sono FQDN dei server logici e non fisici, quindi è necessaria una configurazione DNS aggiuntiva prima della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-106">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="a3f4a-107">Lync Server 2013 non supporta i domini con etichetta singola.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-107">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="a3f4a-108">Ad esempio, è supportata una foresta con un dominio radice denominato <STRONG>contoso. local</STRONG> , ma un dominio radice denominato <STRONG>local</STRONG> non è supportato.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-108">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="a3f4a-109">Per informazioni dettagliate, vedere l'articolo 300684 della Microsoft Knowledge Base "informazioni sulla configurazione di Windows per i domini con nomi DNS con etichetta singola," at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-109">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a3f4a-110">Il nome specificato deve essere uguale al nome del computer configurato nel server.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-110">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="a3f4a-111">Per impostazione predefinita, il nome del computer di un computer che non è associato a un dominio è un nome breve, non un FQDN.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-111">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="a3f4a-112">Generatore di topologie usa gli FQDN e non i nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-112">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a3f4a-113"><STRONG>Usare solo caratteri standard</STRONG> (tra cui a-z, a-z, 0-9 e segni meno) durante l'assegnazione di nomi di dominio completi dei server che usano Lync Server, Edge Server e pool.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-113"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="a3f4a-114">Non usare caratteri Unicode o carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-114">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="a3f4a-115">I caratteri non standard di un nome di dominio completo spesso non sono supportati dalle autorità di certificazione pubbliche e DNS esterne (CAs) (quando il nome di dominio completo deve essere assegnato a SN nel certificato).</span><span class="sxs-lookup"><span data-stu-id="a3f4a-115">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="a3f4a-116">Prima di utilizzare la topologia dopo la distribuzione, verificare che vengano creati i seguenti record DNS e Active Directory (in base alle esigenze delle caratteristiche specifiche):</span><span class="sxs-lookup"><span data-stu-id="a3f4a-116">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="a3f4a-117">Ogni ruolo del server che esisterà nella topologia viene pubblicato come oggetto Active Directory (l'aggiunta del computer al dominio verrà realizzata).</span><span class="sxs-lookup"><span data-stu-id="a3f4a-117">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="a3f4a-118">Un record DNS esiste per ogni server.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-118">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="a3f4a-119">Un record SRV DNS esiste per ogni dominio SIP se si prevede di usare l'accesso automatico per i client in forma \_di\_sipinternaltls TCP. \<Dominio\>SIP.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-119">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="a3f4a-120">Se si utilizzerà la configurazione manuale per i client, questo record non è necessario.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-120">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="a3f4a-121">Un record DNS per ogni URL semplice configurato, di cui ci sono in genere quattro: Meet, dialin, LWA e Scheduler.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-121">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="a3f4a-122">Inoltre, c'è l'URL semplice amministratore che è un URL speciale per l'accesso al pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-122">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="a3f4a-123">Il server in cui è in uso SQL Server deve essere unito al dominio e raggiungibile dal computer a cui viene eseguita la pubblicazione di generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-123">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="a3f4a-124">La tabella segue le architetture di riferimento presentate nella sezione pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-124">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="a3f4a-125">Per informazioni dettagliate, vedere [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-125">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="a3f4a-126">Record DNS necessari per il pool Front-End</span><span class="sxs-lookup"><span data-stu-id="a3f4a-126">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3f4a-127">Posizione</span><span class="sxs-lookup"><span data-stu-id="a3f4a-127">Location</span></span></th>
<th><span data-ttu-id="a3f4a-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="a3f4a-128">Type</span></span></th>
<th><span data-ttu-id="a3f4a-129">FQDN</span><span class="sxs-lookup"><span data-stu-id="a3f4a-129">FQDN</span></span></th>
<th><span data-ttu-id="a3f4a-130">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="a3f4a-130">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3f4a-131">DNS interno</span><span class="sxs-lookup"><span data-stu-id="a3f4a-131">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-132">A</span><span class="sxs-lookup"><span data-stu-id="a3f4a-132">A</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-133">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a3f4a-133">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-134">Pool01 (bilanciamento del carico DNS).</span><span class="sxs-lookup"><span data-stu-id="a3f4a-134">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="a3f4a-135">Richiede un record DNS per l'indirizzo IP di ogni server front-end all'interno del pool, eseguendo il mapping al nome di dominio completo del pool.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-135">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3f4a-136">DNS interno</span><span class="sxs-lookup"><span data-stu-id="a3f4a-136">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-137">A</span><span class="sxs-lookup"><span data-stu-id="a3f4a-137">A</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-138">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a3f4a-138">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-139">Pool01 (Virtual IP (VIP) di bilanciamento del carico hardware).</span><span class="sxs-lookup"><span data-stu-id="a3f4a-139">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3f4a-140">DNS interno</span><span class="sxs-lookup"><span data-stu-id="a3f4a-140">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-141">A</span><span class="sxs-lookup"><span data-stu-id="a3f4a-141">A</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-142">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a3f4a-142">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="a3f4a-143">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a3f4a-143">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="a3f4a-144">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a3f4a-144">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="a3f4a-145">…</span><span class="sxs-lookup"><span data-stu-id="a3f4a-145"></span></span></p></td>
<td><p><span data-ttu-id="a3f4a-146">Pool01 Front End Server (nodo 1).</span><span class="sxs-lookup"><span data-stu-id="a3f4a-146">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="a3f4a-147">Pool01 Front End Server (nodo 2).</span><span class="sxs-lookup"><span data-stu-id="a3f4a-147">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="a3f4a-148">Pool01 Front End Server (nodo 3).</span><span class="sxs-lookup"><span data-stu-id="a3f4a-148">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="a3f4a-149">…</span><span class="sxs-lookup"><span data-stu-id="a3f4a-149"></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3f4a-150">DNS interno</span><span class="sxs-lookup"><span data-stu-id="a3f4a-150">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-151">A</span><span class="sxs-lookup"><span data-stu-id="a3f4a-151">A</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-152">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a3f4a-152">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-153">Pool01 Front End Server (nodo 2).</span><span class="sxs-lookup"><span data-stu-id="a3f4a-153">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3f4a-154">DNS interno</span><span class="sxs-lookup"><span data-stu-id="a3f4a-154">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-155">A</span><span class="sxs-lookup"><span data-stu-id="a3f4a-155">A</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-156">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a3f4a-156">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-157">Pool01 (VIP) per il traffico Web da client a server.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-157">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3f4a-158">DNS interno</span><span class="sxs-lookup"><span data-stu-id="a3f4a-158">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-159">A</span><span class="sxs-lookup"><span data-stu-id="a3f4a-159">A</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-160">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a3f4a-160">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-161">Pool01 back end server che utilizza SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-161">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3f4a-162">DNS interno</span><span class="sxs-lookup"><span data-stu-id="a3f4a-162">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-163">A</span><span class="sxs-lookup"><span data-stu-id="a3f4a-163">A</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3f4a-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-165">Obbligatorio per Lync Phone Edition o accesso automatico dei client senza record SRV DNS e per la corrispondenza di domini rigidi.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-165">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="a3f4a-166">Non obbligatorio in tutti i casi.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-166">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3f4a-167">DNS interno</span><span class="sxs-lookup"><span data-stu-id="a3f4a-167">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-168">A</span><span class="sxs-lookup"><span data-stu-id="a3f4a-168">A</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-169">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="a3f4a-169">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-170">Presuppone un secondo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-170">Assumes a second SIP domain.</span></span> <span data-ttu-id="a3f4a-171">Obbligatorio per Lync Phone Edition, accesso automatico dei client senza record SRV DNS e per la corrispondenza di domini rigidi.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-171">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="a3f4a-172">Non obbligatorio in tutti i casi.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-172">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3f4a-173">DNS interno</span><span class="sxs-lookup"><span data-stu-id="a3f4a-173">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-174">A</span><span class="sxs-lookup"><span data-stu-id="a3f4a-174">A</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-175">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3f4a-175">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-176">URL semplice per i servizi di conferenza telefonica con accesso esterno pubblicati internamente-Front End Server (o Director, se installato) risponde a semplici query URL.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-176">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3f4a-177">DNS interno</span><span class="sxs-lookup"><span data-stu-id="a3f4a-177">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-178">A</span><span class="sxs-lookup"><span data-stu-id="a3f4a-178">A</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-179">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3f4a-179">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-180">URL semplice per le conferenze pubblicate internamente-Front End Server (o Director, se installato) risponde a semplici query URL.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-180">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3f4a-181">DNS interno</span><span class="sxs-lookup"><span data-stu-id="a3f4a-181">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-182">A</span><span class="sxs-lookup"><span data-stu-id="a3f4a-182">A</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-183">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3f4a-183">admin.contoso.com</span></span></p>
<p><span data-ttu-id="a3f4a-184">admin</span><span class="sxs-lookup"><span data-stu-id="a3f4a-184">admin</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-185">Record facoltativo, URL semplice per il pannello di controllo di Lync Server 2013 pubblicato internamente-Front-End Server (o direttore, se installato) risponde a semplici query URL.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-185">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="a3f4a-186">È consigliabile solo nome host (nessun nome di dominio).</span><span class="sxs-lookup"><span data-stu-id="a3f4a-186">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a3f4a-187">VIP = indirizzo IP virtuale per il bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="a3f4a-187">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="a3f4a-188">Record SRV DNS per il pool Front-End</span><span class="sxs-lookup"><span data-stu-id="a3f4a-188">DNS SRV Records for the Front End pool</span></span>


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
<th><span data-ttu-id="a3f4a-189">Posizione</span><span class="sxs-lookup"><span data-stu-id="a3f4a-189">Location</span></span></th>
<th><span data-ttu-id="a3f4a-190">Tipo</span><span class="sxs-lookup"><span data-stu-id="a3f4a-190">Type</span></span></th>
<th><span data-ttu-id="a3f4a-191">FQDN</span><span class="sxs-lookup"><span data-stu-id="a3f4a-191">FQDN</span></span></th>
<th><span data-ttu-id="a3f4a-192">FQDN di destinazione</span><span class="sxs-lookup"><span data-stu-id="a3f4a-192">Target FQDN</span></span></th>
<th><span data-ttu-id="a3f4a-193">Porta</span><span class="sxs-lookup"><span data-stu-id="a3f4a-193">Port</span></span></th>
<th><span data-ttu-id="a3f4a-194">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="a3f4a-194">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3f4a-195">DNS interno</span><span class="sxs-lookup"><span data-stu-id="a3f4a-195">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-196">SRV</span><span class="sxs-lookup"><span data-stu-id="a3f4a-196">SRV</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-197">_sipinternaltls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a3f4a-197">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-198">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3f4a-198">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-199">5061</span><span class="sxs-lookup"><span data-stu-id="a3f4a-199">5061</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-200">Necessario per la configurazione automatica dei client di Lync 2013 per l'utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-200">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3f4a-201">DNS interno</span><span class="sxs-lookup"><span data-stu-id="a3f4a-201">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-202">SRV</span><span class="sxs-lookup"><span data-stu-id="a3f4a-202">SRV</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-203">_sipinternaltls. _tcp. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="a3f4a-203">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-204">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="a3f4a-204">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-205">5061</span><span class="sxs-lookup"><span data-stu-id="a3f4a-205">5061</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-206">Necessario per la configurazione automatica dei client di Lync 2013 per l'utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-206">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3f4a-207">DNS interno</span><span class="sxs-lookup"><span data-stu-id="a3f4a-207">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-208">SRV</span><span class="sxs-lookup"><span data-stu-id="a3f4a-208">SRV</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-209">_ntp. _udp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a3f4a-209">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-210">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3f4a-210">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-211">123</span><span class="sxs-lookup"><span data-stu-id="a3f4a-211">123</span></span></p></td>
<td><p><span data-ttu-id="a3f4a-212">Origine del protocollo Network Time Protocol (NTP) necessaria per i dispositivi in cui è in esecuzione Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-212">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="a3f4a-213">Internamente, questo deve puntare al controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-213">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="a3f4a-214">Se il controller di dominio non è definito, tenterà di usare il server NTP time.windows.com.</span><span class="sxs-lookup"><span data-stu-id="a3f4a-214">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

