---
title: 'Lync Server 2013: Riepilogo di DNS - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP pubblici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48185594
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f748f8107e4d1c0da41a07285eb61e4a3149551
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="04174-102">Riepilogo di DNS - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04174-102">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04174-103">_**Argomento Ultima modifica:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="04174-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="04174-104">I requisiti dei record DNS per l'accesso remoto a Lync Server 2013 sono abbastanza semplici rispetto a quelli per i certificati e le porte.</span><span class="sxs-lookup"><span data-stu-id="04174-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="04174-105">Inoltre, molti record sono facoltativi, a seconda di come si configurano i client che usano Lync 2013 e se si Abilita la Federazione.</span><span class="sxs-lookup"><span data-stu-id="04174-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="04174-106">Per informazioni dettagliate sui requisiti DNS di Lync 2013, vedere [determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04174-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="04174-107">Per informazioni dettagliate sulla configurazione della configurazione automatica dei client di Lync 2013 se non è configurato il DNS split-brain, vedere la sezione "configurazione automatica senza DNS divisa" in [determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04174-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="04174-108">La tabella seguente contiene un riepilogo dei record DNS necessari per supportare la singola topologia perimetrale consolidata visualizzata nella figura singola topologia perimetrale consolidata.</span><span class="sxs-lookup"><span data-stu-id="04174-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="04174-109">Tieni presente che alcuni record DNS sono necessari solo per la configurazione automatica dei client di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="04174-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="04174-110">Se si prevede di usare gli oggetti Criteri di gruppo per configurare i client Lync, i record associati non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="04174-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="04174-111">IMPORTANTE: requisiti della scheda di rete Edge Server</span><span class="sxs-lookup"><span data-stu-id="04174-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="04174-112">Per evitare problemi di routing, verificare che siano presenti almeno due schede di rete negli Edge Server e che il gateway predefinito sia impostato solo sulla scheda di rete associata all'interfaccia esterna.</span><span class="sxs-lookup"><span data-stu-id="04174-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="04174-113">Ad esempio, come illustrato nella figura scenario di Edge consolidato in scala [consolidata, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , il gateway predefinito punta al firewall esterno.</span><span class="sxs-lookup"><span data-stu-id="04174-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="04174-114">È possibile configurare due schede di rete in ogni server perimetrale nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="04174-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="04174-115">**Scheda di rete 1-nodo 1 (interfaccia interna)**</span><span class="sxs-lookup"><span data-stu-id="04174-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="04174-116">Interfaccia interna con 172.25.33.10 assegnati.</span><span class="sxs-lookup"><span data-stu-id="04174-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="04174-117">Nessun gateway predefinito è definito.</span><span class="sxs-lookup"><span data-stu-id="04174-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="04174-118">Verificare che esista una route dalla rete che contiene l'interfaccia interna di Edge a tutte le reti che contengono server che includono client Lync Server 2013 o Lync Server 2013, ad esempio da 172.25.33.0 a 192.168.10.0.</span><span class="sxs-lookup"><span data-stu-id="04174-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="04174-119">**Scheda di rete 1-nodo 2 (interfaccia interna)**</span><span class="sxs-lookup"><span data-stu-id="04174-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="04174-120">Interfaccia interna con 172.25.33.11 assegnati.</span><span class="sxs-lookup"><span data-stu-id="04174-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="04174-121">Nessun gateway predefinito è definito.</span><span class="sxs-lookup"><span data-stu-id="04174-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="04174-122">Verificare che esista una route dalla rete che contiene l'interfaccia interna di Edge a tutte le reti che contengono server che includono client Lync Server 2013 o Lync Server 2013, ad esempio da 172.25.33.0 a 192.168.10.0.</span><span class="sxs-lookup"><span data-stu-id="04174-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="04174-123">**Scheda di rete 2 node 1 (interfaccia esterna)**</span><span class="sxs-lookup"><span data-stu-id="04174-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="04174-124">Alla scheda di rete sono assegnati tre indirizzi IP privati, ad esempio 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge Services.</span><span class="sxs-lookup"><span data-stu-id="04174-124">Three private IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <span data-ttu-id="04174-125">L'indirizzo IP pubblico del servizio Edge di Access è primario con il set di gateway predefinito per il router pubblico (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="04174-125">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="04174-126">I servizi di Web Conferencing Edge e gli indirizzi IP privati del servizio Edge A/V sono indirizzi IP aggiuntivi nella sezione **Avanzate** delle proprietà di **Internet Protocol versione 4 (TCP/IPv4)** e **protocollo Internet versione 6 (TCP/IPv6)** delle **proprietà di connessione dell'area locale** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="04174-126">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04174-127">È comunque possibile usare un singolo indirizzo IP per tutte le tre interfacce del servizio Edge.</span><span class="sxs-lookup"><span data-stu-id="04174-127">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="04174-128">Anche se questo Salva gli indirizzi IP, richiede numeri di porta diversi per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="04174-128">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="04174-129">Il numero di porta predefinito è 443/TCP, che garantisce che la maggior parte dei firewall remoti consentirà il traffico.</span><span class="sxs-lookup"><span data-stu-id="04174-129">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="04174-130">La modifica dei valori della porta in (ad esempio) 5061/TCP per il servizio Access Edge, 444/TCP per il servizio Web Conferencing Edge e 443/TCP per il servizio A/V Edge può causare problemi per gli utenti remoti in cui un firewall che sta dietro non consente il traffico su 5061/TCP e 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="04174-130">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="04174-131">Inoltre, tre indirizzi IP distinti semplificano la risoluzione dei problemi grazie alla possibilità di filtrare in base all'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="04174-131">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>

  - <span data-ttu-id="04174-132">**Scheda di rete 2 node 2 (interfaccia esterna)**</span><span class="sxs-lookup"><span data-stu-id="04174-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="04174-133">Alla scheda di rete sono assegnati tre indirizzi IP privati, ad esempio 131.107.155.11 for Access Edge service, 131.107.155.21 for Web Conferencing Edge service, 131.107.155.31 for A/V Edge Services.</span><span class="sxs-lookup"><span data-stu-id="04174-133">Three private IP addresses are assigned to this network adapter, for example 131.107.155.11 for Access Edge service, 131.107.155.21 for Web Conferencing Edge service, 131.107.155.31 for A/V Edge service.</span></span>
    
    <span data-ttu-id="04174-134">L'indirizzo IP pubblico del servizio Edge di Access è primario con il set di gateway predefinito per il router pubblico (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="04174-134">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="04174-135">I servizi di Web Conferencing Edge e gli indirizzi IP privati del servizio Edge A/V sono indirizzi IP aggiuntivi nella sezione **Avanzate** delle proprietà di **Internet Protocol versione 4 (TCP/IPv4)** e **protocollo Internet versione 6 (TCP/IPv6)** delle **proprietà di connessione dell'area locale** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="04174-135">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="04174-136">La configurazione di Edge Server con due schede di rete è una delle due opzioni.</span><span class="sxs-lookup"><span data-stu-id="04174-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="04174-137">L'altra opzione consiste nell'usare una scheda di rete per il lato interno e tre schede di rete per il lato esterno del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="04174-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="04174-138">Il vantaggio principale di questa opzione è una scheda di rete distinta per ogni servizio Edge Server e una raccolta di dati potenzialmente più concisa quando è necessaria la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="04174-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a><span data-ttu-id="04174-139">Record DNS necessari per i bordi consolidati in scala, bilanciamento del carico DNS con indirizzi IP pubblici (esempio)</span><span class="sxs-lookup"><span data-stu-id="04174-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04174-140">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="04174-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="04174-141">Record FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="04174-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="04174-142">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="04174-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="04174-143">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="04174-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04174-144">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="04174-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="04174-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04174-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04174-146">131.107.155.10 e 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="04174-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="04174-147">Ripetizione dell'interfaccia esterna di Access Edge Services (contoso), se necessario per tutti i domini SIP con gli utenti abilitati a Lync</span><span class="sxs-lookup"><span data-stu-id="04174-147">Access Edge service external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04174-148">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="04174-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="04174-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04174-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04174-150">131.107.155.20 e 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="04174-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="04174-151">Interfaccia esterna di Web Conferencing Edge service</span><span class="sxs-lookup"><span data-stu-id="04174-151">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04174-152">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="04174-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="04174-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04174-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04174-154">131.107.155.30 e 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="04174-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="04174-155">Interfaccia esterna di un/V Edge service</span><span class="sxs-lookup"><span data-stu-id="04174-155">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04174-156">DNS esterno/SRV/443</span><span class="sxs-lookup"><span data-stu-id="04174-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="04174-157">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="04174-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04174-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04174-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04174-159">Interfaccia esterna di Access Edge Services.</span><span class="sxs-lookup"><span data-stu-id="04174-159">Access Edge service external interface.</span></span> <span data-ttu-id="04174-160">Necessario per la configurazione automatica dei client Lync 2013 e Lync 2010 per l'utilizzo esterno.</span><span class="sxs-lookup"><span data-stu-id="04174-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="04174-161">Ripetere le esigenze per tutti i domini SIP con gli utenti abilitati a Lync.</span><span class="sxs-lookup"><span data-stu-id="04174-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04174-162">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="04174-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="04174-163">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="04174-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04174-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04174-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04174-165">Interfaccia esterna di Access Edge service necessaria per l'individuazione automatica di DNS dei partner federati noti come "dominio SIP consentito" (chiamata federazione avanzata nelle versioni precedenti).</span><span class="sxs-lookup"><span data-stu-id="04174-165">Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="04174-166">Ripetere la procedura necessaria per tutti i domini SIP con gli utenti abilitati a Lync</span><span class="sxs-lookup"><span data-stu-id="04174-166">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04174-167">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="04174-167">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="04174-168">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="04174-168">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="04174-169">172.25.33.10 e 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="04174-169">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="04174-170">Interfaccia interna del bordo consolidato</span><span class="sxs-lookup"><span data-stu-id="04174-170">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="04174-171">Record necessari per la Federazione</span><span class="sxs-lookup"><span data-stu-id="04174-171">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04174-172">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="04174-172">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="04174-173">FQDN</span><span class="sxs-lookup"><span data-stu-id="04174-173">FQDN</span></span></th>
<th><span data-ttu-id="04174-174">Indirizzo IP/record host FQDN</span><span class="sxs-lookup"><span data-stu-id="04174-174">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="04174-175">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="04174-175">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04174-176">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="04174-176">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="04174-177">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="04174-177">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04174-178">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04174-178">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04174-179">Interfaccia esterna per SIP Access Edge service necessaria per l'individuazione automatica del DNS della Federazione ad altri potenziali partner federativi ed è nota come "domini SIP consentiti" (chiamata federazione avanzata nelle versioni precedenti).</span><span class="sxs-lookup"><span data-stu-id="04174-179">SIP Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="04174-180">Ripetere le operazioni necessarie per tutti i domini SIP con gli utenti abilitati a Lync e i client di Microsoft Lync mobile che usano il servizio di notifica push o il servizio di notifica push Apple</span><span class="sxs-lookup"><span data-stu-id="04174-180">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="04174-181">Riepilogo DNS per il protocollo di messaggistica e presenza estensibile</span><span class="sxs-lookup"><span data-stu-id="04174-181">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04174-182">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="04174-182">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="04174-183">FQDN</span><span class="sxs-lookup"><span data-stu-id="04174-183">FQDN</span></span></th>
<th><span data-ttu-id="04174-184">Indirizzo IP/record host FQDN</span><span class="sxs-lookup"><span data-stu-id="04174-184">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="04174-185">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="04174-185">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04174-186">DNS esterno/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="04174-186">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="04174-187">_xmpp-server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="04174-187">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04174-188">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04174-188">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04174-189">Interfaccia esterna proxy XMPP nel pool di servizi o Edge di Access. Ripetere l'impostazione necessaria per tutti i domini SIP interni con gli utenti abilitati a Lync in cui è consentito il contatto con i contatti XMPP tramite la configurazione dei criteri di accesso esterno tramite un criterio globale, il criterio del sito in cui si trova l'utente o i criteri degli utenti applicati alla Utenti abilitati per Lync.</span><span class="sxs-lookup"><span data-stu-id="04174-189">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="04174-190">Un dominio XMPP consentito deve essere configurato anche nei criteri dei partner federati XMPP.</span><span class="sxs-lookup"><span data-stu-id="04174-190">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="04174-191">Vedere gli argomenti in <strong>vedere anche</strong> per ulteriori dettagli</span><span class="sxs-lookup"><span data-stu-id="04174-191">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04174-192">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="04174-192">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="04174-193">xmpp.contoso.com (ad esempio)</span><span class="sxs-lookup"><span data-stu-id="04174-193">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="04174-194">Indirizzo IP del servizio Access Edge nell'Edge Server o nel pool di Edge che ospita il proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="04174-194">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="04174-195">Punta al servizio di Access Edge o al pool di Edge che ospita il servizio proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="04174-195">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="04174-196">In genere, il record SRV creato punterà al record host (A o AAAA)</span><span class="sxs-lookup"><span data-stu-id="04174-196">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

