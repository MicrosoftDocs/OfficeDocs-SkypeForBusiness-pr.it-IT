---
title: Riepilogo di DNS - singola topologia perimetrale consolidata con indirizzi IP pubblici
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3578bc7b1668bf8cb2268ed079e558e1cf1761
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="b8ad5-102">Riepilogo di DNS - singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8ad5-102">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8ad5-103">_**Argomento Ultima modifica:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="b8ad5-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="b8ad5-104">I requisiti dei record DNS per l'accesso remoto a Lync Server 2013 sono abbastanza semplici rispetto a quelli per i certificati e le porte.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="b8ad5-105">Inoltre, molti record sono facoltativi, a seconda di come si configurano i client che usano Lync 2013 e se si Abilita la Federazione.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="b8ad5-106">Per informazioni dettagliate sui requisiti DNS di Lync 2013, vedere [determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8ad5-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="b8ad5-107">Per informazioni dettagliate sulla configurazione automatica dei client in cui è in uso Lync 2013 se non è configurato il DNS split-brain, vedere "configurazione automatica senza DNS split-brain" in [determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8ad5-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="b8ad5-108">La tabella seguente contiene un riepilogo dei record DNS necessari per supportare la singola topologia perimetrale consolidata visualizzata nella figura singola topologia perimetrale consolidata.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="b8ad5-109">Tieni presente che alcuni record DNS sono necessari solo per la configurazione automatica dei client Lync 2013 e Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="b8ad5-110">Se si prevede di usare gli oggetti Criteri di gruppo per configurare i client Lync, i record di configurazione automatica associati non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="b8ad5-111">IMPORTANTE: requisiti della scheda di rete Edge Server</span><span class="sxs-lookup"><span data-stu-id="b8ad5-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="b8ad5-112">Per evitare problemi di routing, verificare che siano presenti almeno due schede di rete negli Edge Server e che il gateway predefinito sia impostato solo sulla scheda di rete associata all'interfaccia esterna.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="b8ad5-113">Ad esempio, come illustrato nella topologia di Edge consolidato con indirizzi IP pubblici in un [unico bordo consolidato con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), il gateway predefinito punta al router esterno nel perimetro Internet o nel firewall in grado di specificare indirizzi IP pubblici.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-113">For example, as shown in the Single Consolidated Edge Topology with Public IP Addresses figure in [Single consolidated edge with public IP addresses in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), the default gateway would point to the external router at your Internet perimeter or firewall that can provide a public IP addresses.</span></span> <span data-ttu-id="b8ad5-114">La relazione di rete per le interfacce Edge Server è una relazione di route anziché una relazione NAT.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-114">The network relationship for Edge Server interfaces is a route relationship instead of a NAT relationship.</span></span>

<span data-ttu-id="b8ad5-115">È possibile configurare due schede di rete nel server perimetrale nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b8ad5-115">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="b8ad5-116">**Scheda di rete 1 (interfaccia interna)**</span><span class="sxs-lookup"><span data-stu-id="b8ad5-116">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="b8ad5-117">Interfaccia interna con 172.25.33.10 assegnati.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="b8ad5-118">Nessun gateway predefinito è definito.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="b8ad5-119">Verificare che esista una route dalla rete che contiene l'interfaccia interna di Edge a tutte le reti che contengono server che includono client Lync Server 2013 o Lync Server 2013, ad esempio da 172.25.33.0 a 192.168.10.0.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="b8ad5-120">**Scheda di rete 2 (interfaccia esterna)**</span><span class="sxs-lookup"><span data-stu-id="b8ad5-120">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="b8ad5-121">Alla scheda di rete vengono assegnati tre indirizzi IP pubblici, ad esempio 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-121">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b8ad5-122">È comunque possibile usare un singolo indirizzo IP per tutte le tre interfacce del servizio Edge.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-122">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="b8ad5-123">Anche se questo Salva gli indirizzi IP, richiede numeri di porta diversi per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-123">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="b8ad5-124">Il numero di porta predefinito è 443/TCP, che garantisce che la maggior parte dei firewall remoti consentirà il traffico.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-124">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="b8ad5-125">La modifica dei valori della porta in (ad esempio) 5061/TCP per l'Access Edge, 444/TCP per il Web Conferencing Edge e 443/TCP per il Edge AV può causare problemi per gli utenti remoti in cui un firewall che si trovano dietro non consente il traffico su 5061/TCP e 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-125">Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="b8ad5-126">Inoltre, tre indirizzi IP distinti semplificano la risoluzione dei problemi grazie alla possibilità di filtrare in base all'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-126">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="b8ad5-127">L'indirizzo IP pubblico di Access Edge è primario con il set di gateway predefinito per il router pubblico (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="b8ad5-127">The Access Edge public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="b8ad5-128">Gli indirizzi IP pubblici di Web Conferencing e A/V Edge sono indirizzi IP aggiuntivi nella sezione **Advanced** delle proprietà di **Internet Protocol versione 4 (TCP/IPv4)** e **Internet Protocol versione 6 (TCP/IPv6)** delle **proprietà di connessione all'area locale** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-128">Web conferencing and A/V Edge public IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="b8ad5-129">La configurazione di Edge Server con due schede di rete è una delle due opzioni.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-129">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="b8ad5-130">L'altra opzione consiste nell'usare una scheda di rete per il lato interno e tre schede di rete per il lato esterno del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-130">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="b8ad5-131">Il vantaggio principale di questa opzione è una scheda di rete distinta per ogni servizio Edge Server e una raccolta di dati potenzialmente più concisa quando è necessaria la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="b8ad5-131">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a><span data-ttu-id="b8ad5-132">Record DNS necessari per un singolo bordo consolidato con indirizzi IP pubblici (ad esempio)</span><span class="sxs-lookup"><span data-stu-id="b8ad5-132">DNS Records Required for Single Consolidated Edge with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8ad5-133">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="b8ad5-133">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="b8ad5-134">Record FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="b8ad5-134">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="b8ad5-135">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="b8ad5-135">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="b8ad5-136">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="b8ad5-136">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8ad5-137">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="b8ad5-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-138">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8ad5-138">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-139">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="b8ad5-139">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-140">Ripetizione dell'interfaccia esterna di Access Edge (contoso), se necessario per tutti i domini SIP con gli utenti abilitati a Lync</span><span class="sxs-lookup"><span data-stu-id="b8ad5-140">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8ad5-141">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="b8ad5-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-142">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8ad5-142">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-143">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="b8ad5-143">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-144">Interfaccia esterna di Web Conferencing Edge</span><span class="sxs-lookup"><span data-stu-id="b8ad5-144">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8ad5-145">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="b8ad5-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-146">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8ad5-146">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-147">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="b8ad5-147">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-148">Interfaccia esterna Edge A/V</span><span class="sxs-lookup"><span data-stu-id="b8ad5-148">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8ad5-149">DNS esterno/SRV/443</span><span class="sxs-lookup"><span data-stu-id="b8ad5-149">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-150">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="b8ad5-150">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-151">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8ad5-151">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-152">Interfaccia esterna di Access Edge.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-152">Access Edge external interface.</span></span> <span data-ttu-id="b8ad5-153">Necessario per la configurazione automatica dei client Lync 2013 e Lync 2010 per l'utilizzo esterno.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-153">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="b8ad5-154">Ripetere le esigenze per tutti i domini SIP con gli utenti abilitati a Lync.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-154">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8ad5-155">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="b8ad5-155">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-156">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="b8ad5-156">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-157">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8ad5-157">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-158">Interfaccia esterna di Access Edge SIP necessaria per l'individuazione automatica di DNS dei partner federati noti come "dominio SIP consentito" (chiamata federazione avanzata nelle versioni precedenti). Ripetere la procedura necessaria per tutti i domini SIP con gli utenti abilitati a Lync</span><span class="sxs-lookup"><span data-stu-id="b8ad5-158">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8ad5-159">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="b8ad5-159">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-160">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b8ad5-160">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-161">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="b8ad5-161">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-162">Interfaccia interna del bordo consolidato</span><span class="sxs-lookup"><span data-stu-id="b8ad5-162">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="b8ad5-163">I record elencati nella tabella precedente vengono visualizzati con un'estensione <EM>.NET</EM> o con estensione <EM>com</EM> per evidenziare la zona in cui devono trovarsi se non si usa il DNS split-brain.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-163">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="b8ad5-164">Se si usa il DNS con suddivisione in cervello, tutti i record si troverebbero nella stessa zona, con l'unica distinzione che indica se si trovano nella versione interna o esterna.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-164">If you are using split-brain DNS, all records would be in the same zone, with the only distinction being whether they are in the internal or external version.</span></span> <span data-ttu-id="b8ad5-165">Per informazioni dettagliate, vedere "DNS con suddivisione del cervello" in <A href="lync-server-2013-determine-dns-requirements.md">determinare i requisiti DNS per Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-165">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="b8ad5-166">Record necessari per la Federazione</span><span class="sxs-lookup"><span data-stu-id="b8ad5-166">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8ad5-167">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="b8ad5-167">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="b8ad5-168">FQDN</span><span class="sxs-lookup"><span data-stu-id="b8ad5-168">FQDN</span></span></th>
<th><span data-ttu-id="b8ad5-169">Indirizzo IP/record host FQDN</span><span class="sxs-lookup"><span data-stu-id="b8ad5-169">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="b8ad5-170">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="b8ad5-170">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8ad5-171">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="b8ad5-171">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-172">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="b8ad5-172">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-173">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8ad5-173">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-174">Interfaccia esterna di Access Edge SIP necessaria per l'individuazione automatica del DNS della Federazione ad altri potenziali partner federativi ed è nota come "domini SIP consentiti" (chiamata federazione avanzata nelle versioni precedenti). Ripetere la procedura necessaria per tutti i domini SIP con gli utenti abilitati a Lync</span><span class="sxs-lookup"><span data-stu-id="b8ad5-174">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="b8ad5-175">Questo record SRV è necessario per la mobilità e la camera di compensazione delle notifiche push</span><span class="sxs-lookup"><span data-stu-id="b8ad5-175">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="b8ad5-176">Riepilogo DNS per il protocollo di messaggistica e presenza estensibile</span><span class="sxs-lookup"><span data-stu-id="b8ad5-176">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8ad5-177">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="b8ad5-177">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="b8ad5-178">FQDN</span><span class="sxs-lookup"><span data-stu-id="b8ad5-178">FQDN</span></span></th>
<th><span data-ttu-id="b8ad5-179">Indirizzo IP/record host FQDN</span><span class="sxs-lookup"><span data-stu-id="b8ad5-179">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="b8ad5-180">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="b8ad5-180">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8ad5-181">DNS esterno/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="b8ad5-181">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-182">_xmpp-server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="b8ad5-182">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-183">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8ad5-183">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-184">Interfaccia esterna proxy XMPP nel pool di servizi o Edge di Access. Ripetere l'impostazione necessaria per tutti i domini SIP interni con gli utenti abilitati a Lync in cui è consentito il contatto con i contatti XMPP tramite la configurazione dei criteri di accesso esterno tramite un criterio globale, il criterio del sito in cui si trova l'utente o i criteri degli utenti applicati alla Utenti abilitati per Lync.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-184">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="b8ad5-185">Un dominio XMPP consentito deve essere configurato anche nei criteri dei partner federati XMPP.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-185">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="b8ad5-186">Vedere gli argomenti in <strong>vedere anche</strong> per ulteriori dettagli</span><span class="sxs-lookup"><span data-stu-id="b8ad5-186">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8ad5-187">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="b8ad5-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-188">xmpp.contoso.com (ad esempio)</span><span class="sxs-lookup"><span data-stu-id="b8ad5-188">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-189">Indirizzo IP del servizio Access Edge nell'Edge Server o nel pool di Edge che ospita il proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="b8ad5-189">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="b8ad5-190">Punta al servizio di Access Edge o al pool di Edge che ospita il servizio proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="b8ad5-190">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="b8ad5-191">In genere, il record SRV creato punterà al record host (A o AAAA)</span><span class="sxs-lookup"><span data-stu-id="b8ad5-191">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

