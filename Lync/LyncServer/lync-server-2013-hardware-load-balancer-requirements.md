---
title: 'Lync Server 2013: Requisiti relativi al servizio di bilanciamento del carico hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d5b10a91f469bf4688de06e836e0bdeffae1112
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="b51f9-102">Requisiti relativi al servizio di bilanciamento del carico hardware per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b51f9-102">Hardware load balancer requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b51f9-103">_**Argomento Ultima modifica:** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="b51f9-103">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="b51f9-104">La topologia di Edge consolidato di Lync Server 2013 è ottimizzata per il bilanciamento del carico DNS per le nuove distribuzioni federative principalmente con altre organizzazioni che usano Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b51f9-104">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="b51f9-105">Se è necessaria una disponibilità elevata per uno degli scenari seguenti, è necessario usare un bilanciamento del carico hardware nei pool di Edge Server per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b51f9-105">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="b51f9-106">Federazione con organizzazioni che usano Office Communications Server 2007 R2 o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="b51f9-106">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="b51f9-107">Messaggistica unificata di Exchange per utenti remoti con messaggistica unificata di Exchange prima di Exchange 2010 con SP1</span><span class="sxs-lookup"><span data-stu-id="b51f9-107">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="b51f9-108">Connettività agli utenti di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="b51f9-108">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b51f9-109">L'uso del bilanciamento del carico DNS su un'interfaccia e il bilanciamento del carico hardware dall'altro non è supportato.</span><span class="sxs-lookup"><span data-stu-id="b51f9-109">Using DNS load balancing on one interface and hardware load balancing on the other is not supported.</span></span> <span data-ttu-id="b51f9-110">È necessario usare il bilanciamento del carico hardware per entrambe le interfacce o il bilanciamento del carico DNS per entrambi.</span><span class="sxs-lookup"><span data-stu-id="b51f9-110">You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b51f9-111">Se si usa un sistema di bilanciamento del carico hardware, il servizio di bilanciamento del carico distribuito per le connessioni con la rete interna deve essere configurato per il bilanciamento del carico solo del traffico verso i server che esegue Access Edge e il servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="b51f9-111">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service.</span></span> <span data-ttu-id="b51f9-112">Non può caricare il bilanciamento del traffico verso il servizio Web Conferencing Edge interno o il servizio proxy XMPP interno.</span><span class="sxs-lookup"><span data-stu-id="b51f9-112">It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b51f9-113">La NAT DSR (Direct Server Return) non è supportata con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b51f9-113">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="b51f9-114">Per determinare se il dispositivo di bilanciamento del carico hardware supporta le funzionalità necessarie per Lync Server 2013, vedere "partner di bilanciamento del carico di Lync Server [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)2010".</span><span class="sxs-lookup"><span data-stu-id="b51f9-114">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="b51f9-115">Requisiti di bilanciamento del carico hardware per i server perimetrali che utilizzano il servizio A/V Edge</span><span class="sxs-lookup"><span data-stu-id="b51f9-115">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="b51f9-116">Di seguito sono riportati i requisiti di bilanciamento del carico hardware per Edge Server che esegue il servizio A/V Edge:</span><span class="sxs-lookup"><span data-stu-id="b51f9-116">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="b51f9-117">Disattivare TCP nagling per le porte interne ed esterne 443.</span><span class="sxs-lookup"><span data-stu-id="b51f9-117">Turn off TCP nagling for both internal and external ports 443.</span></span> <span data-ttu-id="b51f9-118">Nagling è il processo di combinazione di diversi piccoli pacchetti in un singolo pacchetto più grande per una trasmissione più efficiente.</span><span class="sxs-lookup"><span data-stu-id="b51f9-118">Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="b51f9-119">Disattivare TCP nagling per l'intervallo di porte esterne 50.000-59.999.</span><span class="sxs-lookup"><span data-stu-id="b51f9-119">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="b51f9-120">Non usare NAT sul firewall interno o esterno.</span><span class="sxs-lookup"><span data-stu-id="b51f9-120">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="b51f9-121">L'interfaccia interna del bordo deve essere in una rete diversa rispetto all'interfaccia esterna del server perimetrale e il routing tra di essi deve essere disabilitato.</span><span class="sxs-lookup"><span data-stu-id="b51f9-121">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="b51f9-122">L'interfaccia esterna dell'Edge Server che usa il servizio A/V Edge deve usare indirizzi IP instradabili pubblicamente e nessuna traduzione NAT o Port in uno degli indirizzi IP esterni di Edge.</span><span class="sxs-lookup"><span data-stu-id="b51f9-122">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="b51f9-123">Requisiti di bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="b51f9-123">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="b51f9-124">I requisiti di affinità basati su cookie sono notevolmente ridotti in Lync Server 2013 per i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="b51f9-124">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="b51f9-125">Se si distribuisce Lync Server 2013 e non vengono mantenuti i server front end o i pool Front-End di Lync Server 2010, non è necessaria la persistenza basata su cookie.</span><span class="sxs-lookup"><span data-stu-id="b51f9-125">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="b51f9-126">Se tuttavia si mantengono temporaneamente o definitivamente tutti i server front-end di Lync Server 2010 o i pool Front-End, è comunque possibile usare la persistenza basata su cookie mentre viene distribuita e configurata per Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b51f9-126">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b51f9-127"><STRONG>Se si decide di usare l'affinità basata su cookie anche se la distribuzione non lo richiede</STRONG>, non c'è alcun impatto negativo.</span><span class="sxs-lookup"><span data-stu-id="b51f9-127"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="b51f9-128">Per le distribuzioni che **non useranno** l'affinità basata su cookie:</span><span class="sxs-lookup"><span data-stu-id="b51f9-128">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="b51f9-129">Nella regola di pubblicazione del proxy inverso per la porta 4443 impostare **Inoltra intestazione host** su true.</span><span class="sxs-lookup"><span data-stu-id="b51f9-129">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True.</span></span> <span data-ttu-id="b51f9-130">In questo modo verrà inoltrato l'URL originale.</span><span class="sxs-lookup"><span data-stu-id="b51f9-130">This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="b51f9-131">Per le distribuzioni **che** utilizzeranno l'affinità basata su cookie:</span><span class="sxs-lookup"><span data-stu-id="b51f9-131">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="b51f9-132">Nella regola di pubblicazione del proxy inverso per la porta 4443 impostare **Inoltra intestazione host** su true.</span><span class="sxs-lookup"><span data-stu-id="b51f9-132">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True.</span></span> <span data-ttu-id="b51f9-133">In questo modo verrà inoltrato l'URL originale.</span><span class="sxs-lookup"><span data-stu-id="b51f9-133">This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="b51f9-134">Il cookie di bilanciamento del carico hardware non deve essere contrassegnato httpOnly</span><span class="sxs-lookup"><span data-stu-id="b51f9-134">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="b51f9-135">Il cookie di bilanciamento del carico hardware non deve avere una data di scadenza</span><span class="sxs-lookup"><span data-stu-id="b51f9-135">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="b51f9-136">Il cookie di bilanciamento del carico hardware deve essere denominato **MS-WSMan** (questo è il valore previsto per i servizi Web e non può essere modificato)</span><span class="sxs-lookup"><span data-stu-id="b51f9-136">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="b51f9-137">Il cookie di bilanciamento del carico hardware deve essere impostato in tutte le risposte HTTP per cui la richiesta HTTP in arrivo non ha un cookie, indipendentemente dal fatto che una risposta HTTP precedente alla stessa connessione TCP abbia già ottenuto un cookie.</span><span class="sxs-lookup"><span data-stu-id="b51f9-137">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie.</span></span> <span data-ttu-id="b51f9-138">Se il bilanciamento del carico ottimizza l'inserimento del cookie per eseguire una sola volta per ogni connessione TCP, non deve essere usata l'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="b51f9-138">If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b51f9-139">Le tipiche configurazioni di bilanciamento del carico hardware usano l'affinità degli indirizzi di origine e la durata di una sessione TCP di 20 minuti, che va bene per i client Lync Server e Lync 2013, perché lo stato della sessione viene gestito tramite l'utilizzo del client e/o l'interazione tra applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b51f9-139">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="b51f9-140">Se si distribuiscono dispositivi mobili, il dispositivo di bilanciamento del carico hardware deve essere in grado di bilanciare il carico delle singole richieste all'interno di una sessione TCP (in effetti, è necessario essere in grado di bilanciare il carico di una singola richiesta in base all'indirizzo IP di destinazione).</span><span class="sxs-lookup"><span data-stu-id="b51f9-140">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b51f9-141">I servizi di bilanciamento del carico hardware F5 hanno una caratteristica denominata OneConnect che garantisce che ogni richiesta all'interno di una connessione TCP sia bilanciata individualmente.</span><span class="sxs-lookup"><span data-stu-id="b51f9-141">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced.</span></span> <span data-ttu-id="b51f9-142">Se si distribuiscono dispositivi mobili, verificare che il fornitore del dispositivo di bilanciamento del carico hardware supporti le stesse funzionalità.</span><span class="sxs-lookup"><span data-stu-id="b51f9-142">If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality.</span></span> <span data-ttu-id="b51f9-143">Le più recenti app per dispositivi mobili Apple iOS richiedono Transport Layer Security (TLS) versione 1,2.</span><span class="sxs-lookup"><span data-stu-id="b51f9-143">The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2.</span></span> <span data-ttu-id="b51f9-144">F5 offre impostazioni specifiche per questo.</span><span class="sxs-lookup"><span data-stu-id="b51f9-144">F5 provides specific settings for this.</span></span><BR><span data-ttu-id="b51f9-145">Per informazioni dettagliate sui dispositivi di bilanciamento del carico hardware di terze parti, vedere<A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="b51f9-145">For details on third party hardware load balancers, see <A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="b51f9-146">Di seguito sono riportati i requisiti di bilanciamento del carico hardware per i servizi Web Director e front end pool:</span><span class="sxs-lookup"><span data-stu-id="b51f9-146">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="b51f9-147">Per i VIP dei servizi Web interni,\_imposta la persistenza degli indirizzi di origine (porta interna 80, 443) nel servizio di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="b51f9-147">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="b51f9-148">Per Lync Server 2013, la\_persistenza degli indirizzi di origine indica che più connessioni provenienti da un singolo indirizzo IP vengono sempre inviate a un server per mantenere lo stato della sessione.</span><span class="sxs-lookup"><span data-stu-id="b51f9-148">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="b51f9-149">Usare il timeout di inattività TCP di 1800 secondi.</span><span class="sxs-lookup"><span data-stu-id="b51f9-149">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="b51f9-150">Nel firewall tra il proxy inverso e il bilanciamento del carico hardware del pool hop successivo creare una regola per consentire HTTPS: traffico sulla porta 4443, dal proxy inverso al bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="b51f9-150">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer.</span></span> <span data-ttu-id="b51f9-151">Il bilanciamento del carico hardware deve essere configurato per l'ascolto sulle porte 80, 443 e 4443.</span><span class="sxs-lookup"><span data-stu-id="b51f9-151">The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b51f9-152">Per ulteriori informazioni sulla configurazione dell'utilità di bilanciamento del carico hardware, vedere la pagina relativa a <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Edge consolidato con bilanciamento del carico hardware in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b51f9-152">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="b51f9-153">Riepilogo dei requisiti di affinità di bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="b51f9-153">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b51f9-154">Posizione client/utente</span><span class="sxs-lookup"><span data-stu-id="b51f9-154">Client/user location</span></span></th>
<th><span data-ttu-id="b51f9-155">Requisiti di affinità FQDN servizi Web esterni</span><span class="sxs-lookup"><span data-stu-id="b51f9-155">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="b51f9-156">Requisiti di affinità FQDN servizi Web interni</span><span class="sxs-lookup"><span data-stu-id="b51f9-156">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b51f9-157">Lync Web App (utenti interni ed esterni)</span><span class="sxs-lookup"><span data-stu-id="b51f9-157">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="b51f9-158">Dispositivo mobile (utenti interni ed esterni)</span><span class="sxs-lookup"><span data-stu-id="b51f9-158">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="b51f9-159">Nessuna affinità</span><span class="sxs-lookup"><span data-stu-id="b51f9-159">No affinity</span></span></p></td>
<td><p><span data-ttu-id="b51f9-160">Affinità indirizzo di origine</span><span class="sxs-lookup"><span data-stu-id="b51f9-160">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b51f9-161">Lync Web App (solo utenti esterni)</span><span class="sxs-lookup"><span data-stu-id="b51f9-161">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="b51f9-162">Dispositivo mobile (utenti interni ed esterni)</span><span class="sxs-lookup"><span data-stu-id="b51f9-162">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="b51f9-163">Nessuna affinità</span><span class="sxs-lookup"><span data-stu-id="b51f9-163">No affinity</span></span></p></td>
<td><p><span data-ttu-id="b51f9-164">Affinità indirizzo di origine</span><span class="sxs-lookup"><span data-stu-id="b51f9-164">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b51f9-165">Lync Web App (solo utenti interni)</span><span class="sxs-lookup"><span data-stu-id="b51f9-165">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="b51f9-166">Dispositivo mobile (non distribuito)</span><span class="sxs-lookup"><span data-stu-id="b51f9-166">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="b51f9-167">Nessuna affinità</span><span class="sxs-lookup"><span data-stu-id="b51f9-167">No affinity</span></span></p></td>
<td><p><span data-ttu-id="b51f9-168">Affinità indirizzo di origine</span><span class="sxs-lookup"><span data-stu-id="b51f9-168">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="b51f9-169">Monitoraggio della porta per i dispositivi di bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="b51f9-169">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="b51f9-170">Puoi definire il monitoraggio della porta sui dispositivi di bilanciamento del carico hardware per determinare quando i servizi specifici non sono più disponibili a causa di problemi hardware o comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="b51f9-170">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="b51f9-171">Ad esempio, se il servizio server front-end (RTCSRV) si arresta perché il server front-end o il pool Front-end non riesce, il monitoraggio di HLB dovrebbe interrompere anche la ricezione del traffico sui servizi Web.</span><span class="sxs-lookup"><span data-stu-id="b51f9-171">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="b51f9-172">Puoi implementare il monitoraggio della porta in HLB per monitorare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b51f9-172">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="b51f9-173">Pool di utenti del server front-end-interfaccia interna di HLB</span><span class="sxs-lookup"><span data-stu-id="b51f9-173">Front End Server User Pool – HLB Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b51f9-174">IP virtuale/porta</span><span class="sxs-lookup"><span data-stu-id="b51f9-174">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="b51f9-175">Porta nodi</span><span class="sxs-lookup"><span data-stu-id="b51f9-175">Node Port</span></span></th>
<th><span data-ttu-id="b51f9-176">Nodo macchina/monitor</span><span class="sxs-lookup"><span data-stu-id="b51f9-176">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="b51f9-177">Profilo di persistenza</span><span class="sxs-lookup"><span data-stu-id="b51f9-177">Persistence Profile</span></span></th>
<th><span data-ttu-id="b51f9-178">Note</span><span class="sxs-lookup"><span data-stu-id="b51f9-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b51f9-179">&lt;Web&gt;pool-int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="b51f9-179">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="b51f9-180">443</span><span class="sxs-lookup"><span data-stu-id="b51f9-180">443</span></span></p></td>
<td><p><span data-ttu-id="b51f9-181">443</span><span class="sxs-lookup"><span data-stu-id="b51f9-181">443</span></span></p></td>
<td><p><span data-ttu-id="b51f9-182">Front-end</span><span class="sxs-lookup"><span data-stu-id="b51f9-182">Front End</span></span></p>
<p><span data-ttu-id="b51f9-183">5061</span><span class="sxs-lookup"><span data-stu-id="b51f9-183">5061</span></span></p></td>
<td><p><span data-ttu-id="b51f9-184">Fonte</span><span class="sxs-lookup"><span data-stu-id="b51f9-184">Source</span></span></p></td>
<td><p><span data-ttu-id="b51f9-185">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b51f9-185">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b51f9-186">&lt;Web&gt;pool-int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="b51f9-186">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="b51f9-187">80</span><span class="sxs-lookup"><span data-stu-id="b51f9-187">80</span></span></p></td>
<td><p><span data-ttu-id="b51f9-188">80</span><span class="sxs-lookup"><span data-stu-id="b51f9-188">80</span></span></p></td>
<td><p><span data-ttu-id="b51f9-189">Front-end</span><span class="sxs-lookup"><span data-stu-id="b51f9-189">Front End</span></span></p>
<p><span data-ttu-id="b51f9-190">5061</span><span class="sxs-lookup"><span data-stu-id="b51f9-190">5061</span></span></p></td>
<td><p><span data-ttu-id="b51f9-191">Fonte</span><span class="sxs-lookup"><span data-stu-id="b51f9-191">Source</span></span></p></td>
<td><p><span data-ttu-id="b51f9-192">HTTP</span><span class="sxs-lookup"><span data-stu-id="b51f9-192">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="b51f9-193">Pool di utenti del server front-end-interfaccia esterna di HLB</span><span class="sxs-lookup"><span data-stu-id="b51f9-193">Front End Server User Pool – HLB External Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b51f9-194">IP virtuale/porta</span><span class="sxs-lookup"><span data-stu-id="b51f9-194">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="b51f9-195">Porta nodi</span><span class="sxs-lookup"><span data-stu-id="b51f9-195">Node Port</span></span></th>
<th><span data-ttu-id="b51f9-196">Nodo macchina/monitor</span><span class="sxs-lookup"><span data-stu-id="b51f9-196">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="b51f9-197">Profilo di persistenza</span><span class="sxs-lookup"><span data-stu-id="b51f9-197">Persistence Profile</span></span></th>
<th><span data-ttu-id="b51f9-198">Note</span><span class="sxs-lookup"><span data-stu-id="b51f9-198">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b51f9-199">&lt;web_mco_443_vs&gt;del pool</span><span class="sxs-lookup"><span data-stu-id="b51f9-199">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="b51f9-200">443</span><span class="sxs-lookup"><span data-stu-id="b51f9-200">443</span></span></p></td>
<td><p><span data-ttu-id="b51f9-201">4443</span><span class="sxs-lookup"><span data-stu-id="b51f9-201">4443</span></span></p></td>
<td><p><span data-ttu-id="b51f9-202">Front-end</span><span class="sxs-lookup"><span data-stu-id="b51f9-202">Front End</span></span></p>
<p><span data-ttu-id="b51f9-203">5061</span><span class="sxs-lookup"><span data-stu-id="b51f9-203">5061</span></span></p></td>
<td><p><span data-ttu-id="b51f9-204">Nessuno</span><span class="sxs-lookup"><span data-stu-id="b51f9-204">None</span></span></p></td>
<td><p><span data-ttu-id="b51f9-205">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b51f9-205">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b51f9-206">&lt;web_mco_80_vs&gt;del pool</span><span class="sxs-lookup"><span data-stu-id="b51f9-206">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="b51f9-207">80</span><span class="sxs-lookup"><span data-stu-id="b51f9-207">80</span></span></p></td>
<td><p><span data-ttu-id="b51f9-208">8080</span><span class="sxs-lookup"><span data-stu-id="b51f9-208">8080</span></span></p></td>
<td><p><span data-ttu-id="b51f9-209">Front-end</span><span class="sxs-lookup"><span data-stu-id="b51f9-209">Front End</span></span></p>
<p><span data-ttu-id="b51f9-210">5061</span><span class="sxs-lookup"><span data-stu-id="b51f9-210">5061</span></span></p></td>
<td><p><span data-ttu-id="b51f9-211">Nessuno</span><span class="sxs-lookup"><span data-stu-id="b51f9-211">None</span></span></p></td>
<td><p><span data-ttu-id="b51f9-212">HTTP</span><span class="sxs-lookup"><span data-stu-id="b51f9-212">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

