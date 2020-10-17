---
title: 'Lync Server 2013: Consolidated Edge in scala di riepilogo DNS, bilanciamento del carico DNS con indirizzi IP privati tramite NAT'
description: 'Lync Server 2013: Consolidated Edge in scala di riepilogo DNS, bilanciamento del carico DNS con indirizzi IP privati tramite NAT.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398201(v=OCS.15)
ms:contentKeyID: 48183447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eef3029323c1c2f798fddc721df832a932524c8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559402"
---
# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="595e6-103">Server perimetrale consolidato in scala di riepilogo DNS, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="595e6-103">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="595e6-104">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="595e6-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="595e6-105">I requisiti dei record DNS per l'accesso remoto a Lync Server 2013 sono relativamente semplici rispetto a quelli relativi ai certificati e alle porte.</span><span class="sxs-lookup"><span data-stu-id="595e6-105">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="595e6-106">Inoltre, molti record sono facoltativi, a seconda del modo in cui vengono configurati i client che eseguono Lync 2013 e se si Abilita la Federazione.</span><span class="sxs-lookup"><span data-stu-id="595e6-106">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="595e6-107">Per informazioni dettagliate sui requisiti DNS di Lync 2013, vedere [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="595e6-107">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="595e6-108">Per informazioni dettagliate sulla configurazione automatica dei client Lync 2013 se il DNS split-brain non è configurato, vedere la sezione "configurazione automatica senza DNS split brain" in [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="595e6-108">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="595e6-109">Nella tabella seguente viene fornito un riepilogo dei record DNS necessari per supportare la topologia perimetrale consolidata singola illustrata nella relativa figura.</span><span class="sxs-lookup"><span data-stu-id="595e6-109">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="595e6-110">Si noti che alcuni record DNS sono necessari solo per la configurazione automatica dei client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="595e6-110">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="595e6-111">Se si prevede di utilizzare gli oggetti Criteri di gruppo per configurare i client Lync, i record associati non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="595e6-111">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="595e6-112">IMPORTANTE: requisiti della scheda di rete per i server perimetrali</span><span class="sxs-lookup"><span data-stu-id="595e6-112">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="595e6-113">Per evitare problemi di routing, verificare che siano presenti almeno due schede di rete nei server perimetrali e che il gateway predefinito sia impostato solo sulla scheda di rete associata all'interfaccia esterna.</span><span class="sxs-lookup"><span data-stu-id="595e6-113">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="595e6-114">Ad esempio, come illustrato nella figura dello scenario perimetrale consolidato in scala in scala [consolidata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), il gateway predefinito dovrebbe puntare al firewall esterno.</span><span class="sxs-lookup"><span data-stu-id="595e6-114">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="595e6-115">È possibile configurare due schede di rete in ogni server perimetrale, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="595e6-115">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="595e6-116">**Scheda di rete 1 - Nodo 1 (interfaccia interna)**</span><span class="sxs-lookup"><span data-stu-id="595e6-116">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="595e6-117">Interfaccia interna con indirizzo 172.25.33.10 assegnato.</span><span class="sxs-lookup"><span data-stu-id="595e6-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="595e6-118">Non è specificato alcun gateway predefinito.</span><span class="sxs-lookup"><span data-stu-id="595e6-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="595e6-119">Verificare che esista una route dalla rete che contiene l'interfaccia interna del server perimetrale a qualsiasi rete che contiene server che eseguono i client Lync 2013 o Lync Server 2013 (ad esempio, da 172.25.33.0 a 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="595e6-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="595e6-120">**Scheda di rete 1 - Nodo 2 (interfaccia interna)**</span><span class="sxs-lookup"><span data-stu-id="595e6-120">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="595e6-121">Interfaccia interna con indirizzo 172.25.33.11 assegnato.</span><span class="sxs-lookup"><span data-stu-id="595e6-121">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="595e6-122">Non è specificato alcun gateway predefinito.</span><span class="sxs-lookup"><span data-stu-id="595e6-122">No default gateway is defined.</span></span>
    
    <span data-ttu-id="595e6-123">Verificare che esista una route dalla rete che contiene l'interfaccia interna del server perimetrale a qualsiasi rete che contiene server che eseguono i client Lync 2013 o Lync Server 2013 (ad esempio, da 172.25.33.0 a 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="595e6-123">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="595e6-124">**Scheda di rete 2 - Nodo 1 (interfaccia esterna)**</span><span class="sxs-lookup"><span data-stu-id="595e6-124">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="595e6-125">A questa scheda di rete sono assegnati tre indirizzi IP privati, ad esempio 10.45.16.10 per Access Edge, 10.45.16.20 per Web Conferencing Edge e 10.45.16.30 per A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="595e6-125">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="595e6-p104">È possibile, anche se non consigliabile, utilizzare un unico indirizzo IP per tutte e tre le interfacce di servizio Edge. Sebbene consenta di ridurre il numero di indirizzi IP, questa soluzione richiede numeri di porta diversi per ogni servizio. Il numero di porta predefinito è 443/TCP, che assicura che il traffico sia consentito dalla maggior parte dei firewall remoti. Se i valori delle porte vengono impostati, ad esempio, su 5061/TCP per Access Edge, 444/TCP per Web Conferencing Edge e 443/TCP per A/V Edge, è possibile che gli utenti remoti riscontrino problemi se il firewall da cui sono protetti non consente il traffico sulle porte 5061/TCP e 444/TCP. Inoltre, tre indirizzi IP distinti semplificano le attività di risoluzione dei problemi grazie alla possibilità di filtrare in base all'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="595e6-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="595e6-131">L'indirizzo IP pubblico di Access Edge è primario, con gateway predefinito impostato sul router integrato (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="595e6-131">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="595e6-132">Gli indirizzi IP privati di Web Conferencing Edge e A/V Edge sono indirizzi IP aggiuntivi nella sezione **Avanzate** delle proprietà di **Protocollo Internet versione 4 (TCP/IPv4)** e **Protocollo Internet versione 6 (TCP/IPv6)** delle proprietà di **Connessione alla rete locale (LAN)** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="595e6-132">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

  - <span data-ttu-id="595e6-133">**Scheda di rete 2 - Nodo 2 (interfaccia esterna)**</span><span class="sxs-lookup"><span data-stu-id="595e6-133">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="595e6-134">A questa scheda di rete sono assegnati tre indirizzi IP privati, ad esempio 10.45.16.11 per Access Edge, 10.45.16.21 per Web Conferencing Edge e 10.45.16.31 per A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="595e6-134">Three private IP addresses are assigned to this network adapter, for example 10.45.16.11 for Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 for AV Edge.</span></span>
    
    <span data-ttu-id="595e6-135">L'indirizzo IP pubblico di Access Edge è primario, con gateway predefinito impostato sul router integrato (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="595e6-135">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="595e6-136">Gli indirizzi IP privati di Web Conferencing Edge e A/V Edge sono indirizzi IP aggiuntivi nella sezione **Avanzate** delle proprietà di **Protocollo Internet versione 4 (TCP/IPv4)** e **Protocollo Internet versione 6 (TCP/IPv6)** delle proprietà di **Connessione alla rete locale (LAN)** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="595e6-136">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="595e6-137">La configurazione del server perimetrale con due schede di rete è una delle due opzioni.</span><span class="sxs-lookup"><span data-stu-id="595e6-137">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="595e6-138">L'altra opzione consiste nell'utilizzare una scheda di rete per il lato interno e tre schede di rete per il lato esterno del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="595e6-138">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="595e6-139">Il vantaggio principale di questa opzione è una scheda di rete distinta per ogni servizio server perimetrale e una raccolta di dati potenzialmente più concisa quando è necessaria la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="595e6-139">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="595e6-140">Record DNS necessari per server perimetrale consolidato in scala, servizio di bilanciamento del carico DNS con indirizzi IP privati tramite NAT (esempio)</span><span class="sxs-lookup"><span data-stu-id="595e6-140">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="595e6-141">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="595e6-141">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="595e6-142">FQDN/Record DNS</span><span class="sxs-lookup"><span data-stu-id="595e6-142">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="595e6-143">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="595e6-143">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="595e6-144">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="595e6-144">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="595e6-145">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="595e6-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="595e6-146">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="595e6-146">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="595e6-147">131.107.155.10 e 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="595e6-147">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="595e6-148">Interfaccia esterna Access Edge (Contoso). Ripetere per tutti i domini SIP con utenti abilitati per Lync, se necessario</span><span class="sxs-lookup"><span data-stu-id="595e6-148">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595e6-149">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="595e6-149">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="595e6-150">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="595e6-150">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="595e6-151">131.107.155.20 e 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="595e6-151">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="595e6-152">Interfaccia esterna Web Conferencing Edge</span><span class="sxs-lookup"><span data-stu-id="595e6-152">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595e6-153">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="595e6-153">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="595e6-154">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="595e6-154">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="595e6-155">131.107.155.30 e 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="595e6-155">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="595e6-156">Interfaccia esterna A/V Edge</span><span class="sxs-lookup"><span data-stu-id="595e6-156">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595e6-157">DNS esterno/SRV/443</span><span class="sxs-lookup"><span data-stu-id="595e6-157">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="595e6-158">_sip _sip._tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="595e6-158">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="595e6-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="595e6-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="595e6-160">Interfaccia esterna di Access Edge.</span><span class="sxs-lookup"><span data-stu-id="595e6-160">Access Edge external interface.</span></span> <span data-ttu-id="595e6-161">Necessario per la configurazione automatica dei client Lync 2013 e Lync 2010 per funzionare esternamente.</span><span class="sxs-lookup"><span data-stu-id="595e6-161">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="595e6-162">Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync.</span><span class="sxs-lookup"><span data-stu-id="595e6-162">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595e6-163">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="595e6-163">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="595e6-164">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="595e6-164">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="595e6-165">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="595e6-165">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="595e6-p107">Interfaccia esterna Access Edge SIP. Necessario per l'individuazione DNS automatica di partner federati, nota come dominio SIP consentito, nonché come federazione avanzata nelle versioni precedenti. Ripetere per tutti i domini SIP con utenti abilitati per Lync, se necessario.</span><span class="sxs-lookup"><span data-stu-id="595e6-p107">SIP Access Edge external interface. Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases). Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595e6-169">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="595e6-169">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="595e6-170">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="595e6-170">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="595e6-171">172.25.33.10 e 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="595e6-171">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="595e6-172">Interfaccia interna del server perimetrale consolidato.</span><span class="sxs-lookup"><span data-stu-id="595e6-172">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="595e6-173">Record necessari per la federazione</span><span class="sxs-lookup"><span data-stu-id="595e6-173">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="595e6-174">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="595e6-174">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="595e6-175">FQDN</span><span class="sxs-lookup"><span data-stu-id="595e6-175">FQDN</span></span></th>
<th><span data-ttu-id="595e6-176">Indirizzo IP/FQDN record host</span><span class="sxs-lookup"><span data-stu-id="595e6-176">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="595e6-177">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="595e6-177">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="595e6-178">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="595e6-178">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="595e6-179">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="595e6-179">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="595e6-180">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="595e6-180">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="595e6-181">Interfaccia esterna SIP di Access Edge. Necessaria per l'individuazione DNS automatica di partner federati, nota come dominio SIP consentito, nonché come federazione avanzata nelle versioni precedenti. Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync.</span><span class="sxs-lookup"><span data-stu-id="595e6-181">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="595e6-182">Questo record SRV è necessario per la mobilità e il fornitore di servizi di accesso a terze parti delle notifiche push</span><span class="sxs-lookup"><span data-stu-id="595e6-182">This SRV record is required for mobility and the push notification clearing house</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="595e6-183">Riepilogo DNS – Public Instant Messaging Connectivity</span><span class="sxs-lookup"><span data-stu-id="595e6-183">DNS Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="595e6-184">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="595e6-184">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="595e6-185">FQDN/Record DNS</span><span class="sxs-lookup"><span data-stu-id="595e6-185">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="595e6-186">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="595e6-186">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="595e6-187">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="595e6-187">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="595e6-188">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="595e6-188">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="595e6-189">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="595e6-189">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="595e6-190">Interfaccia del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="595e6-190">Access Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="595e6-191">Interfaccia esterna di Access Edge (Contoso). Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync</span><span class="sxs-lookup"><span data-stu-id="595e6-191">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="595e6-192">Riepilogo DNS per Extensible Messaging and Presence Protocol</span><span class="sxs-lookup"><span data-stu-id="595e6-192">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="595e6-193">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="595e6-193">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="595e6-194">FQDN</span><span class="sxs-lookup"><span data-stu-id="595e6-194">FQDN</span></span></th>
<th><span data-ttu-id="595e6-195">Indirizzo IP/FQDN record host</span><span class="sxs-lookup"><span data-stu-id="595e6-195">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="595e6-196">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="595e6-196">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="595e6-197">DNS esterno/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="595e6-197">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="595e6-198">_xmpp-server._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="595e6-198">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="595e6-199">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="595e6-199">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="595e6-200">Interfaccia esterna del proxy XMPP nel servizio Access Edge o nel pool di server perimetrali. Ripetere quanto necessario per tutti i domini SIP interni con gli utenti abilitati per Lync, in cui è consentito il contatto con i contatti XMPP tramite la configurazione del criterio di accesso esterno tramite un criterio globale, il criterio del sito in cui si trova l'utente o il criterio utente applicato all'utente abilitato per Lync.</span><span class="sxs-lookup"><span data-stu-id="595e6-200">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="595e6-201">Un dominio XMPP consentito deve inoltre essere configurato nel criterio dei partner XMPP federati.</span><span class="sxs-lookup"><span data-stu-id="595e6-201">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="595e6-202">Per informazioni dettagliate, vedere gli argomenti in <strong>Vedere anche</strong></span><span class="sxs-lookup"><span data-stu-id="595e6-202">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595e6-203">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="595e6-203">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="595e6-204">xmpp.contoso.com (esempio)</span><span class="sxs-lookup"><span data-stu-id="595e6-204">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="595e6-205">Indirizzo IP del servizio Access Edge nel server perimetrale o nel pool perimetrale che ospita il proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="595e6-205">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="595e6-206">Punta al servizio Access Edge o al pool di server perimetrali che ospita il servizio proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="595e6-206">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="595e6-207">Il record SRV creato punterà a questo record host (A o AAAA).</span><span class="sxs-lookup"><span data-stu-id="595e6-207">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

