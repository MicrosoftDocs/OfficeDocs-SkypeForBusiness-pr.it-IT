---
title: Riepilogo DNS-singolo server perimetrale consolidato con indirizzi IP pubblici
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
ms.openlocfilehash: 622cb9811e33762bf40c05dfa5e5f0ab644b51aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="56dbb-102">Riepilogo DNS-singolo server perimetrale consolidato con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56dbb-102">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56dbb-103">_**Ultimo argomento modificato:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="56dbb-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="56dbb-104">I requisiti dei record DNS per l'accesso remoto a Lync Server 2013 sono relativamente semplici rispetto a quelli relativi ai certificati e alle porte.</span><span class="sxs-lookup"><span data-stu-id="56dbb-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="56dbb-105">Inoltre, molti record sono facoltativi, a seconda del modo in cui vengono configurati i client che eseguono Lync 2013 e se si Abilita la Federazione.</span><span class="sxs-lookup"><span data-stu-id="56dbb-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="56dbb-106">Per informazioni dettagliate sui requisiti DNS di Lync 2013, vedere [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56dbb-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="56dbb-107">Per informazioni dettagliate sulla configurazione automatica dei client che eseguono Lync 2013 se il DNS split-brain non è configurato, vedere la sezione relativa alla configurazione automatica senza DNS split-brain in [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56dbb-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="56dbb-108">Nella tabella seguente viene fornito un riepilogo dei record DNS necessari per supportare la topologia perimetrale consolidata singola illustrata nella relativa figura.</span><span class="sxs-lookup"><span data-stu-id="56dbb-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="56dbb-109">Si noti che alcuni record DNS sono necessari solo per la configurazione automatica dei client Lync 2013 e Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="56dbb-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="56dbb-110">Se si prevede di utilizzare gli oggetti Criteri di gruppo per configurare i client Lync, i record di configurazione automatica associati non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="56dbb-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="56dbb-111">IMPORTANTE: requisiti della scheda di rete per i server perimetrali</span><span class="sxs-lookup"><span data-stu-id="56dbb-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="56dbb-112">Per evitare problemi di routing, verificare che siano presenti almeno due schede di rete nei server perimetrali e che il gateway predefinito sia impostato solo sulla scheda di rete associata all'interfaccia esterna.</span><span class="sxs-lookup"><span data-stu-id="56dbb-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="56dbb-113">Ad esempio, come illustrato nella singola topologia perimetrale consolidata con indirizzi IP pubblici in un [unico perimetro consolidato con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), il gateway predefinito potrebbe puntare al router esterno nel perimetro o nel firewall Internet che può fornire un indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="56dbb-113">For example, as shown in the Single Consolidated Edge Topology with Public IP Addresses figure in [Single consolidated edge with public IP addresses in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), the default gateway would point to the external router at your Internet perimeter or firewall that can provide a public IP addresses.</span></span> <span data-ttu-id="56dbb-114">La relazione di rete per le interfacce del server perimetrale è una relazione di route anziché una relazione NAT.</span><span class="sxs-lookup"><span data-stu-id="56dbb-114">The network relationship for Edge Server interfaces is a route relationship instead of a NAT relationship.</span></span>

<span data-ttu-id="56dbb-115">È possibile configurare due schede di rete all'interno del server perimetrale come segue:</span><span class="sxs-lookup"><span data-stu-id="56dbb-115">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="56dbb-116">**Scheda di rete 1 (interfaccia interna)**</span><span class="sxs-lookup"><span data-stu-id="56dbb-116">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="56dbb-117">Interfaccia interna con indirizzo 172.25.33.10 assegnato.</span><span class="sxs-lookup"><span data-stu-id="56dbb-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="56dbb-118">Non è specificato alcun gateway predefinito.</span><span class="sxs-lookup"><span data-stu-id="56dbb-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="56dbb-119">Verificare che esista una route dalla rete che contiene l'interfaccia interna del server perimetrale a qualsiasi rete che contiene server che eseguono i client Lync 2013 o Lync Server 2013 (ad esempio, da 172.25.33.0 a 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="56dbb-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="56dbb-120">**Scheda di rete 2 (interfaccia esterna)**</span><span class="sxs-lookup"><span data-stu-id="56dbb-120">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="56dbb-121">A questa scheda di rete sono assegnati tre indirizzi IP pubblici, ad esempio 131.107.155.10 per Access Edge, 131.107.155.20 per Web Conferencing Edge, 131.107.155.30 per AV Edge.</span><span class="sxs-lookup"><span data-stu-id="56dbb-121">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="56dbb-p104">È possibile, sebbene non consigliabile, utilizzare un unico indirizzo IP per le tre interfacce del servizio Edge. Sebbene in questo modo sia possibile risparmiare indirizzi IP, è necessario un numero di porta separato per ciascun servizio. Il numero di porta predefinito è 443/TCP, porta questa che permette anche ai firewall più remoti di consentire il traffico. Se si cambia il valore delle porte, come ad esempio 5061/TCP per l'Access Edge, 444/TCP per il Web Conferencing Edge e 443/TCP A/V Edge, si potrebbero causare problemi agli utenti remoti qualora il firewall dietro il quale essi si trovano non consentisse il traffico su 5061/TCP e 444/TCP. Inoltre, la presenza di tre indirizzi IP differenti semplifica la risoluzione dei problemi, poiché questa è in grado di filtrare a seconda dell'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="56dbb-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="56dbb-127">L'indirizzo IP pubblico di Access Edge è quello primario, con il gateway predefinito impostato sul router pubblico (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="56dbb-127">The Access Edge public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="56dbb-128">Gli indirizzi IP pubblici di Web conferencing e A/V Edge sono indirizzi IP aggiuntivi nella sezione **Avanzate** delle proprietà di **Internet Protocol Version 4 (TCP/IPv4)** e **Internet Protocol Version 6 (TCP/IPv6)** delle **Proprietà LAN** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="56dbb-128">Web conferencing and A/V Edge public IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="56dbb-129">La configurazione del server perimetrale con due schede di rete è una delle due opzioni.</span><span class="sxs-lookup"><span data-stu-id="56dbb-129">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="56dbb-130">L'altra opzione consiste nell'utilizzare una scheda di rete per il lato interno e tre schede di rete per il lato esterno del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="56dbb-130">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="56dbb-131">Il vantaggio principale di questa opzione è una scheda di rete distinta per ogni servizio server perimetrale e una raccolta di dati potenzialmente più concisa quando è necessaria la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="56dbb-131">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a><span data-ttu-id="56dbb-132">Record DNS necessari per la topologia perimetrale singola con indirizzi IP pubblici (esempio)</span><span class="sxs-lookup"><span data-stu-id="56dbb-132">DNS Records Required for Single Consolidated Edge with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56dbb-133">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="56dbb-133">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="56dbb-134">FQDN/Record DNS</span><span class="sxs-lookup"><span data-stu-id="56dbb-134">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="56dbb-135">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="56dbb-135">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="56dbb-136">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="56dbb-136">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56dbb-137">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="56dbb-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="56dbb-138">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="56dbb-138">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="56dbb-139">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="56dbb-139">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="56dbb-140">Interfaccia esterna di Access Edge (Contoso). Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync</span><span class="sxs-lookup"><span data-stu-id="56dbb-140">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56dbb-141">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="56dbb-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="56dbb-142">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="56dbb-142">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="56dbb-143">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="56dbb-143">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="56dbb-144">Interfaccia esterna Web Conferencing Edge Server</span><span class="sxs-lookup"><span data-stu-id="56dbb-144">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56dbb-145">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="56dbb-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="56dbb-146">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="56dbb-146">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="56dbb-147">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="56dbb-147">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="56dbb-148">Interfaccia esterna A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="56dbb-148">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56dbb-149">DNS esterno/SRV/443</span><span class="sxs-lookup"><span data-stu-id="56dbb-149">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="56dbb-150">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="56dbb-150">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="56dbb-151">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="56dbb-151">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="56dbb-152">Interfaccia esterna di Access Edge.</span><span class="sxs-lookup"><span data-stu-id="56dbb-152">Access Edge external interface.</span></span> <span data-ttu-id="56dbb-153">Necessario per la configurazione automatica dei client Lync 2013 e Lync 2010 per funzionare esternamente.</span><span class="sxs-lookup"><span data-stu-id="56dbb-153">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="56dbb-154">Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync.</span><span class="sxs-lookup"><span data-stu-id="56dbb-154">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56dbb-155">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="56dbb-155">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="56dbb-156">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="56dbb-156">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="56dbb-157">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="56dbb-157">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="56dbb-158">Interfaccia esterna SIP di Access Edge. Necessaria per l'individuazione DNS automatica di partner federati, nota come dominio SIP consentito, nonché come federazione avanzata nelle versioni precedenti. Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync.</span><span class="sxs-lookup"><span data-stu-id="56dbb-158">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56dbb-159">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="56dbb-159">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="56dbb-160">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="56dbb-160">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="56dbb-161">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="56dbb-161">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="56dbb-162">Interfaccia interna perimetrale consolidata</span><span class="sxs-lookup"><span data-stu-id="56dbb-162">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="56dbb-163">I record elencati nella tabella precedente sono visualizzati con estensione <EM>net</EM> o <EM>com</EM>, per evidenziare la zona in cui devono trovarsi se non si utilizza il DNS di tipo split brain.</span><span class="sxs-lookup"><span data-stu-id="56dbb-163">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="56dbb-164">Se si utilizza il DNS di tipo split brain, tutti i record devono trovarsi nella stessa zona, con l'unica distinzione tra versione interna ed esterna.</span><span class="sxs-lookup"><span data-stu-id="56dbb-164">If you are using split-brain DNS, all records would be in the same zone, with the only distinction being whether they are in the internal or external version.</span></span> <span data-ttu-id="56dbb-165">Per informazioni dettagliate, vedere "DNS split-brain" in <A href="lync-server-2013-determine-dns-requirements.md">determine DNS requirements for Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="56dbb-165">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="56dbb-166">Record necessari per la federazione</span><span class="sxs-lookup"><span data-stu-id="56dbb-166">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56dbb-167">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="56dbb-167">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="56dbb-168">FQDN</span><span class="sxs-lookup"><span data-stu-id="56dbb-168">FQDN</span></span></th>
<th><span data-ttu-id="56dbb-169">Indirizzo IP/FQDN record host</span><span class="sxs-lookup"><span data-stu-id="56dbb-169">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="56dbb-170">Si mappa a/Commenti</span><span class="sxs-lookup"><span data-stu-id="56dbb-170">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56dbb-171">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="56dbb-171">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="56dbb-172">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="56dbb-172">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="56dbb-173">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="56dbb-173">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="56dbb-174">Interfaccia esterna SIP di Access Edge. Necessaria per l'individuazione DNS automatica di partner federati, nota come dominio SIP consentito, nonché come federazione avanzata nelle versioni precedenti. Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync.</span><span class="sxs-lookup"><span data-stu-id="56dbb-174">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="56dbb-175">Questo record SRV è necessario per la mobilità e il fornitore di servizi di accesso a terze parti delle notifiche push</span><span class="sxs-lookup"><span data-stu-id="56dbb-175">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="56dbb-176">Riepilogo DNS per il protocollo XMPP</span><span class="sxs-lookup"><span data-stu-id="56dbb-176">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56dbb-177">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="56dbb-177">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="56dbb-178">FQDN</span><span class="sxs-lookup"><span data-stu-id="56dbb-178">FQDN</span></span></th>
<th><span data-ttu-id="56dbb-179">Indirizzo IP/FQDN record host</span><span class="sxs-lookup"><span data-stu-id="56dbb-179">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="56dbb-180">Si mappa a/Commenti</span><span class="sxs-lookup"><span data-stu-id="56dbb-180">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56dbb-181">DNS esterno/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="56dbb-181">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="56dbb-182">_xmpp-server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="56dbb-182">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="56dbb-183">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="56dbb-183">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="56dbb-184">Interfaccia esterna del proxy XMPP nel servizio Access Edge o nel pool di server perimetrali. Ripetere quanto necessario per tutti i domini SIP interni con gli utenti abilitati per Lync, in cui è consentito il contatto con i contatti XMPP tramite la configurazione del criterio di accesso esterno tramite un criterio globale, il criterio del sito in cui si trova l'utente o il criterio utente applicato all' Utente abilitato per Lync.</span><span class="sxs-lookup"><span data-stu-id="56dbb-184">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="56dbb-185">Un dominio XMPP consentito deve inoltre essere configurato nel criterio dei partner XMPP federati.</span><span class="sxs-lookup"><span data-stu-id="56dbb-185">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="56dbb-186">Per informazioni dettagliate, vedere gli argomenti in <strong>Vedere anche</strong></span><span class="sxs-lookup"><span data-stu-id="56dbb-186">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56dbb-187">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="56dbb-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="56dbb-188">xmpp.contoso.com (esempio)</span><span class="sxs-lookup"><span data-stu-id="56dbb-188">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="56dbb-189">Indirizzo IP del servizio Access Edge nel server perimetrale o nel pool perimetrale che ospita il proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="56dbb-189">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="56dbb-190">Punta al servizio Access Edge o al pool di server perimetrali che ospita il servizio proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="56dbb-190">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="56dbb-191">Il record SRV creato punterà a questo record host (A o AAAA).</span><span class="sxs-lookup"><span data-stu-id="56dbb-191">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

