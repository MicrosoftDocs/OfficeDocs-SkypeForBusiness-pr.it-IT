---
title: Server di sintesi DNS-Edge consolidato in scala con i dispositivi di bilanciamento del carico hardware
description: Server perimetrale consolidato in scala di riepilogo DNS con dispositivi di bilanciamento del carico hardware.
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
ms.openlocfilehash: 59581f435267a7db607e03a8cbf52d21f70897f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570662"
---
# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="9e210-103">Server di sintesi DNS-Edge consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9e210-103">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e210-104">_**Ultimo argomento modificato:** 2013-01-27_</span><span class="sxs-lookup"><span data-stu-id="9e210-104">_**Topic Last Modified:** 2013-01-27_</span></span>

<span data-ttu-id="9e210-105">I requisiti dei record DNS per l'accesso remoto a Lync Server 2013 sono relativamente semplici rispetto a quelli relativi ai certificati e alle porte.</span><span class="sxs-lookup"><span data-stu-id="9e210-105">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="9e210-106">Inoltre, molti record sono facoltativi, a seconda del modo in cui vengono configurati i client che eseguono Lync 2013 e se si Abilita la Federazione.</span><span class="sxs-lookup"><span data-stu-id="9e210-106">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="9e210-107">Per informazioni dettagliate sui requisiti DNS di Lync 2013, vedere [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e210-107">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="9e210-108">Per informazioni dettagliate sulla configurazione automatica dei client Lync 2013 se il DNS split-brain non è configurato, vedere la sezione "configurazione automatica senza DNS split brain" in [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e210-108">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="9e210-109">Nella tabella seguente è incluso un riepilogo dei record DNS necessari per supportare la topologia perimetrale consolidata con scalabilità implementata (bilanciamento del carico hardware) illustrata in Reference Architecture 3: Scaled Consolidated Edge (Hardware Load Balanced).</span><span class="sxs-lookup"><span data-stu-id="9e210-109">The following table contains a summary of the DNS records that are required to support the Scaled Consolidated Edge Topology (Hardware Load Balanced) figure.</span></span> <span data-ttu-id="9e210-110">Si noti che alcuni record DNS sono necessari solo per la configurazione automatica per i client Lync.</span><span class="sxs-lookup"><span data-stu-id="9e210-110">Note that certain DNS records are required only for automatic configuration for Lync clients.</span></span> <span data-ttu-id="9e210-111">Se si prevede di utilizzare gli oggetti Criteri di gruppo per configurare i client Lync, i record associati non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="9e210-111">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="9e210-112">IMPORTANTE: requisiti della scheda di rete per i server perimetrali</span><span class="sxs-lookup"><span data-stu-id="9e210-112">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="9e210-113">Per evitare problemi di routing, verificare che siano presenti almeno due schede di rete nei server perimetrali e che il gateway predefinito sia impostato solo sulla scheda di rete associata all'interfaccia esterna.</span><span class="sxs-lookup"><span data-stu-id="9e210-113">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="9e210-114">Ad esempio, come illustrato nella figura dello scenario perimetrale consolidato con scalabilità verticale in [scala consolidata con bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), il gateway predefinito dovrebbe puntare al firewall esterno.</span><span class="sxs-lookup"><span data-stu-id="9e210-114">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="9e210-115">È possibile configurare due schede di rete in ogni server perimetrale, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9e210-115">You can configure two network adapters in each of your Edge Servers as follows:</span></span>

  - <span data-ttu-id="9e210-116">**Scheda di rete 1 (interfaccia interna)**</span><span class="sxs-lookup"><span data-stu-id="9e210-116">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="9e210-117">Interfaccia interna con indirizzo 172.25.33.10 assegnato.</span><span class="sxs-lookup"><span data-stu-id="9e210-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="9e210-118">Nessun gateway predefinito.</span><span class="sxs-lookup"><span data-stu-id="9e210-118">No default gateway.</span></span>
    
    <span data-ttu-id="9e210-119">Verificare che esista una route dalla rete che contiene l'interfaccia interna del server perimetrale a qualsiasi rete che contiene client o server Lync Server che eseguono Lync Server (ad esempio, da 172.25.33.0 a 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="9e210-119">Ensure there is a route from the network containing the Edge Server internal interface to any networks that contain Lync Server clients or servers running Lync Server (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="9e210-120">**Scheda di rete 2 (interfaccia esterna)**</span><span class="sxs-lookup"><span data-stu-id="9e210-120">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="9e210-121">A questa scheda di rete sono assegnati tre indirizzi IP pubblici, ad esempio 131.107.155.10 per il servizio Access Edge, 131.107.155.20 per il servizio Web Conferencing Edge, 131.107.155.30 per il servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="9e210-121">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="9e210-122">Gli indirizzi IP assegnati alle interfacce di rete esterne effettive del server perimetrale possono dipendere da quale dispositivo di bilanciamento del carico hardware si sceglie.</span><span class="sxs-lookup"><span data-stu-id="9e210-122">The IP addresses that are assigned to the actual external network interfaces of the Edge Server may depend on which hardware load balancer you choose.</span></span> <span data-ttu-id="9e210-123">Fare riferimento alla documentazione del dispositivo di bilanciamento del carico hardware per comprendere i requisiti degli indirizzi IP effettivi.</span><span class="sxs-lookup"><span data-stu-id="9e210-123">Refer to the documentation for your hardware load balancer to understand the actual IP address requirements.</span></span><BR><span data-ttu-id="9e210-124">È possibile, anche se non consigliabile, utilizzare un singolo indirizzo IP per tutte e tre le interfacce dei servizi perimetrali.</span><span class="sxs-lookup"><span data-stu-id="9e210-124">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="9e210-125">Benché in questo modo sia possibile utilizzare meno indirizzi IP, vengono richiesti numeri di porte diversi per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="9e210-125">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="9e210-126">Il numero di porta predefinito è 443/TCP, che garantisce il passaggio del traffico attraverso i firewall più remoti.</span><span class="sxs-lookup"><span data-stu-id="9e210-126">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="9e210-127">Se si modificano i valori delle porte su (ad esempio) 5061/TCP per il servizio Access Edge, 444/TCP per il servizio Web Conferencing Edge e 443/TCP per il servizio A/V Edge potrebbe causare problemi per gli utenti remoti in cui un firewall che sono dietro non consente il traffico su 5061/TCP e 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="9e210-127">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="9e210-128">L'utilizzo di tre indirizzi IP distinti inoltre semplifica la risoluzione dei problemi poiché consente di applicare un filtro in base all'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="9e210-128">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="9e210-129">L'indirizzo IP del servizio Access Edge è primario, con gateway predefinito impostato su router con connessione Internet (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="9e210-129">Access Edge service IP address is primary with default gateway set to Internet-facing router (131.107.155.1).</span></span>
    
    <span data-ttu-id="9e210-130">Servizio Web Conferencing Edge e indirizzi IP del servizio A/V Edge secondario.</span><span class="sxs-lookup"><span data-stu-id="9e210-130">Web Conferencing Edge service and A/V Edge service IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="9e210-131">La configurazione del server perimetrale con due schede di rete è una delle due opzioni.</span><span class="sxs-lookup"><span data-stu-id="9e210-131">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="9e210-132">L'altra opzione consiste nell'utilizzare una scheda di rete per il lato interno e tre schede di rete per il lato esterno del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="9e210-132">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="9e210-133">Il vantaggio principale di questa opzione è una scheda di rete distinta per ogni servizio server perimetrale e una raccolta di dati potenzialmente più concisa quando è necessaria la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="9e210-133">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a><span data-ttu-id="9e210-134">Record DNS necessari per la topologia perimetrale consolidata e bilanciamento del carico hardware (esempio)</span><span class="sxs-lookup"><span data-stu-id="9e210-134">DNS Records Required for Scaled Consolidated Edge, Hardware Load Balanced (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e210-135">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="9e210-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="9e210-136">FQDN/Record DNS</span><span class="sxs-lookup"><span data-stu-id="9e210-136">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="9e210-137">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="9e210-137">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="9e210-138">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="9e210-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e210-139">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="9e210-139">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9e210-140">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e210-140">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9e210-141">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="9e210-141">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="9e210-142">Interfaccia esterna del servizio Access Edge (contoso).</span><span class="sxs-lookup"><span data-stu-id="9e210-142">Access Edge service external interface (Contoso).</span></span> <span data-ttu-id="9e210-143">Ripetere per tutti i domini SIP con utenti abilitati per Lync, se necessario.</span><span class="sxs-lookup"><span data-stu-id="9e210-143">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e210-144">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="9e210-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9e210-145">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e210-145">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9e210-146">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="9e210-146">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="9e210-147">Interfaccia esterna del servizio Web Conferencing Edge</span><span class="sxs-lookup"><span data-stu-id="9e210-147">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e210-148">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="9e210-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9e210-149">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e210-149">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9e210-150">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="9e210-150">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="9e210-151">Interfaccia esterna del servizio A/V Edge</span><span class="sxs-lookup"><span data-stu-id="9e210-151">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e210-152">DNS esterno/SRV/443</span><span class="sxs-lookup"><span data-stu-id="9e210-152">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="9e210-153">_sip _sip._tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="9e210-153">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9e210-154">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e210-154">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9e210-155">Interfaccia esterna del servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="9e210-155">Access Edge service external interface.</span></span> <span data-ttu-id="9e210-156">Necessario per la configurazione automatica dei client Lync 2013 e Lync 2010 per funzionare esternamente.</span><span class="sxs-lookup"><span data-stu-id="9e210-156">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="9e210-157">Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync.</span><span class="sxs-lookup"><span data-stu-id="9e210-157">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e210-158">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="9e210-158">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="9e210-159">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="9e210-159">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9e210-160">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e210-160">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9e210-161">Interfaccia esterna del servizio SIP Access Edge necessaria per l'individuazione automatica di DNS dei partner federati noti come "dominio SIP consentito" (denominato Federazione avanzata nelle versioni precedenti).</span><span class="sxs-lookup"><span data-stu-id="9e210-161">SIP Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="9e210-162">Ripetere quanto necessario per tutti i domini SIP con gli utenti abilitati per Lync e i client Microsoft Lync mobile che utilizzano il servizio di notifica push o il servizio di notifica push di Apple</span><span class="sxs-lookup"><span data-stu-id="9e210-162">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e210-163">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="9e210-163">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9e210-164">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="9e210-164">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="9e210-165">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="9e210-165">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="9e210-166">Interfaccia interna perimetrale consolidata</span><span class="sxs-lookup"><span data-stu-id="9e210-166">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

