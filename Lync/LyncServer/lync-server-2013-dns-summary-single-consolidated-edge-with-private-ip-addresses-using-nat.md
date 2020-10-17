---
title: Riepilogo DNS-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: a7e5d792-f397-45e5-af85-20d0f4bf405f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412787(v=OCS.15)
ms:contentKeyID: 48185025
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f97c44b0d199ec257b6e8b8e1d5f4c6d7fa307b4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501243"
---
# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="0dad0-102">Riepilogo DNS-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0dad0-102">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0dad0-103">_**Ultimo argomento modificato:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="0dad0-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="0dad0-104">I requisiti dei record DNS per l'accesso remoto a Lync Server 2013 sono relativamente semplici rispetto a quelli relativi ai certificati e alle porte.</span><span class="sxs-lookup"><span data-stu-id="0dad0-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="0dad0-105">Inoltre, molti record sono facoltativi, a seconda del modo in cui vengono configurati i client che eseguono Lync 2013 e se si Abilita la Federazione.</span><span class="sxs-lookup"><span data-stu-id="0dad0-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="0dad0-106">Per informazioni dettagliate sui requisiti DNS di Lync 2013, vedere [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0dad0-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="0dad0-107">Per informazioni dettagliate sulla configurazione automatica dei client che eseguono Lync 2013 se il DNS split-brain non è configurato, vedere la sezione relativa alla configurazione automatica senza Split-Brain DNS in [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0dad0-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="0dad0-108">Nella tabella seguente viene fornito un riepilogo dei record DNS necessari per supportare la topologia perimetrale consolidata singola illustrata nella relativa figura.</span><span class="sxs-lookup"><span data-stu-id="0dad0-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="0dad0-109">Si noti che alcuni record DNS sono necessari solo per la configurazione automatica dei client Lync 2013 e Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="0dad0-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="0dad0-110">Se si prevede di utilizzare gli oggetti Criteri di gruppo per configurare i client Lync, i record di configurazione automatica associati non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="0dad0-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="0dad0-111">IMPORTANTE: requisiti della scheda di rete per i server perimetrali</span><span class="sxs-lookup"><span data-stu-id="0dad0-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="0dad0-112">Per evitare problemi di routing, verificare che siano presenti almeno due schede di rete nei server perimetrali e che il gateway predefinito sia impostato solo sulla scheda di rete associata all'interfaccia esterna.</span><span class="sxs-lookup"><span data-stu-id="0dad0-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="0dad0-113">Ad esempio, come illustrato nella singola topologia perimetrale consolidata in un [unico perimetro consolidato con indirizzi IP privati e NAT in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), il gateway predefinito dovrebbe puntare al firewall esterno (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="0dad0-113">For example, as shown in the Single Consolidated Edge Topology figure in [Single consolidated edge with private IP addresses and NAT in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), the default gateway would point to the external firewall (10.45.16.1).</span></span>

<span data-ttu-id="0dad0-114">È possibile configurare due schede di rete all'interno del server perimetrale come segue:</span><span class="sxs-lookup"><span data-stu-id="0dad0-114">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="0dad0-115">**Scheda di rete 1 (interfaccia interna)**</span><span class="sxs-lookup"><span data-stu-id="0dad0-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="0dad0-116">Interfaccia interna con indirizzo 172.25.33.10 assegnato.</span><span class="sxs-lookup"><span data-stu-id="0dad0-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="0dad0-117">Non è specificato alcun gateway predefinito.</span><span class="sxs-lookup"><span data-stu-id="0dad0-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="0dad0-118">Verificare che esista una route dalla rete che contiene l'interfaccia interna del server perimetrale a qualsiasi rete che contiene server che eseguono i client Lync 2013 o Lync Server 2013 (ad esempio, da 172.25.33.0 a 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="0dad0-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="0dad0-119">**Scheda di rete 2 (interfaccia esterna)**</span><span class="sxs-lookup"><span data-stu-id="0dad0-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="0dad0-120">A questa scheda di rete sono assegnati tre indirizzi IP privati, ad esempio 10.45.16.10 per Access Edge, 10.45.16.20 per Web Conferencing Edge e 10.45.16.30 per AV Edge</span><span class="sxs-lookup"><span data-stu-id="0dad0-120">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="0dad0-p104">È possibile, ma non consigliabile, utilizzare un solo indirizzo IP per tutte e tre le interfacce dei servizi Edge. Sebbene questa scelta consenta di risparmiare indirizzi IP, richiede numeri di porta diversi per ogni servizio. Il numero di porta predefinito è 443/TCP e garantisce che la maggior parte dei firewall remoti consenta il traffico. L'impostazione dei valori di porta ad esempio su 5061/TCP per Access Edge, 444/TCP per Web Conferencing Edge e 443/TCP per AV Edge può causare problemi per gli utenti remoti se un firewall da cui sono protetti non consente il traffico su 5061/TCP e 444/TCP. L'utilizzo di tre indirizzi IP distinti inoltre facilita la risoluzione dei problemi perché i dati possono essere filtrati in base all'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="0dad0-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="0dad0-126">L'indirizzo IP di Access Edge è primario, con gateway predefinito impostato sul router integrato (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="0dad0-126">Access Edge IP address is primary with default gateway set to integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="0dad0-127">Gli indirizzi di Web Conferencing e A/V Edge sono secondari.</span><span class="sxs-lookup"><span data-stu-id="0dad0-127">Web conferencing and A/V Edge IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="0dad0-128">La configurazione del server perimetrale con due schede di rete è una delle due opzioni.</span><span class="sxs-lookup"><span data-stu-id="0dad0-128">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="0dad0-129">L'altra opzione consiste nell'utilizzare una scheda di rete per il lato interno e tre schede di rete per il lato esterno del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="0dad0-129">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="0dad0-130">Il vantaggio principale di questa opzione è una scheda di rete distinta per ogni servizio server perimetrale e una raccolta di dati potenzialmente più concisa quando è necessaria la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="0dad0-130">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="0dad0-131">Record DNS necessari per un server perimetrale consolidato singolo con indirizzi IP privati e NAT (esempio)</span><span class="sxs-lookup"><span data-stu-id="0dad0-131">DNS Records Required for Single Consolidated Edge with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0dad0-132">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="0dad0-132">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="0dad0-133">FQDN/Record DNS</span><span class="sxs-lookup"><span data-stu-id="0dad0-133">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="0dad0-134">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="0dad0-134">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="0dad0-135">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="0dad0-135">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0dad0-136">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="0dad0-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0dad0-137">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0dad0-137">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0dad0-138">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="0dad0-138">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="0dad0-139">Interfaccia esterna Access Edge (Contoso). Ripetere secondo le necessità per tutti i domini SIP con utenti abilitati per Lync.</span><span class="sxs-lookup"><span data-stu-id="0dad0-139">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0dad0-140">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="0dad0-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0dad0-141">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0dad0-141">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0dad0-142">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="0dad0-142">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="0dad0-143">Interfaccia esterna Web Conferencing Edge Server</span><span class="sxs-lookup"><span data-stu-id="0dad0-143">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0dad0-144">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="0dad0-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0dad0-145">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0dad0-145">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0dad0-146">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="0dad0-146">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="0dad0-147">Interfaccia esterna A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="0dad0-147">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0dad0-148">DNS esterno/SRV/443</span><span class="sxs-lookup"><span data-stu-id="0dad0-148">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="0dad0-149">_sip _sip._tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0dad0-149">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0dad0-150">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0dad0-150">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0dad0-151">Interfaccia esterna di Access Edge.</span><span class="sxs-lookup"><span data-stu-id="0dad0-151">Access Edge external interface.</span></span> <span data-ttu-id="0dad0-152">Necessario per la configurazione automatica dei client Lync 2013 e Lync 2010 per funzionare esternamente.</span><span class="sxs-lookup"><span data-stu-id="0dad0-152">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="0dad0-153">Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync.</span><span class="sxs-lookup"><span data-stu-id="0dad0-153">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0dad0-154">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="0dad0-154">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="0dad0-155">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0dad0-155">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0dad0-156">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0dad0-156">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0dad0-157">Interfaccia esterna SIP di Access Edge. Necessaria per l'individuazione DNS automatica di partner federati, nota come dominio SIP consentito, nonché come federazione avanzata nelle versioni precedenti. Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync.</span><span class="sxs-lookup"><span data-stu-id="0dad0-157">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0dad0-158">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="0dad0-158">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0dad0-159">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0dad0-159">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="0dad0-160">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="0dad0-160">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="0dad0-161">Interfaccia interna perimetrale consolidata</span><span class="sxs-lookup"><span data-stu-id="0dad0-161">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="0dad0-162">I record elencati nella tabella precedente sono visualizzati con estensione <EM>net</EM> o <EM>com</EM> per evidenziare la zona in cui devono trovarsi se non si utilizza DNS di tipo split brain.</span><span class="sxs-lookup"><span data-stu-id="0dad0-162">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="0dad0-163">Se si utilizza DNS di tipo split brain, tutti i record devono trovarsi nella stessa zona <EM>com</EM>, con l'unica distinzione tra versione interna ed esterna della zona DNS.</span><span class="sxs-lookup"><span data-stu-id="0dad0-163">If you are using split-brain DNS, all records would be in the same <EM>.com</EM> zone, with the only distinction being whether they are in the internal or external DNS zone version.</span></span> <span data-ttu-id="0dad0-164">Per informazioni dettagliate, vedere "DNS split-brain" in <A href="lync-server-2013-determine-dns-requirements.md">determine DNS requirements for Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0dad0-164">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="0dad0-165">Record necessari per la federazione</span><span class="sxs-lookup"><span data-stu-id="0dad0-165">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0dad0-166">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="0dad0-166">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="0dad0-167">FQDN</span><span class="sxs-lookup"><span data-stu-id="0dad0-167">FQDN</span></span></th>
<th><span data-ttu-id="0dad0-168">Indirizzo IP/FQDN record host</span><span class="sxs-lookup"><span data-stu-id="0dad0-168">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="0dad0-169">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="0dad0-169">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0dad0-170">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="0dad0-170">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="0dad0-171">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0dad0-171">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0dad0-172">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0dad0-172">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0dad0-173">Interfaccia esterna SIP di Access Edge. Necessaria per l'individuazione DNS automatica di partner federati, nota come dominio SIP consentito, nonché come federazione avanzata nelle versioni precedenti. Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync.</span><span class="sxs-lookup"><span data-stu-id="0dad0-173">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="0dad0-174">Questo record SRV è necessario per la mobilità e il fornitore di servizi di accesso a terze parti delle notifiche push</span><span class="sxs-lookup"><span data-stu-id="0dad0-174">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="0dad0-175">Riepilogo DNS per il protocollo XMPP</span><span class="sxs-lookup"><span data-stu-id="0dad0-175">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0dad0-176">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="0dad0-176">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="0dad0-177">FQDN</span><span class="sxs-lookup"><span data-stu-id="0dad0-177">FQDN</span></span></th>
<th><span data-ttu-id="0dad0-178">Indirizzo IP/FQDN record host</span><span class="sxs-lookup"><span data-stu-id="0dad0-178">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="0dad0-179">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="0dad0-179">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0dad0-180">DNS esterno/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="0dad0-180">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="0dad0-181">_xmpp-server._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0dad0-181">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0dad0-182">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0dad0-182">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0dad0-183">Interfaccia esterna del proxy XMPP nel servizio Access Edge o nel pool di server perimetrali. Ripetere quanto necessario per tutti i domini SIP interni con gli utenti abilitati per Lync, in cui è consentito il contatto con i contatti XMPP tramite la configurazione del criterio di accesso esterno tramite un criterio globale, il criterio del sito in cui si trova l'utente o il criterio utente applicato all'utente abilitato per Lync.</span><span class="sxs-lookup"><span data-stu-id="0dad0-183">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="0dad0-184">Un dominio XMPP consentito deve inoltre essere configurato nel criterio dei partner XMPP federati.</span><span class="sxs-lookup"><span data-stu-id="0dad0-184">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="0dad0-185">Per informazioni dettagliate, vedere gli argomenti in <strong>Vedere anche</strong></span><span class="sxs-lookup"><span data-stu-id="0dad0-185">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0dad0-186">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="0dad0-186">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0dad0-187">xmpp.contoso.com (esempio)</span><span class="sxs-lookup"><span data-stu-id="0dad0-187">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="0dad0-188">Indirizzo IP del servizio Access Edge nel server perimetrale o nel pool perimetrale che ospita il proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="0dad0-188">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="0dad0-189">Punta al servizio Access Edge o al pool di server perimetrali che ospita il servizio proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="0dad0-189">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="0dad0-190">Il record SRV creato punterà a questo record host (A o AAAA).</span><span class="sxs-lookup"><span data-stu-id="0dad0-190">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

