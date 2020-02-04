---
title: Riepilogo di DNS - topologia perimetrale consolidata con scalabilità implementata e servizi di bilanciamento del carico hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6be703e13ec50eb66ba52c981196df06adc6e5b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="f8570-102">Riepilogo di DNS - topologia perimetrale consolidata con scalabilità implementata e servizi di bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8570-102">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8570-103">_**Argomento Ultima modifica:** 2013-01-27_</span><span class="sxs-lookup"><span data-stu-id="f8570-103">_**Topic Last Modified:** 2013-01-27_</span></span>

<span data-ttu-id="f8570-104">I requisiti dei record DNS per l'accesso remoto a Lync Server 2013 sono abbastanza semplici rispetto a quelli per i certificati e le porte.</span><span class="sxs-lookup"><span data-stu-id="f8570-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="f8570-105">Inoltre, molti record sono facoltativi, a seconda di come si configurano i client che usano Lync 2013 e se si Abilita la Federazione.</span><span class="sxs-lookup"><span data-stu-id="f8570-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="f8570-106">Per informazioni dettagliate sui requisiti DNS di Lync 2013, vedere [determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8570-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="f8570-107">Per informazioni dettagliate sulla configurazione della configurazione automatica dei client di Lync 2013 se non è configurato il DNS split-brain, vedere la sezione "configurazione automatica senza DNS divisa" in [determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8570-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="f8570-108">La tabella seguente contiene un riepilogo dei record DNS necessari per supportare la topologia di Edge consolidato in scala (bilanciamento del carico hardware).</span><span class="sxs-lookup"><span data-stu-id="f8570-108">The following table contains a summary of the DNS records that are required to support the Scaled Consolidated Edge Topology (Hardware Load Balanced) figure.</span></span> <span data-ttu-id="f8570-109">Tieni presente che alcuni record DNS sono necessari solo per la configurazione automatica per i client Lync.</span><span class="sxs-lookup"><span data-stu-id="f8570-109">Note that certain DNS records are required only for automatic configuration for Lync clients.</span></span> <span data-ttu-id="f8570-110">Se si prevede di usare gli oggetti Criteri di gruppo per configurare i client Lync, i record associati non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="f8570-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="f8570-111">IMPORTANTE: requisiti della scheda di rete Edge Server</span><span class="sxs-lookup"><span data-stu-id="f8570-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="f8570-112">Per evitare problemi di routing, verificare che siano presenti almeno due schede di rete negli Edge Server e che il gateway predefinito sia impostato solo sulla scheda di rete associata all'interfaccia esterna.</span><span class="sxs-lookup"><span data-stu-id="f8570-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="f8570-113">Ad esempio, come illustrato nella figura scenario Consolidated Edge in scala [consolidata con il bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), il gateway predefinito punta al firewall esterno.</span><span class="sxs-lookup"><span data-stu-id="f8570-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="f8570-114">È possibile configurare due schede di rete in ogni server perimetrale come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f8570-114">You can configure two network adapters in each of your Edge Servers as follows:</span></span>

  - <span data-ttu-id="f8570-115">**Scheda di rete 1 (interfaccia interna)**</span><span class="sxs-lookup"><span data-stu-id="f8570-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="f8570-116">Interfaccia interna con 172.25.33.10 assegnati.</span><span class="sxs-lookup"><span data-stu-id="f8570-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="f8570-117">Nessun gateway predefinito.</span><span class="sxs-lookup"><span data-stu-id="f8570-117">No default gateway.</span></span>
    
    <span data-ttu-id="f8570-118">Verificare che esista una route dalla rete che contiene l'interfaccia interna del server perimetrale a tutte le reti che contengono client o server Lync Server che utilizzano Lync Server, ad esempio da 172.25.33.0 a 192.168.10.0.</span><span class="sxs-lookup"><span data-stu-id="f8570-118">Ensure there is a route from the network containing the Edge Server internal interface to any networks that contain Lync Server clients or servers running Lync Server (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="f8570-119">**Scheda di rete 2 (interfaccia esterna)**</span><span class="sxs-lookup"><span data-stu-id="f8570-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="f8570-120">Alla scheda di rete vengono assegnati tre indirizzi IP pubblici, ad esempio 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge Services.</span><span class="sxs-lookup"><span data-stu-id="f8570-120">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="f8570-121">Gli indirizzi IP assegnati alle interfacce di rete esterne effettive dell'Edge Server possono dipendere dal bilanciamento del carico hardware scelto.</span><span class="sxs-lookup"><span data-stu-id="f8570-121">The IP addresses that are assigned to the actual external network interfaces of the Edge Server may depend on which hardware load balancer you choose.</span></span> <span data-ttu-id="f8570-122">Fare riferimento alla documentazione relativa al dispositivo di bilanciamento del carico hardware per comprendere i requisiti di indirizzo IP effettivi.</span><span class="sxs-lookup"><span data-stu-id="f8570-122">Refer to the documentation for your hardware load balancer to understand the actual IP address requirements.</span></span><BR><span data-ttu-id="f8570-123">È comunque possibile usare un singolo indirizzo IP per tutte le tre interfacce del servizio Edge.</span><span class="sxs-lookup"><span data-stu-id="f8570-123">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="f8570-124">Anche se questo Salva gli indirizzi IP, richiede numeri di porta diversi per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="f8570-124">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="f8570-125">Il numero di porta predefinito è 443/TCP, che garantisce che la maggior parte dei firewall remoti consentirà il traffico.</span><span class="sxs-lookup"><span data-stu-id="f8570-125">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="f8570-126">La modifica dei valori della porta in (ad esempio) 5061/TCP per il servizio Access Edge, 444/TCP per il servizio Web Conferencing Edge e 443/TCP per il servizio A/V Edge può causare problemi per gli utenti remoti in cui un firewall che sta dietro non consente il traffico su 5061/TCP e 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="f8570-126">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="f8570-127">Inoltre, tre indirizzi IP distinti semplificano la risoluzione dei problemi grazie alla possibilità di filtrare in base all'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="f8570-127">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="f8570-128">L'indirizzo IP del servizio Edge di Access è primario con il gateway predefinito impostato su router con accesso a Internet (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="f8570-128">Access Edge service IP address is primary with default gateway set to Internet-facing router (131.107.155.1).</span></span>
    
    <span data-ttu-id="f8570-129">Web Conferencing Edge service e gli indirizzi IP di un/V Edge service secondari.</span><span class="sxs-lookup"><span data-stu-id="f8570-129">Web Conferencing Edge service and A/V Edge service IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="f8570-130">La configurazione di Edge Server con due schede di rete è una delle due opzioni.</span><span class="sxs-lookup"><span data-stu-id="f8570-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="f8570-131">L'altra opzione consiste nell'usare una scheda di rete per il lato interno e tre schede di rete per il lato esterno del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f8570-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="f8570-132">Il vantaggio principale di questa opzione è una scheda di rete distinta per ogni servizio Edge Server e una raccolta di dati potenzialmente più concisa quando è necessaria la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="f8570-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a><span data-ttu-id="f8570-133">Record DNS necessari per il bordo consolidato in scala, bilanciamento del carico hardware (esempio)</span><span class="sxs-lookup"><span data-stu-id="f8570-133">DNS Records Required for Scaled Consolidated Edge, Hardware Load Balanced (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8570-134">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="f8570-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f8570-135">Record FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="f8570-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="f8570-136">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="f8570-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="f8570-137">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="f8570-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8570-138">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="f8570-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f8570-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f8570-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f8570-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="f8570-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="f8570-141">Interfaccia esterna di Access Edge Services (contoso).</span><span class="sxs-lookup"><span data-stu-id="f8570-141">Access Edge service external interface (Contoso).</span></span> <span data-ttu-id="f8570-142">Ripetere la procedura necessaria per tutti i domini SIP con gli utenti abilitati a Lync</span><span class="sxs-lookup"><span data-stu-id="f8570-142">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8570-143">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="f8570-143">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f8570-144">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f8570-144">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f8570-145">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="f8570-145">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="f8570-146">Interfaccia esterna di Web Conferencing Edge service</span><span class="sxs-lookup"><span data-stu-id="f8570-146">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8570-147">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="f8570-147">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f8570-148">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f8570-148">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f8570-149">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="f8570-149">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="f8570-150">Interfaccia esterna di un/V Edge service</span><span class="sxs-lookup"><span data-stu-id="f8570-150">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8570-151">DNS esterno/SRV/443</span><span class="sxs-lookup"><span data-stu-id="f8570-151">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="f8570-152">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="f8570-152">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f8570-153">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f8570-153">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f8570-154">Interfaccia esterna di Access Edge Services.</span><span class="sxs-lookup"><span data-stu-id="f8570-154">Access Edge service external interface.</span></span> <span data-ttu-id="f8570-155">Necessario per la configurazione automatica dei client Lync 2013 e Lync 2010 per l'utilizzo esterno.</span><span class="sxs-lookup"><span data-stu-id="f8570-155">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="f8570-156">Ripetere le esigenze per tutti i domini SIP con gli utenti abilitati a Lync.</span><span class="sxs-lookup"><span data-stu-id="f8570-156">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8570-157">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="f8570-157">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="f8570-158">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="f8570-158">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f8570-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f8570-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f8570-160">Interfaccia esterna SIP Access Edge service necessaria per l'individuazione automatica di DNS dei partner federati noti come "dominio SIP consentito" (chiamata federazione avanzata nelle versioni precedenti).</span><span class="sxs-lookup"><span data-stu-id="f8570-160">SIP Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="f8570-161">Ripetere le operazioni necessarie per tutti i domini SIP con gli utenti abilitati a Lync e i client di Microsoft Lync mobile che usano il servizio di notifica push o il servizio di notifica push Apple</span><span class="sxs-lookup"><span data-stu-id="f8570-161">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8570-162">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="f8570-162">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f8570-163">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f8570-163">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f8570-164">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="f8570-164">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="f8570-165">Interfaccia interna del bordo consolidato</span><span class="sxs-lookup"><span data-stu-id="f8570-165">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

