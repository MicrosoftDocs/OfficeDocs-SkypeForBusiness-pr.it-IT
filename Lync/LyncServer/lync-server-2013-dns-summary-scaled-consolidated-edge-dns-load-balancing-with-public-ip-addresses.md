---
title: 'Lync Server 2013: Consolidated Edge in scala di riepilogo DNS, bilanciamento del carico DNS con indirizzi IP pubblici'
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
ms.openlocfilehash: 4f2cd6350a74f4dd054d30d81ac13c15c829d122
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="41614-102">Server perimetrale consolidato in scala di riepilogo DNS, bilanciamento del carico DNS con indirizzi IP pubblici in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="41614-102">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41614-103">_**Ultimo argomento modificato:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="41614-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="41614-104">I requisiti dei record DNS per l'accesso remoto a Lync Server 2013 sono relativamente semplici rispetto a quelli relativi ai certificati e alle porte.</span><span class="sxs-lookup"><span data-stu-id="41614-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="41614-105">Inoltre, molti record sono facoltativi, a seconda del modo in cui vengono configurati i client che eseguono Lync 2013 e se si Abilita la Federazione.</span><span class="sxs-lookup"><span data-stu-id="41614-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="41614-106">Per informazioni dettagliate sui requisiti DNS di Lync 2013, vedere [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41614-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="41614-107">Per informazioni dettagliate sulla configurazione automatica dei client Lync 2013 se il DNS split-brain non è configurato, vedere la sezione "configurazione automatica senza DNS split brain" in [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41614-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="41614-108">Nella tabella seguente viene fornito un riepilogo dei record DNS necessari per supportare la topologia perimetrale consolidata singola illustrata nella relativa figura.</span><span class="sxs-lookup"><span data-stu-id="41614-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="41614-109">Si noti che alcuni record DNS sono necessari solo per la configurazione automatica dei client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="41614-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="41614-110">Se si prevede di utilizzare gli oggetti Criteri di gruppo per configurare i client Lync, i record associati non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="41614-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="41614-111">IMPORTANTE: requisiti della scheda di rete per i server perimetrali</span><span class="sxs-lookup"><span data-stu-id="41614-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="41614-112">Per evitare problemi di routing, verificare che siano presenti almeno due schede di rete nei server perimetrali e che il gateway predefinito sia impostato solo sulla scheda di rete associata all'interfaccia esterna.</span><span class="sxs-lookup"><span data-stu-id="41614-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="41614-113">Ad esempio, come illustrato nella figura dello scenario dei server perimetrali in scala consolidato in [scala consolidata perimetrale, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , il gateway predefinito dovrebbe puntare al firewall esterno.</span><span class="sxs-lookup"><span data-stu-id="41614-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="41614-114">È possibile configurare due schede di rete in ogni server perimetrale, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="41614-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="41614-115">**Scheda di rete 1 - Nodo 1 (interfaccia interna)**</span><span class="sxs-lookup"><span data-stu-id="41614-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="41614-116">Interfaccia interna con indirizzo 172.25.33.10 assegnato.</span><span class="sxs-lookup"><span data-stu-id="41614-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="41614-117">Nessun gateway predefinito definito.</span><span class="sxs-lookup"><span data-stu-id="41614-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="41614-118">Verificare che esista una route dalla rete che contiene l'interfaccia interna del server perimetrale a qualsiasi rete che contiene server che eseguono i client Lync 2013 o Lync Server 2013 (ad esempio, da 172.25.33.0 a 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="41614-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="41614-119">**Scheda di rete 1 - Nodo 2 (interfaccia interna)**</span><span class="sxs-lookup"><span data-stu-id="41614-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="41614-120">Interfaccia interna con indirizzo 172.25.33.11 assegnato.</span><span class="sxs-lookup"><span data-stu-id="41614-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="41614-121">Non è specificato alcun gateway predefinito.</span><span class="sxs-lookup"><span data-stu-id="41614-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="41614-122">Verificare che esista una route dalla rete che contiene l'interfaccia interna del server perimetrale a qualsiasi rete che contiene server che eseguono i client Lync 2013 o Lync Server 2013 (ad esempio, da 172.25.33.0 a 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="41614-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="41614-123">**Scheda di rete 2 - Nodo 1 (interfaccia esterna)**</span><span class="sxs-lookup"><span data-stu-id="41614-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="41614-124">A questa scheda di rete sono assegnati tre indirizzi IP privati, ad esempio 131.107.155.10 per il servizio Access Edge, 131.107.155.20 per il servizio Web Conferencing Edge, 131.107.155.30 per il servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="41614-124">Three private IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <span data-ttu-id="41614-125">L'indirizzo IP pubblico del servizio Access Edge è primario, con gateway predefinito impostato sul router pubblico (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="41614-125">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="41614-126">I servizi Web Conferencing Edge e gli indirizzi IP privati del servizio A/V Edge sono indirizzi IP aggiuntivi nella sezione **Advanced** delle proprietà del **protocollo Internet versione 4 (TCP/IPv4)** e del **protocollo Internet versione 6 (TCP/IPv6)** delle **proprietà della connessione all'area locale** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="41614-126">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="41614-127">È possibile, anche se non consigliabile, utilizzare un singolo indirizzo IP per tutte e tre le interfacce dei servizi perimetrali.</span><span class="sxs-lookup"><span data-stu-id="41614-127">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="41614-128">Benché in questo modo sia possibile utilizzare meno indirizzi IP, vengono richiesti numeri di porte diversi per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="41614-128">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="41614-129">Il numero di porta predefinito è 443/TCP, che garantisce il passaggio del traffico attraverso i firewall più remoti.</span><span class="sxs-lookup"><span data-stu-id="41614-129">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="41614-130">Se si modificano i valori delle porte su (ad esempio) 5061/TCP per il servizio Access Edge, 444/TCP per il servizio Web Conferencing Edge e 443/TCP per il servizio A/V Edge potrebbe causare problemi per gli utenti remoti in cui un firewall che sono dietro non consente il traffico su 5061/TCP e 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="41614-130">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="41614-131">L'utilizzo di tre indirizzi IP distinti inoltre semplifica la risoluzione dei problemi poiché consente di applicare un filtro in base all'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="41614-131">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>

  - <span data-ttu-id="41614-132">**Scheda di rete 2 - Nodo 2 (interfaccia esterna)**</span><span class="sxs-lookup"><span data-stu-id="41614-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="41614-133">A questa scheda di rete sono assegnati tre indirizzi IP privati, ad esempio 131.107.155.11 per il servizio Access Edge, 131.107.155.21 per il servizio Web Conferencing Edge, 131.107.155.31 per il servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="41614-133">Three private IP addresses are assigned to this network adapter, for example 131.107.155.11 for Access Edge service, 131.107.155.21 for Web Conferencing Edge service, 131.107.155.31 for A/V Edge service.</span></span>
    
    <span data-ttu-id="41614-134">L'indirizzo IP pubblico del servizio Access Edge è primario, con gateway predefinito impostato sul router pubblico (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="41614-134">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="41614-135">I servizi Web Conferencing Edge e gli indirizzi IP privati del servizio A/V Edge sono indirizzi IP aggiuntivi nella sezione **Advanced** delle proprietà del **protocollo Internet versione 4 (TCP/IPv4)** e del **protocollo Internet versione 6 (TCP/IPv6)** delle **proprietà della connessione all'area locale** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="41614-135">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="41614-136">La configurazione del server perimetrale con due schede di rete è una delle due opzioni.</span><span class="sxs-lookup"><span data-stu-id="41614-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="41614-137">L'altra opzione consiste nell'utilizzare una scheda di rete per il lato interno e tre schede di rete per il lato esterno del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="41614-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="41614-138">Il vantaggio principale di questa opzione è una scheda di rete distinta per ogni servizio server perimetrale e una raccolta di dati potenzialmente più concisa quando è necessaria la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="41614-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a><span data-ttu-id="41614-139">Record DNS necessari per topologia perimetrale consolidata con scalabilità implementata e bilanciamento del carico DNS con indirizzi IP pubblici (esempio)</span><span class="sxs-lookup"><span data-stu-id="41614-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41614-140">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="41614-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="41614-141">FQDN/Record DNS</span><span class="sxs-lookup"><span data-stu-id="41614-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="41614-142">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="41614-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="41614-143">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="41614-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41614-144">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="41614-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="41614-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="41614-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="41614-146">131.107.155.10 e 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="41614-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="41614-147">Ripetizione dell'interfaccia esterna del servizio Access Edge (contoso) come necessario per tutti i domini SIP con gli utenti abilitati per Lync</span><span class="sxs-lookup"><span data-stu-id="41614-147">Access Edge service external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41614-148">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="41614-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="41614-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="41614-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="41614-150">131.107.155.20 e 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="41614-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="41614-151">Interfaccia esterna del servizio Web Conferencing Edge</span><span class="sxs-lookup"><span data-stu-id="41614-151">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41614-152">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="41614-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="41614-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="41614-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="41614-154">131.107.155.30 e 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="41614-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="41614-155">Interfaccia esterna del servizio A/V Edge</span><span class="sxs-lookup"><span data-stu-id="41614-155">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41614-156">DNS esterno/SRV/443</span><span class="sxs-lookup"><span data-stu-id="41614-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="41614-157">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="41614-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="41614-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="41614-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="41614-159">Interfaccia esterna del servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="41614-159">Access Edge service external interface.</span></span> <span data-ttu-id="41614-160">Necessario per la configurazione automatica dei client Lync 2013 e Lync 2010 per funzionare esternamente.</span><span class="sxs-lookup"><span data-stu-id="41614-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="41614-161">Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync.</span><span class="sxs-lookup"><span data-stu-id="41614-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41614-162">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="41614-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="41614-163">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="41614-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="41614-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="41614-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="41614-165">Interfaccia esterna del servizio Access Edge necessario per l'individuazione automatica del DNS dei partner federati noti come "dominio SIP consentito" (denominato Federazione avanzata nelle versioni precedenti).</span><span class="sxs-lookup"><span data-stu-id="41614-165">Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="41614-166">Ripetere per tutti i domini SIP con utenti abilitati per Lync, se necessario.</span><span class="sxs-lookup"><span data-stu-id="41614-166">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41614-167">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="41614-167">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="41614-168">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="41614-168">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="41614-169">172.25.33.10 e 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="41614-169">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="41614-170">Interfaccia interna del server perimetrale consolidato.</span><span class="sxs-lookup"><span data-stu-id="41614-170">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="41614-171">Record necessari per la federazione</span><span class="sxs-lookup"><span data-stu-id="41614-171">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41614-172">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="41614-172">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="41614-173">FQDN</span><span class="sxs-lookup"><span data-stu-id="41614-173">FQDN</span></span></th>
<th><span data-ttu-id="41614-174">Indirizzo IP/FQDN record host</span><span class="sxs-lookup"><span data-stu-id="41614-174">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="41614-175">Si mappa a/Commenti</span><span class="sxs-lookup"><span data-stu-id="41614-175">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41614-176">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="41614-176">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="41614-177">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="41614-177">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="41614-178">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="41614-178">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="41614-179">Interfaccia esterna del servizio Access Edge SIP necessaria per l'individuazione automatica dei DNS della Federazione verso altri potenziali partner di federazione ed è nota come "domini SIP consentiti" (denominata Federazione avanzata nelle versioni precedenti).</span><span class="sxs-lookup"><span data-stu-id="41614-179">SIP Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="41614-180">Ripetere quanto necessario per tutti i domini SIP con gli utenti abilitati per Lync e i client Microsoft Lync mobile che utilizzano il servizio di notifica push o il servizio di notifica push di Apple</span><span class="sxs-lookup"><span data-stu-id="41614-180">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="41614-181">Riepilogo DNS per il protocollo XMPP</span><span class="sxs-lookup"><span data-stu-id="41614-181">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41614-182">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="41614-182">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="41614-183">FQDN</span><span class="sxs-lookup"><span data-stu-id="41614-183">FQDN</span></span></th>
<th><span data-ttu-id="41614-184">Indirizzo IP/FQDN record host</span><span class="sxs-lookup"><span data-stu-id="41614-184">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="41614-185">Si mappa a/Commenti</span><span class="sxs-lookup"><span data-stu-id="41614-185">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41614-186">DNS esterno/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="41614-186">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="41614-187">_xmpp-server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="41614-187">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="41614-188">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="41614-188">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="41614-189">Interfaccia esterna del proxy XMPP nel servizio Access Edge o nel pool di server perimetrali. Ripetere quanto necessario per tutti i domini SIP interni con gli utenti abilitati per Lync, in cui è consentito il contatto con i contatti XMPP tramite la configurazione del criterio di accesso esterno tramite un criterio globale, il criterio del sito in cui si trova l'utente o il criterio utente applicato all' Utente abilitato per Lync.</span><span class="sxs-lookup"><span data-stu-id="41614-189">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="41614-190">Un dominio XMPP consentito deve inoltre essere configurato nel criterio dei partner XMPP federati.</span><span class="sxs-lookup"><span data-stu-id="41614-190">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="41614-191">Per informazioni dettagliate, vedere gli argomenti in <strong>Vedere anche</strong></span><span class="sxs-lookup"><span data-stu-id="41614-191">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41614-192">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="41614-192">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="41614-193">xmpp.contoso.com (esempio)</span><span class="sxs-lookup"><span data-stu-id="41614-193">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="41614-194">Indirizzo IP del servizio Access Edge nel server perimetrale o nel pool perimetrale che ospita il proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="41614-194">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="41614-195">Punta al servizio Access Edge o al pool di server perimetrali che ospita il servizio proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="41614-195">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="41614-196">Il record SRV creato punterà a questo record host (A o AAAA).</span><span class="sxs-lookup"><span data-stu-id="41614-196">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

