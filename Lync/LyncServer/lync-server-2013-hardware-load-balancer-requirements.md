---
title: Requisiti per il bilanciamento del carico hardware di Lync Server 2013
description: Requisiti del dispositivo di bilanciamento del carico hardware di Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69cbf79c1fd7551dfd428c23ed22c924d0805c43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552922"
---
# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="5759c-103">Requisiti per il bilanciamento del carico hardware per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5759c-103">Hardware load balancer requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5759c-104">_**Ultimo argomento modificato:** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="5759c-104">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="5759c-105">La topologia perimetrale consolidata di Lync Server 2013 è ottimizzata per il bilanciamento del carico DNS per le nuove distribuzioni che si riferiscono principalmente ad altre organizzazioni che utilizzano Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5759c-105">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="5759c-106">Se è richiesta la disponibilità elevata per uno degli scenari seguenti, sarà necessario utilizzare un dispositivo di bilanciamento del carico hardware nei pool di server perimetrali nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5759c-106">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="5759c-107">Federazione con organizzazioni che utilizzano Office Communications Server 2007 R2 o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="5759c-107">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="5759c-108">Messaggistica unificata di Exchange per gli utenti remoti tramite messaggistica unificata di Exchange prima di Exchange 2010 con SP1</span><span class="sxs-lookup"><span data-stu-id="5759c-108">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="5759c-109">Connettività con utenti di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="5759c-109">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5759c-p102">Non è possibile usare il bilanciamento del carico DNS in un'interfaccia e il bilanciamento del carico hardware in un'altra. È necessario usare lo stesso tipo di bilanciamento del carico per entrambe le interfacce, in quanto non è supportata una combinazione dei due tipi.</span><span class="sxs-lookup"><span data-stu-id="5759c-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5759c-p103">Se si usa un servizio di bilanciamento del carico hardware, il bilanciamento del carico distribuito per le connessioni con la rete interna deve essere configurato per bilanciare il carico solo del traffico verso i server che eseguono i servizi Access Edge e A/V Edge. Non è possibile bilanciare il carico del traffico verso il servizio Web Conferencing Edge interno o il servizio del proxy XMPP interno.</span><span class="sxs-lookup"><span data-stu-id="5759c-p103">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5759c-114">Il protocollo DSR (Direct Server Return) NAT non è supportato con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5759c-114">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="5759c-115">Per determinare se il dispositivo di bilanciamento del carico hardware supporta le funzionalità necessarie per Lync Server 2013, vedere la sezione relativa ai partner di bilanciamento del carico di Lync Server 2010 all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) .</span><span class="sxs-lookup"><span data-stu-id="5759c-115">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="5759c-116">Requisiti dei servizi di bilanciamento del carico hardware per i server perimetrali che eseguono il servizio A/V Edge</span><span class="sxs-lookup"><span data-stu-id="5759c-116">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="5759c-117">Di seguito sono riportati i requisiti per il bilanciamento del carico hardware per i server perimetrali che eseguono il servizio A/V Edge:</span><span class="sxs-lookup"><span data-stu-id="5759c-117">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="5759c-p104">Disattivare il nagling TCP per le porte 443 interne ed esterne. Per nagling si intende il processo di combinazione di più pacchetti di piccole dimensioni in un singolo pacchetto di dimensioni maggiori per una trasmissione più efficiente.</span><span class="sxs-lookup"><span data-stu-id="5759c-p104">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="5759c-120">Disattivare il nagling TCP per l'intervallo di porte esterne compreso tra 50.000 e 59.999.</span><span class="sxs-lookup"><span data-stu-id="5759c-120">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="5759c-121">Non utilizzare NAT nel firewall interno o esterno.</span><span class="sxs-lookup"><span data-stu-id="5759c-121">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="5759c-122">L'interfaccia interna perimetrale deve trovarsi in una rete diversa rispetto all'interfaccia esterna del server perimetrale e il routing tra di esse deve essere disabilitato.</span><span class="sxs-lookup"><span data-stu-id="5759c-122">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="5759c-123">L'interfaccia esterna del server perimetrale che esegue il servizio A/V Edge deve utilizzare gli indirizzi IP instradabili pubblicamente e non la conversione NAT o la porta su uno degli indirizzi IP esterni perimetrali.</span><span class="sxs-lookup"><span data-stu-id="5759c-123">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="5759c-124">Requisiti relativi al servizio di bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="5759c-124">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="5759c-125">I requisiti di affinità basati su cookie sono notevolmente ridotti in Lync Server 2013 per i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="5759c-125">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="5759c-126">Se si sta distribuendo Lync Server 2013 e non si conservano i server Lync Server 2010 front end o i pool Front End, non è necessaria la persistenza basata su cookie.</span><span class="sxs-lookup"><span data-stu-id="5759c-126">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="5759c-127">Tuttavia, se si conservano temporaneamente o definitivamente i server front end o i pool Front-End di Lync Server 2010, è comunque possibile utilizzare la persistenza basata su cookie come è stata distribuita e configurata per Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5759c-127">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5759c-128"><STRONG>La decisione di usare l'affinità basata sui cookie anche se la distribuzione non la richiede</STRONG> non determina un impatto negativo.</span><span class="sxs-lookup"><span data-stu-id="5759c-128"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="5759c-129">Per le distribuzioni in cui l'affinità basata sui cookie **non verrà usata**:</span><span class="sxs-lookup"><span data-stu-id="5759c-129">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="5759c-p106">Nella regola di pubblicazione del proxy inverso per la porta 4443, impostare **Forward host header** su True in modo da assicurarsi che l'URL originale venga inoltrato.</span><span class="sxs-lookup"><span data-stu-id="5759c-p106">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="5759c-132">Per le distribuzioni in cui l'affinità basata sui cookie **verrà usata**:</span><span class="sxs-lookup"><span data-stu-id="5759c-132">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="5759c-p107">Nella regola di pubblicazione del proxy inverso per la porta 4443, impostare **Forward host header** su True in modo da assicurarsi che l'URL originale venga inoltrato.</span><span class="sxs-lookup"><span data-stu-id="5759c-p107">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="5759c-135">Il cookie del bilanciamento del carico hardware NON DEVE essere contrassegnato come httpOnly</span><span class="sxs-lookup"><span data-stu-id="5759c-135">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="5759c-136">Per il bilanciamento del carico hardware NON DEVE essere impostata una data di scadenza</span><span class="sxs-lookup"><span data-stu-id="5759c-136">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="5759c-137">Il cookie del bilanciamento del carico hardware DEVE essere denominato **MS-WSMAN** ovvero il valore, non modificabile, previsto dai servizi Web</span><span class="sxs-lookup"><span data-stu-id="5759c-137">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="5759c-p108">Il cookie del bilanciamento del carico hardware DEVE essere impostato in ogni risposta HTTP per la quale la richiesta HTTP in arrivo non presentava un cookie, indipendentemente dal fatto che una precedente risposta HTTP nella stessa connessione TCP abbia già ottenuto un cookie. Se il bilanciamento del carico ottimizza l'inserimento del cookie in modo che venga eseguito una sola volta per ogni connessione TCP, tale ottimizzazione NON DEVE essere usata</span><span class="sxs-lookup"><span data-stu-id="5759c-p108">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5759c-140">Le configurazioni tipiche del dispositivo di bilanciamento del carico hardware utilizzano l'affinità degli indirizzi di origine e la durata di una sessione di 20 min. TCP, che va bene per i client Lync Server e Lync 2013 perché lo stato della sessione viene mantenuto tramite l'utilizzo del client e/o l'interazione tra applicazioni.</span><span class="sxs-lookup"><span data-stu-id="5759c-140">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="5759c-141">Se si distribuiscono dispositivi mobili, il servizio di bilanciamento del carico hardware deve essere in grado di bilanciare il carico delle singole richieste in una sessione TCP (in effetti, è necessario essere in grado di bilanciare il carico di una singola richiesta in base all'indirizzo IP di destinazione).</span><span class="sxs-lookup"><span data-stu-id="5759c-141">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="5759c-p109">I servizi di bilanciamento del carico hardware F5 presentano una funzionalità chiamata OneConnect che garantisce che il bilanciamento del carico venga eseguito per ogni singola richiesta all'interno di una connessione TCP. Se si distribuiscono dispositivi mobili, verificare che il fornitore di servizi di bilanciamento del carico hardware supporti la stessa funzionalità. Le applicazioni per dispositivi mobili Apple iOS più recenti richiedono TLS (Transport Layer Security) versione 1.2. F5 offre impostazioni specifiche a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="5759c-p109">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span><BR><span data-ttu-id="5759c-146">Per informazioni dettagliate sui dispositivi di bilanciamento del carico hardware di terze parti, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="5759c-146">For details on third party hardware load balancers, see <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="5759c-147">Vengono riportati di seguito i requisiti dei servizi di bilanciamento del carico hardware per i servizi Web dei pool di server Director e Front End:</span><span class="sxs-lookup"><span data-stu-id="5759c-147">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="5759c-148">Per i VIP dei servizi Web interni, impostare \_ la persistenza dell'indirizzo di origine (porta interna 80, 443) nel dispositivo di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="5759c-148">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="5759c-149">Per Lync Server 2013, la \_ persistenza dell'addr di origine implica che più connessioni provenienti da un singolo indirizzo IP vengano sempre inviate a un solo server per mantenere lo stato della sessione.</span><span class="sxs-lookup"><span data-stu-id="5759c-149">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="5759c-150">Impostare il timeout di inattività TCP su 1800 secondi.</span><span class="sxs-lookup"><span data-stu-id="5759c-150">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="5759c-p111">Nel firewall tra il proxy inverso e il servizio di bilanciamento del carico hardware del pool di hop successivi, creare una regola per consentire il traffico HTTPS nella porta 4443, dal proxy inverso al servizio di bilanciamento del carico hardware. Il servizio di bilanciamento del carico hardware deve essere configurato per l'ascolto sulle porte 80, 443 e 4443.</span><span class="sxs-lookup"><span data-stu-id="5759c-p111">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer. The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5759c-153">Per ulteriori informazioni sulla configurazione del dispositivo di bilanciamento del carico hardware, leggere il <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">perimetro consolidato in scala di riepilogo delle porte con i dispositivi di bilanciamento del carico hardware in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5759c-153">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="5759c-154">Riepilogo dei requisiti per l'affinità del servizio di bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="5759c-154">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5759c-155">Posizione client/utente</span><span class="sxs-lookup"><span data-stu-id="5759c-155">Client/user location</span></span></th>
<th><span data-ttu-id="5759c-156">Requisiti per l'affinità FQDN dei servizi Web esterni</span><span class="sxs-lookup"><span data-stu-id="5759c-156">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="5759c-157">Requisiti per l'affinità FQDN dei servizi Web interni</span><span class="sxs-lookup"><span data-stu-id="5759c-157">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5759c-158">Lync Web App (utenti interni ed esterni)</span><span class="sxs-lookup"><span data-stu-id="5759c-158">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="5759c-159">Dispositivo mobile (utenti interni ed esterni)</span><span class="sxs-lookup"><span data-stu-id="5759c-159">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="5759c-160">Nessuna affinità</span><span class="sxs-lookup"><span data-stu-id="5759c-160">No affinity</span></span></p></td>
<td><p><span data-ttu-id="5759c-161">Affinità indirizzo di origine</span><span class="sxs-lookup"><span data-stu-id="5759c-161">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5759c-162">Lync Web App (solo utenti esterni)</span><span class="sxs-lookup"><span data-stu-id="5759c-162">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="5759c-163">Dispositivo mobile (utenti interni ed esterni)</span><span class="sxs-lookup"><span data-stu-id="5759c-163">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="5759c-164">Nessuna affinità</span><span class="sxs-lookup"><span data-stu-id="5759c-164">No affinity</span></span></p></td>
<td><p><span data-ttu-id="5759c-165">Affinità indirizzo di origine</span><span class="sxs-lookup"><span data-stu-id="5759c-165">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5759c-166">Lync Web App (solo per gli utenti interni)</span><span class="sxs-lookup"><span data-stu-id="5759c-166">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="5759c-167">Dispositivo mobile (non distribuito)</span><span class="sxs-lookup"><span data-stu-id="5759c-167">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="5759c-168">Nessuna affinità</span><span class="sxs-lookup"><span data-stu-id="5759c-168">No affinity</span></span></p></td>
<td><p><span data-ttu-id="5759c-169">Affinità indirizzo di origine</span><span class="sxs-lookup"><span data-stu-id="5759c-169">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="5759c-170">Monitoraggio delle porte per i servizi di bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="5759c-170">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="5759c-171">Il monitoraggio delle porte viene definito nei servizi di bilanciamento del carico hardware per stabilire quando determinati servizi non sono più disponibili a causa di un errore hardware o delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="5759c-171">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="5759c-172">Ad esempio, se il servizio front end server (RTCSRV) si interrompe perché il front end server o il pool Front End ha esito negativo, il monitoraggio di HLB dovrebbe anche interrompere la ricezione del traffico sui servizi Web.</span><span class="sxs-lookup"><span data-stu-id="5759c-172">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="5759c-173">Il monitoraggio delle porte viene implementato nel servizio HLB per monitorare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5759c-173">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="5759c-174">Pool di utenti front end server – interfaccia interna di HLB</span><span class="sxs-lookup"><span data-stu-id="5759c-174">Front End Server User Pool – HLB Internal Interface</span></span>

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
<th><span data-ttu-id="5759c-175">IP virtuale/Porta</span><span class="sxs-lookup"><span data-stu-id="5759c-175">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="5759c-176">Porta nodo</span><span class="sxs-lookup"><span data-stu-id="5759c-176">Node Port</span></span></th>
<th><span data-ttu-id="5759c-177">Computer/Monitor nodo</span><span class="sxs-lookup"><span data-stu-id="5759c-177">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="5759c-178">Profilo persistenza</span><span class="sxs-lookup"><span data-stu-id="5759c-178">Persistence Profile</span></span></th>
<th><span data-ttu-id="5759c-179">Note</span><span class="sxs-lookup"><span data-stu-id="5759c-179">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5759c-180">&lt;int_mco_443_vs del pool &gt;</span><span class="sxs-lookup"><span data-stu-id="5759c-180">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="5759c-181">443</span><span class="sxs-lookup"><span data-stu-id="5759c-181">443</span></span></p></td>
<td><p><span data-ttu-id="5759c-182">443</span><span class="sxs-lookup"><span data-stu-id="5759c-182">443</span></span></p></td>
<td><p><span data-ttu-id="5759c-183">Front End</span><span class="sxs-lookup"><span data-stu-id="5759c-183">Front End</span></span></p>
<p><span data-ttu-id="5759c-184">5061</span><span class="sxs-lookup"><span data-stu-id="5759c-184">5061</span></span></p></td>
<td><p><span data-ttu-id="5759c-185">Origine</span><span class="sxs-lookup"><span data-stu-id="5759c-185">Source</span></span></p></td>
<td><p><span data-ttu-id="5759c-186">HTTPS</span><span class="sxs-lookup"><span data-stu-id="5759c-186">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5759c-187">&lt;int_mco_80_vs del pool &gt;</span><span class="sxs-lookup"><span data-stu-id="5759c-187">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="5759c-188">80</span><span class="sxs-lookup"><span data-stu-id="5759c-188">80</span></span></p></td>
<td><p><span data-ttu-id="5759c-189">80</span><span class="sxs-lookup"><span data-stu-id="5759c-189">80</span></span></p></td>
<td><p><span data-ttu-id="5759c-190">Front End</span><span class="sxs-lookup"><span data-stu-id="5759c-190">Front End</span></span></p>
<p><span data-ttu-id="5759c-191">5061</span><span class="sxs-lookup"><span data-stu-id="5759c-191">5061</span></span></p></td>
<td><p><span data-ttu-id="5759c-192">Origine</span><span class="sxs-lookup"><span data-stu-id="5759c-192">Source</span></span></p></td>
<td><p><span data-ttu-id="5759c-193">HTTP</span><span class="sxs-lookup"><span data-stu-id="5759c-193">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="5759c-194">Pool di utenti front end server – interfaccia esterna di HLB</span><span class="sxs-lookup"><span data-stu-id="5759c-194">Front End Server User Pool – HLB External Interface</span></span>

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
<th><span data-ttu-id="5759c-195">IP virtuale/Porta</span><span class="sxs-lookup"><span data-stu-id="5759c-195">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="5759c-196">Porta nodo</span><span class="sxs-lookup"><span data-stu-id="5759c-196">Node Port</span></span></th>
<th><span data-ttu-id="5759c-197">Computer/Monitor nodo</span><span class="sxs-lookup"><span data-stu-id="5759c-197">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="5759c-198">Profilo persistenza</span><span class="sxs-lookup"><span data-stu-id="5759c-198">Persistence Profile</span></span></th>
<th><span data-ttu-id="5759c-199">Note</span><span class="sxs-lookup"><span data-stu-id="5759c-199">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5759c-200">&lt;web_mco_443_vs del pool &gt;</span><span class="sxs-lookup"><span data-stu-id="5759c-200">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="5759c-201">443</span><span class="sxs-lookup"><span data-stu-id="5759c-201">443</span></span></p></td>
<td><p><span data-ttu-id="5759c-202">4443</span><span class="sxs-lookup"><span data-stu-id="5759c-202">4443</span></span></p></td>
<td><p><span data-ttu-id="5759c-203">Front End</span><span class="sxs-lookup"><span data-stu-id="5759c-203">Front End</span></span></p>
<p><span data-ttu-id="5759c-204">5061</span><span class="sxs-lookup"><span data-stu-id="5759c-204">5061</span></span></p></td>
<td><p><span data-ttu-id="5759c-205">Nessuno</span><span class="sxs-lookup"><span data-stu-id="5759c-205">None</span></span></p></td>
<td><p><span data-ttu-id="5759c-206">HTTPS</span><span class="sxs-lookup"><span data-stu-id="5759c-206">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5759c-207">&lt;web_mco_80_vs del pool &gt;</span><span class="sxs-lookup"><span data-stu-id="5759c-207">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="5759c-208">80</span><span class="sxs-lookup"><span data-stu-id="5759c-208">80</span></span></p></td>
<td><p><span data-ttu-id="5759c-209">8080</span><span class="sxs-lookup"><span data-stu-id="5759c-209">8080</span></span></p></td>
<td><p><span data-ttu-id="5759c-210">Front End</span><span class="sxs-lookup"><span data-stu-id="5759c-210">Front End</span></span></p>
<p><span data-ttu-id="5759c-211">5061</span><span class="sxs-lookup"><span data-stu-id="5759c-211">5061</span></span></p></td>
<td><p><span data-ttu-id="5759c-212">Nessuno</span><span class="sxs-lookup"><span data-stu-id="5759c-212">None</span></span></p></td>
<td><p><span data-ttu-id="5759c-213">HTTP</span><span class="sxs-lookup"><span data-stu-id="5759c-213">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

