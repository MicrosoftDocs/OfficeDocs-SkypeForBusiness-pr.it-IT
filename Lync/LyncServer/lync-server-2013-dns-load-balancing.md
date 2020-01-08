---
title: 'Lync Server 2013: bilanciamento del carico DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4248815c2e896c6c4ce36d22fd6544c298527766
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="45e73-102">Bilanciamento del carico DNS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45e73-102">DNS load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45e73-103">_**Argomento Ultima modifica:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="45e73-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="45e73-104">Lync Server Abilita il bilanciamento del carico DNS, una soluzione software che consente di ridurre notevolmente il sovraccarico di amministrazione per il bilanciamento del carico nella rete.</span><span class="sxs-lookup"><span data-stu-id="45e73-104">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="45e73-105">Il bilanciamento del carico DNS bilancia il traffico di rete univoco per Lync Server, ad esempio il traffico SIP e il traffico multimediale.</span><span class="sxs-lookup"><span data-stu-id="45e73-105">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="45e73-106">Se si distribuisce il bilanciamento del carico DNS, il sovraccarico di amministrazione dell'organizzazione per i dispositivi di bilanciamento del carico hardware verrà ridotto a icona.</span><span class="sxs-lookup"><span data-stu-id="45e73-106">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="45e73-107">Inoltre, la risoluzione dei problemi complessi relativi alla configurazione errata dei bilanciatori di carichi per il traffico SIP verrà eliminata.</span><span class="sxs-lookup"><span data-stu-id="45e73-107">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="45e73-108">È anche possibile impedire le connessioni del server in modo da poter prendere i server offline.</span><span class="sxs-lookup"><span data-stu-id="45e73-108">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="45e73-109">Il bilanciamento del carico DNS garantisce inoltre che i problemi di bilanciamento del carico hardware non influiscono sugli elementi del traffico SIP, ad esempio il routing delle chiamate di base.</span><span class="sxs-lookup"><span data-stu-id="45e73-109">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="45e73-110">Se si usa il bilanciamento del carico DNS, potrebbe essere anche possibile acquistare i dispositivi di bilanciamento del carico hardware a costo inferiore rispetto a quelli usati per tutti i tipi di traffico.</span><span class="sxs-lookup"><span data-stu-id="45e73-110">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="45e73-111">È consigliabile usare i bilanciatori di carico che hanno superato i test di qualifica di interoperabilità con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="45e73-111">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="45e73-112">Per informazioni dettagliate sui test di interoperabilità del bilanciamento del carico, vedere "partner di bilanciamento del carico [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)di Lync Server 2010".</span><span class="sxs-lookup"><span data-stu-id="45e73-112">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="45e73-113">Il bilanciamento del carico DNS è supportato per i pool Front-End, i pool di Edge Server, i pool di Director e i pool di Mediation Server autonomi.</span><span class="sxs-lookup"><span data-stu-id="45e73-113">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="45e73-114">Bilanciamento del carico DNS nei pool di front end e nei pool di Director</span><span class="sxs-lookup"><span data-stu-id="45e73-114">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="45e73-115">È possibile usare il bilanciamento del carico DNS per il traffico SIP nei pool di front end e nei pool di Director.</span><span class="sxs-lookup"><span data-stu-id="45e73-115">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools.</span></span> <span data-ttu-id="45e73-116">Con il bilanciamento del carico DNS distribuito, è comunque necessario usare anche i dispositivi di bilanciamento del carico hardware per questi pool, ma solo per il traffico HTTPS da client a server.</span><span class="sxs-lookup"><span data-stu-id="45e73-116">With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic.</span></span> <span data-ttu-id="45e73-117">Il bilanciamento del carico hardware viene usato per il traffico HTTPS dai client sulle porte 443 e 80.</span><span class="sxs-lookup"><span data-stu-id="45e73-117">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="45e73-118">Anche se hai ancora bisogno di bilanciamento del carico hardware per questi pool, la loro configurazione e l'amministrazione saranno principalmente per il traffico HTTPS, a cui sono abituati gli amministratori dei dispositivi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="45e73-118">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="45e73-119">Bilanciamento del carico DNS e supporto di client e server meno recenti</span><span class="sxs-lookup"><span data-stu-id="45e73-119">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="45e73-120">Il bilanciamento del carico DNS supporta il failover automatico solo per i server che utilizzano Lync Server 2013 o Lync Server 2010 e per i client Lync 2013 e Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="45e73-120">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="45e73-121">Le versioni precedenti di client e Office Communications Server possono comunque connettersi ai pool in cui è in esecuzione il bilanciamento del carico DNS, ma se non riescono a stabilire una connessione al primo server a cui si riferisce il bilanciamento del carico DNS, non riescono a eseguire il failover su un altro server nel pool .</span><span class="sxs-lookup"><span data-stu-id="45e73-121">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="45e73-122">Inoltre, se si usa la messaggistica unificata di Exchange, è necessario usare un minimo di Exchange 2010 SP1 per ottenere il supporto per il bilanciamento del carico DNS di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="45e73-122">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="45e73-123">Se si usa una versione precedente di Exchange, gli utenti non avranno funzionalità di failover per questi scenari di messaggistica unificata di Exchange:</span><span class="sxs-lookup"><span data-stu-id="45e73-123">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="45e73-124">Riproduzione della segreteria telefonica aziendale sul telefono</span><span class="sxs-lookup"><span data-stu-id="45e73-124">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="45e73-125">Trasferimento di chiamate da un operatore automatico di messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="45e73-125">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="45e73-126">Tutti gli altri scenari di messaggistica unificata di Exchange funzioneranno correttamente.</span><span class="sxs-lookup"><span data-stu-id="45e73-126">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="45e73-127">Distribuzione del bilanciamento del carico DNS nei pool di front-end e di Director</span><span class="sxs-lookup"><span data-stu-id="45e73-127">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="45e73-128">La distribuzione di bilanciamento del carico DNS nei pool di front end e nei pool di Director richiede di eseguire alcuni passaggi aggiuntivi con FQDN e record DNS.</span><span class="sxs-lookup"><span data-stu-id="45e73-128">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="45e73-129">Un pool che usa il bilanciamento del carico DNS deve avere due nomi di dominio completi: il nome di dominio completo del pool normale usato dal bilanciamento del carico DNS, ad esempio pool01.contoso.com, e viene risolto nell'IPs fisico dei server del pool e un altro nome di dominio completo per i servizi Web del pool, ad esempio web01.contoso.com), che viene risolto nell'indirizzo IP virtuale del pool.</span><span class="sxs-lookup"><span data-stu-id="45e73-129">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="45e73-130">In Generatore di topologia, se si vuole distribuire il bilanciamento del carico DNS per un pool, per creare il nome di dominio completo aggiuntivo per i servizi Web del pool, è necessario selezionare la casella di controllo **Sostituisci il nome FQDN del pool di servizi Web interni** e digitare il nome di dominio completo nella pagina **specifica gli URL dei servizi Web per questo pool** .</span><span class="sxs-lookup"><span data-stu-id="45e73-130">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="45e73-131">Per supportare il nome di dominio completo usato dal bilanciamento del carico DNS, è necessario eseguire il provisioning del DNS per risolvere il nome di dominio completo del pool, ad esempio pool01.contoso.com, agli indirizzi IP di tutti i server del pool (ad es. 192.168.1.1, 192.168.1.2 e così via).</span><span class="sxs-lookup"><span data-stu-id="45e73-131">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span> <span data-ttu-id="45e73-132">Dovresti includere solo gli indirizzi IP dei server attualmente distribuiti.</span><span class="sxs-lookup"><span data-stu-id="45e73-132">You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="45e73-133">Se si hanno più di un pool Front end o un server front-end, l'FQDN dei servizi Web esterni deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="45e73-133">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="45e73-134">Se ad esempio si definisce il nome di dominio completo dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile usare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front-end o front end server.</span><span class="sxs-lookup"><span data-stu-id="45e73-134">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="45e73-135">Se si sta distribuendo anche Directors, l'FQDN dei servizi Web esterni definiti per qualsiasi pool di Director o Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front-end o front end server.</span><span class="sxs-lookup"><span data-stu-id="45e73-135">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="45e73-136">Se decidi di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni nome di dominio completo deve essere univoco da qualsiasi altro pool di front-end, Director o pool di Director.</span><span class="sxs-lookup"><span data-stu-id="45e73-136">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="45e73-137">Bilanciamento del carico DNS nei pool di Edge Server</span><span class="sxs-lookup"><span data-stu-id="45e73-137">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="45e73-138">È possibile distribuire il bilanciamento del carico DNS nei pool di Edge Server.</span><span class="sxs-lookup"><span data-stu-id="45e73-138">You can deploy DNS load balancing on Edge Server pools.</span></span> <span data-ttu-id="45e73-139">In questo caso, è necessario tenere conto di alcune considerazioni.</span><span class="sxs-lookup"><span data-stu-id="45e73-139">If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="45e73-140">L'uso del bilanciamento del carico DNS nei server perimetrali causa una perdita di capacità di failover negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="45e73-140">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="45e73-141">Federazione con organizzazioni che utilizzano versioni di Office Communications Server rilasciate prima di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="45e73-141">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="45e73-142">Scambio di messaggi istantanei con gli utenti di servizi di messaggistica istantanea pubblica AOLand\!Yahoo, oltre a provider e server basati su XMPP, come Google Talk.</span><span class="sxs-lookup"><span data-stu-id="45e73-142">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="45e73-143">Google Talk è attualmente l'unico partner XMPP supportato.</span><span class="sxs-lookup"><span data-stu-id="45e73-143">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="45e73-144">A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="45e73-144">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="45e73-145">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="45e73-145">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="45e73-146">Messenger fino alla data di chiusura del servizio.</span><span class="sxs-lookup"><span data-stu-id="45e73-146">Messenger until the service shut down date.</span></span> <span data-ttu-id="45e73-147">Data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="45e73-147">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="45e73-148">è stato annunciato.</span><span class="sxs-lookup"><span data-stu-id="45e73-148">has been announced.</span></span> <span data-ttu-id="45e73-149">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="45e73-149">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="45e73-150">Questi scenari funzionano fintanto che tutti i server perimetrali nel pool sono in esecuzione, ma se un server perimetrale non è disponibile, le richieste di questi scenari che verranno inviate non avranno esito positivo, invece di eseguire il routing a un altro Edge Server.</span><span class="sxs-lookup"><span data-stu-id="45e73-150">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="45e73-151">Se si usa la messaggistica unificata di Exchange, è necessario usare un minimo di Exchange 2013 per ottenere il supporto per il bilanciamento del carico DNS di Lync Server sul bordo.</span><span class="sxs-lookup"><span data-stu-id="45e73-151">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="45e73-152">Se si usa una versione precedente di Exchange, gli utenti remoti non avranno funzionalità di failover per questi scenari di messaggistica unificata di Exchange:</span><span class="sxs-lookup"><span data-stu-id="45e73-152">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="45e73-153">Riproduzione della segreteria telefonica aziendale sul telefono</span><span class="sxs-lookup"><span data-stu-id="45e73-153">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="45e73-154">Trasferimento di chiamate da un operatore automatico di messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="45e73-154">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="45e73-155">Tutti gli altri scenari di messaggistica unificata di Exchange funzioneranno correttamente.</span><span class="sxs-lookup"><span data-stu-id="45e73-155">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="45e73-156">L'interfaccia perimetrale interna e l'interfaccia perimetrale esterna devono usare lo stesso tipo di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="45e73-156">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="45e73-157">Non è possibile usare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra.</span><span class="sxs-lookup"><span data-stu-id="45e73-157">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="45e73-158">Distribuzione del bilanciamento del carico DNS nei pool di Edge Server</span><span class="sxs-lookup"><span data-stu-id="45e73-158">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="45e73-159">Per distribuire il bilanciamento del carico DNS nell'interfaccia esterna del pool di Edge Server, sono necessarie le seguenti voci DNS:</span><span class="sxs-lookup"><span data-stu-id="45e73-159">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="45e73-160">Per il servizio Access Edge è necessaria una voce per ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="45e73-160">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="45e73-161">Ogni voce deve risolvere il nome di dominio completo del servizio Access Edge, ad esempio sip.contoso.com, all'indirizzo IP del servizio Access Edge in uno degli Edge Server del pool.</span><span class="sxs-lookup"><span data-stu-id="45e73-161">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="45e73-162">Per il servizio Web Conferencing Edge è necessario immettere una voce per ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="45e73-162">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="45e73-163">Ogni voce deve risolvere il nome di dominio completo del servizio Web Conferencing Edge (ad esempio webconf.contoso.com) nell'indirizzo IP del servizio Web Conferencing Edge in uno degli Edge Server del pool.</span><span class="sxs-lookup"><span data-stu-id="45e73-163">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="45e73-164">Per il servizio Edge audio/video è necessario immettere una voce per ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="45e73-164">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="45e73-165">Ogni voce deve risolvere il nome di dominio completo del servizio Edge audio/video, ad esempio av.contoso.com, all'indirizzo IP del servizio A/V Edge in uno degli Edge Server del pool.</span><span class="sxs-lookup"><span data-stu-id="45e73-165">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="45e73-166">Per distribuire il bilanciamento del carico DNS nell'interfaccia interna del pool di Edge Server, è necessario aggiungere un record DNS, che risolve il nome di dominio completo interno del pool di Edge Server con l'indirizzo IP di ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="45e73-166">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="45e73-167">Uso del bilanciamento del carico DNS nei pool di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="45e73-167">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="45e73-168">È possibile usare il bilanciamento del carico DNS nei pool di Mediation Server autonomi.</span><span class="sxs-lookup"><span data-stu-id="45e73-168">You can use DNS load balancing on stand-alone Mediation Server pools.</span></span> <span data-ttu-id="45e73-169">Tutto il traffico SIP e multimediale è bilanciato dal bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="45e73-169">All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="45e73-170">Per distribuire il bilanciamento del carico DNS in un pool di Mediation Server, è necessario eseguire il provisioning del DNS per risolvere il nome di dominio completo del pool, ad esempio mediationpool1.contoso.com, agli indirizzi IP di tutti i server del pool, ad esempio 192.168.1.1, 192.168.1.2 e così via.</span><span class="sxs-lookup"><span data-stu-id="45e73-170">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="45e73-171">Bloccare il traffico a un server con il bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="45e73-171">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="45e73-172">Se si usa il bilanciamento del carico DNS ed è necessario bloccare il traffico verso un computer specifico, non è sufficiente rimuovere semplicemente le voci di indirizzo IP dall'FQDN del pool.</span><span class="sxs-lookup"><span data-stu-id="45e73-172">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="45e73-173">È necessario rimuovere anche la voce DNS per il computer.</span><span class="sxs-lookup"><span data-stu-id="45e73-173">You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="45e73-174">Tieni presente che per il traffico da server a server, Lync Server 2013 usa il bilanciamento del carico in grado di riconoscere la topologia.</span><span class="sxs-lookup"><span data-stu-id="45e73-174">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="45e73-175">I server leggono la topologia pubblicata in Central Management store per ottenere i nomi di dominio completi dei server nella topologia e distribuiscono automaticamente il traffico tra i server.</span><span class="sxs-lookup"><span data-stu-id="45e73-175">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="45e73-176">Per impedire a un server di ricevere il traffico da server a server, è necessario rimuovere il server dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="45e73-176">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

