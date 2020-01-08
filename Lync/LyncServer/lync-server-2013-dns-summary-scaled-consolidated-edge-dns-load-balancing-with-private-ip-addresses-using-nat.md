---
title: 'Lync Server 2013: Riepilogo di DNS - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398201(v=OCS.15)
ms:contentKeyID: 48183447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7476f258ddd70adad7f200db90b39438a19f4f84
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="9c628-102">Riepilogo di DNS - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c628-102">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c628-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="9c628-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="9c628-104">I requisiti dei record DNS per l'accesso remoto a Lync Server 2013 sono abbastanza semplici rispetto a quelli per i certificati e le porte.</span><span class="sxs-lookup"><span data-stu-id="9c628-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="9c628-105">Inoltre, molti record sono facoltativi, a seconda di come si configurano i client che usano Lync 2013 e se si Abilita la Federazione.</span><span class="sxs-lookup"><span data-stu-id="9c628-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="9c628-106">Per informazioni dettagliate sui requisiti DNS di Lync 2013, vedere [determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c628-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="9c628-107">Per informazioni dettagliate sulla configurazione della configurazione automatica dei client di Lync 2013 se non è configurato il DNS split-brain, vedere la sezione "configurazione automatica senza DNS divisa" in [determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c628-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="9c628-108">La tabella seguente contiene un riepilogo dei record DNS necessari per supportare la singola topologia perimetrale consolidata visualizzata nella figura singola topologia perimetrale consolidata.</span><span class="sxs-lookup"><span data-stu-id="9c628-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="9c628-109">Tieni presente che alcuni record DNS sono necessari solo per la configurazione automatica dei client di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9c628-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="9c628-110">Se si prevede di usare gli oggetti Criteri di gruppo per configurare i client Lync, i record associati non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="9c628-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="9c628-111">IMPORTANTE: requisiti della scheda di rete Edge Server</span><span class="sxs-lookup"><span data-stu-id="9c628-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="9c628-112">Per evitare problemi di routing, verificare che siano presenti almeno due schede di rete negli Edge Server e che il gateway predefinito sia impostato solo sulla scheda di rete associata all'interfaccia esterna.</span><span class="sxs-lookup"><span data-stu-id="9c628-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="9c628-113">Ad esempio, come illustrato nella figura scenario di Edge consolidato in scala [consolidata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), il gateway predefinito punta al firewall esterno.</span><span class="sxs-lookup"><span data-stu-id="9c628-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="9c628-114">È possibile configurare due schede di rete in ogni server perimetrale nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="9c628-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="9c628-115">**Scheda di rete 1-nodo 1 (interfaccia interna)**</span><span class="sxs-lookup"><span data-stu-id="9c628-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="9c628-116">Interfaccia interna con 172.25.33.10 assegnati.</span><span class="sxs-lookup"><span data-stu-id="9c628-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="9c628-117">Nessun gateway predefinito è definito.</span><span class="sxs-lookup"><span data-stu-id="9c628-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="9c628-118">Verificare che esista una route dalla rete che contiene l'interfaccia interna di Edge a tutte le reti che contengono server che includono client Lync Server 2013 o Lync Server 2013, ad esempio da 172.25.33.0 a 192.168.10.0.</span><span class="sxs-lookup"><span data-stu-id="9c628-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="9c628-119">**Scheda di rete 1-nodo 2 (interfaccia interna)**</span><span class="sxs-lookup"><span data-stu-id="9c628-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="9c628-120">Interfaccia interna con 172.25.33.11 assegnati.</span><span class="sxs-lookup"><span data-stu-id="9c628-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="9c628-121">Nessun gateway predefinito è definito.</span><span class="sxs-lookup"><span data-stu-id="9c628-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="9c628-122">Verificare che esista una route dalla rete che contiene l'interfaccia interna di Edge a tutte le reti che contengono server che includono client Lync Server 2013 o Lync Server 2013, ad esempio da 172.25.33.0 a 192.168.10.0.</span><span class="sxs-lookup"><span data-stu-id="9c628-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="9c628-123">**Scheda di rete 2 node 1 (interfaccia esterna)**</span><span class="sxs-lookup"><span data-stu-id="9c628-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="9c628-124">Alla scheda di rete vengono assegnati tre indirizzi IP privati, ad esempio 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge.</span><span class="sxs-lookup"><span data-stu-id="9c628-124">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9c628-125">È comunque possibile usare un singolo indirizzo IP per tutte le tre interfacce del servizio Edge.</span><span class="sxs-lookup"><span data-stu-id="9c628-125">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="9c628-126">Anche se questo Salva gli indirizzi IP, richiede numeri di porta diversi per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="9c628-126">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="9c628-127">Il numero di porta predefinito è 443/TCP, che garantisce che la maggior parte dei firewall remoti consentirà il traffico.</span><span class="sxs-lookup"><span data-stu-id="9c628-127">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="9c628-128">La modifica dei valori della porta in (ad esempio) 5061/TCP per l'Access Edge, 444/TCP per il Web Conferencing Edge e 443/TCP per il Edge AV può causare problemi per gli utenti remoti in cui un firewall che si trovano dietro non consente il traffico su 5061/TCP e 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="9c628-128">Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="9c628-129">Inoltre, tre indirizzi IP distinti semplificano la risoluzione dei problemi grazie alla possibilità di filtrare in base all'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="9c628-129">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="9c628-130">L'indirizzo IP pubblico di Access Edge è primario con il set di gateway predefinito per il router integrato (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="9c628-130">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="9c628-131">Gli indirizzi IP privati di servizi di conferenza Web e A/V Edge sono indirizzi IP aggiuntivi nella sezione **Avanzate** delle proprietà di **Internet Protocol versione 4 (TCP/IPv4)** e **Internet Protocol versione 6 (TCP/IPv6)** delle **proprietà di connessione all'area locale** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="9c628-131">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

  - <span data-ttu-id="9c628-132">**Scheda di rete 2 node 2 (interfaccia esterna)**</span><span class="sxs-lookup"><span data-stu-id="9c628-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="9c628-133">Alla scheda di rete vengono assegnati tre indirizzi IP privati, ad esempio 10.45.16.11 for Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 for AV Edge.</span><span class="sxs-lookup"><span data-stu-id="9c628-133">Three private IP addresses are assigned to this network adapter, for example 10.45.16.11 for Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 for AV Edge.</span></span>
    
    <span data-ttu-id="9c628-134">L'indirizzo IP pubblico di Access Edge è primario con il set di gateway predefinito per il router integrato (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="9c628-134">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="9c628-135">Gli indirizzi IP privati di servizi di conferenza Web e A/V Edge sono indirizzi IP aggiuntivi nella sezione **Avanzate** delle proprietà di **Internet Protocol versione 4 (TCP/IPv4)** e **Internet Protocol versione 6 (TCP/IPv6)** delle **proprietà di connessione all'area locale** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="9c628-135">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="9c628-136">La configurazione di Edge Server con due schede di rete è una delle due opzioni.</span><span class="sxs-lookup"><span data-stu-id="9c628-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="9c628-137">L'altra opzione consiste nell'usare una scheda di rete per il lato interno e tre schede di rete per il lato esterno del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="9c628-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="9c628-138">Il vantaggio principale di questa opzione è una scheda di rete distinta per ogni servizio Edge Server e una raccolta di dati potenzialmente più concisa quando è necessaria la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="9c628-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="9c628-139">Record DNS necessari per il bordo consolidato scalato, bilanciamento del carico DNS con indirizzi IP privati tramite NAT (esempio)</span><span class="sxs-lookup"><span data-stu-id="9c628-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c628-140">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="9c628-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="9c628-141">Record FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="9c628-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="9c628-142">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="9c628-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="9c628-143">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="9c628-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c628-144">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="9c628-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9c628-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c628-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c628-146">131.107.155.10 e 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="9c628-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="9c628-147">Ripetizione dell'interfaccia esterna di Access Edge (contoso), se necessario per tutti i domini SIP con gli utenti abilitati a Lync</span><span class="sxs-lookup"><span data-stu-id="9c628-147">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c628-148">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="9c628-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9c628-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c628-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c628-150">131.107.155.20 e 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="9c628-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="9c628-151">Interfaccia esterna di Web Conferencing Edge</span><span class="sxs-lookup"><span data-stu-id="9c628-151">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c628-152">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="9c628-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9c628-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c628-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c628-154">131.107.155.30 e 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="9c628-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="9c628-155">Interfaccia esterna Edge A/V</span><span class="sxs-lookup"><span data-stu-id="9c628-155">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c628-156">DNS esterno/SRV/443</span><span class="sxs-lookup"><span data-stu-id="9c628-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="9c628-157">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="9c628-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c628-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c628-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c628-159">Interfaccia esterna di Access Edge.</span><span class="sxs-lookup"><span data-stu-id="9c628-159">Access Edge external interface.</span></span> <span data-ttu-id="9c628-160">Necessario per la configurazione automatica dei client Lync 2013 e Lync 2010 per l'utilizzo esterno.</span><span class="sxs-lookup"><span data-stu-id="9c628-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="9c628-161">Ripetere le esigenze per tutti i domini SIP con gli utenti abilitati a Lync.</span><span class="sxs-lookup"><span data-stu-id="9c628-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c628-162">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="9c628-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="9c628-163">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="9c628-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c628-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c628-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c628-165">Interfaccia esterna di Access Edge SIP.</span><span class="sxs-lookup"><span data-stu-id="9c628-165">SIP Access Edge external interface.</span></span> <span data-ttu-id="9c628-166">Obbligatorio per l'individuazione automatica di DNS per i partner federati noti come "dominio SIP consentito" (chiamata federazione avanzata nelle versioni precedenti).</span><span class="sxs-lookup"><span data-stu-id="9c628-166">Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="9c628-167">Ripetere la procedura necessaria per tutti i domini SIP con gli utenti abilitati a Lync</span><span class="sxs-lookup"><span data-stu-id="9c628-167">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c628-168">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="9c628-168">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9c628-169">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="9c628-169">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="9c628-170">172.25.33.10 e 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="9c628-170">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="9c628-171">Interfaccia interna del bordo consolidato</span><span class="sxs-lookup"><span data-stu-id="9c628-171">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="9c628-172">Record necessari per la Federazione</span><span class="sxs-lookup"><span data-stu-id="9c628-172">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c628-173">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="9c628-173">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="9c628-174">FQDN</span><span class="sxs-lookup"><span data-stu-id="9c628-174">FQDN</span></span></th>
<th><span data-ttu-id="9c628-175">Indirizzo IP/record host FQDN</span><span class="sxs-lookup"><span data-stu-id="9c628-175">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="9c628-176">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="9c628-176">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c628-177">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="9c628-177">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="9c628-178">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="9c628-178">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c628-179">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c628-179">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c628-180">Interfaccia esterna di Access Edge SIP necessaria per l'individuazione automatica del DNS della Federazione ad altri potenziali partner federativi ed è nota come "domini SIP consentiti" (chiamata federazione avanzata nelle versioni precedenti). Ripetere la procedura necessaria per tutti i domini SIP con gli utenti abilitati a Lync</span><span class="sxs-lookup"><span data-stu-id="9c628-180">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="9c628-181">Questo record SRV è necessario per la mobilità e la camera di compensazione delle notifiche push</span><span class="sxs-lookup"><span data-stu-id="9c628-181">This SRV record is required for mobility and the push notification clearing house</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="9c628-182">Riepilogo DNS-connettività di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="9c628-182">DNS Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c628-183">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="9c628-183">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="9c628-184">Record FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="9c628-184">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="9c628-185">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="9c628-185">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="9c628-186">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="9c628-186">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c628-187">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="9c628-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9c628-188">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c628-188">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c628-189">Interfaccia del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="9c628-189">Access Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="9c628-190">Ripetizione dell'interfaccia esterna di Access Edge (contoso), se necessario per tutti i domini SIP con gli utenti abilitati a Lync</span><span class="sxs-lookup"><span data-stu-id="9c628-190">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="9c628-191">Riepilogo DNS per il protocollo di messaggistica e presenza estensibile</span><span class="sxs-lookup"><span data-stu-id="9c628-191">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c628-192">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="9c628-192">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="9c628-193">FQDN</span><span class="sxs-lookup"><span data-stu-id="9c628-193">FQDN</span></span></th>
<th><span data-ttu-id="9c628-194">Indirizzo IP/record host FQDN</span><span class="sxs-lookup"><span data-stu-id="9c628-194">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="9c628-195">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="9c628-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c628-196">DNS esterno/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="9c628-196">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="9c628-197">_xmpp-server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="9c628-197">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c628-198">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c628-198">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c628-199">Interfaccia esterna proxy XMPP nel pool di servizi o Edge di Access. Ripetere l'impostazione necessaria per tutti i domini SIP interni con gli utenti abilitati a Lync in cui è consentito il contatto con i contatti XMPP tramite la configurazione dei criteri di accesso esterno tramite un criterio globale, il criterio del sito in cui si trova l'utente o i criteri degli utenti applicati alla Utenti abilitati per Lync.</span><span class="sxs-lookup"><span data-stu-id="9c628-199">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="9c628-200">Un dominio XMPP consentito deve essere configurato anche nei criteri dei partner federati XMPP.</span><span class="sxs-lookup"><span data-stu-id="9c628-200">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="9c628-201">Vedere gli argomenti in <strong>vedere anche</strong> per ulteriori dettagli</span><span class="sxs-lookup"><span data-stu-id="9c628-201">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c628-202">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="9c628-202">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9c628-203">xmpp.contoso.com (ad esempio)</span><span class="sxs-lookup"><span data-stu-id="9c628-203">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="9c628-204">Indirizzo IP del servizio Access Edge nell'Edge Server o nel pool di Edge che ospita il proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="9c628-204">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="9c628-205">Punta al servizio di Access Edge o al pool di Edge che ospita il servizio proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="9c628-205">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="9c628-206">In genere, il record SRV creato punterà al record host (A o AAAA)</span><span class="sxs-lookup"><span data-stu-id="9c628-206">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

