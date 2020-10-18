---
title: 'Lync Server 2013: bilanciamento del carico DNS'
description: 'Lync Server 2013: bilanciamento del carico DNS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba95604ca8f4007c76cedea9bf2a16dbd7db455c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574422"
---
# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="aca80-103">Bilanciamento del carico DNS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aca80-103">DNS load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aca80-104">_**Ultimo argomento modificato:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="aca80-104">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="aca80-105">Lync Server consente il bilanciamento del carico DNS, una soluzione software che può ridurre notevolmente il sovraccarico di amministrazione per il bilanciamento del carico sulla rete.</span><span class="sxs-lookup"><span data-stu-id="aca80-105">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="aca80-106">Il bilanciamento del carico DNS bilancia il traffico di rete univoco per Lync Server, ad esempio il traffico SIP e il traffico multimediale.</span><span class="sxs-lookup"><span data-stu-id="aca80-106">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="aca80-107">Se si distribuisce il bilanciamento del carico DNS, il sovraccarico di amministrazione dell'organizzazione per i dispositivi di bilanciamento del carico hardware verrà ridotto a icona.</span><span class="sxs-lookup"><span data-stu-id="aca80-107">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="aca80-108">È inoltre possibile eliminare la complessità legata alla risoluzione dei problemi relativi a una configurazione errata dei servizi di bilanciamento del carico per il traffico SIP.</span><span class="sxs-lookup"><span data-stu-id="aca80-108">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="aca80-109">È anche possibile impedire le connessioni al server, per poter disconnettere i server.</span><span class="sxs-lookup"><span data-stu-id="aca80-109">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="aca80-110">Il bilanciamento del carico DNS garantisce infine che i problemi dei servizi di bilanciamento del carico hardware non influiscano su elementi del traffico SIP, ad esempio il routing delle chiamate di base.</span><span class="sxs-lookup"><span data-stu-id="aca80-110">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="aca80-111">Se si utilizza il bilanciamento del carico DNS, è anche possibile acquistare servizi di bilanciamento del carico hardware a un costo più conveniente rispetto a quello da sostenere se si utilizzano servizi di bilanciamento del carico hardware per tutti i tipi di traffico.</span><span class="sxs-lookup"><span data-stu-id="aca80-111">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="aca80-112">È consigliabile utilizzare i bilanciamento del carico che hanno superato i test di qualificazione per l'interoperabilità con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aca80-112">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="aca80-113">Per informazioni dettagliate sul test di interoperabilità del bilanciamento del carico, vedere "Lync Server 2010 Load Balancer Partners" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) .</span><span class="sxs-lookup"><span data-stu-id="aca80-113">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="aca80-114">Il bilanciamento del carico DNS è supportato per i pool Front End, i pool di server perimetrali, i pool di server Director e i pool di Mediation Server autonomi.</span><span class="sxs-lookup"><span data-stu-id="aca80-114">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="aca80-115">Bilanciamento del carico DNS in pool Front End e pool di server Director</span><span class="sxs-lookup"><span data-stu-id="aca80-115">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="aca80-p104">È possibile utilizzare il bilanciamento del carico DNS per il traffico SIP in pool Front End e pool di server Director. Dopo aver distribuito il bilanciamento del carico DNS, è comunque necessario utilizzare anche servizi di bilanciamento del carico hardware per questi pool, ma solo per il traffico HTTPS da client a server. Il servizio di bilanciamento del carico hardware viene utilizzato per il traffico HTTPS dai client nelle porte 443 e 80.</span><span class="sxs-lookup"><span data-stu-id="aca80-p104">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools. With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic. The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="aca80-119">Sebbene siano comunque necessari servizi di bilanciamento del carico hardware per questi pool, la loro impostazione e l'amministrazione saranno principalmente relative al traffico HTTPS a cui gli amministratori dei servizi di bilanciamento del carico hardware sono abituati.</span><span class="sxs-lookup"><span data-stu-id="aca80-119">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="aca80-120">Bilanciamento del carico DNS e supporto di server e client precedenti</span><span class="sxs-lookup"><span data-stu-id="aca80-120">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="aca80-121">Il bilanciamento del carico DNS supporta il failover automatico solo per i server che eseguono Lync Server 2013 o Lync Server 2010 e per i client Lync 2013 e Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="aca80-121">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="aca80-122">Le versioni precedenti dei client e di Office Communications Server possono comunque connettersi ai pool che eseguono il bilanciamento del carico DNS, ma se non possono stabilire una connessione con il primo server a cui si riferisce il bilanciamento del carico DNS, non sono in grado di eseguire il failover su un altro server del pool.</span><span class="sxs-lookup"><span data-stu-id="aca80-122">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="aca80-123">Inoltre, se si utilizza la messaggistica unificata di Exchange, è necessario utilizzare almeno Exchange 2010 SP1 per ottenere supporto per il bilanciamento del carico DNS di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aca80-123">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="aca80-124">Se si utilizza una versione precedente di Exchange, gli utenti non avranno funzionalità di failover per questi scenari di messaggistica unificata di Exchange:</span><span class="sxs-lookup"><span data-stu-id="aca80-124">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="aca80-125">Riproduzione della segreteria telefonica VoIP aziendale nel telefono</span><span class="sxs-lookup"><span data-stu-id="aca80-125">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="aca80-126">Trasferimento delle chiamate da un Operatore automatico messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="aca80-126">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="aca80-127">Tutti gli altri scenari di messaggistica unificata di Exchange funzioneranno correttamente.</span><span class="sxs-lookup"><span data-stu-id="aca80-127">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="aca80-128">Distribuzione del bilanciamento del carico DNS in pool Front End e pool di server Director</span><span class="sxs-lookup"><span data-stu-id="aca80-128">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="aca80-129">Per la distribuzione del bilanciamento del carico DNS in pool Front End e pool di server Director è necessario eseguire due passaggi aggiuntivi relativi a FQDN e record DNS.</span><span class="sxs-lookup"><span data-stu-id="aca80-129">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="aca80-130">Un pool che utilizza il bilanciamento del carico DNS deve disporre di due nomi di dominio completi (FQDN): il nome di dominio completo del pool standard, che viene utilizzato dal bilanciamento del carico DNS (ad esempio pool01.contoso.com) e che viene risolto negli indirizzi IP fisici dei server del pool e un altro nome di dominio completo per i servizi Web del pool (ad esempio web01.contoso.com), che viene risolto nell'indirizzo IP virtuale del pool.</span><span class="sxs-lookup"><span data-stu-id="aca80-130">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="aca80-131">In Generatore di topologie, se si desidera distribuire il bilanciamento del carico DNS per un pool, per creare questo FQDN supplementare per i servizi Web del pool è necessario selezionare la casella di controllo **Sostituisci FQDN pool di servizi Web interni** e digitare il nome di dominio completo, nella pagina **specificare gli URL dei servizi Web per il pool** .</span><span class="sxs-lookup"><span data-stu-id="aca80-131">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="aca80-p107">Per supportare il nome di dominio completo utilizzato dal bilanciamento del carico DNS, è necessario effettuare il provisioning di DNS per risolvere il nome di dominio completo del pool (ad esempio pool01.contoso.com) negli indirizzi IP di tutti i server del pool (ad esempio 192.168.1.1, 192.168.1.2 e così via). Includere solo gli indirizzi IP dei server attualmente distribuiti.</span><span class="sxs-lookup"><span data-stu-id="aca80-p107">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="aca80-134">Se si dispone di più di un pool Front end o front end server, l'FQDN dei servizi Web esterni deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="aca80-134">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="aca80-135">Ad esempio, se si definisce l'FQDN dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile utilizzare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front end o front end server.</span><span class="sxs-lookup"><span data-stu-id="aca80-135">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="aca80-136">Se si sta distribuendo anche Director, l'FQDN dei servizi Web esterni definiti per qualsiasi server Director o di server Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front end o front-end.</span><span class="sxs-lookup"><span data-stu-id="aca80-136">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="aca80-137">Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="aca80-137">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="aca80-138">Bilanciamento del carico DNS in pool di server perimetrali</span><span class="sxs-lookup"><span data-stu-id="aca80-138">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="aca80-p109">È possibile distribuire il bilanciamento del carico DNS in pool di server perimetrali. In tal caso, è necessario tenere presenti alcune considerazioni.</span><span class="sxs-lookup"><span data-stu-id="aca80-p109">You can deploy DNS load balancing on Edge Server pools. If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="aca80-141">L'utilizzo del bilanciamento del carico DNS nei server perimetrali comporta una perdita della capacità di failover negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="aca80-141">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="aca80-142">Federazione con organizzazioni che eseguono versioni di Office Communications Server rilasciate prima di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aca80-142">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="aca80-143">Scambio di messaggi istantanei con gli utenti di servizi di messaggistica istantanea pubblica AOLand Yahoo \! , oltre ai server e ai provider basati su XMPP, come Google Talk.</span><span class="sxs-lookup"><span data-stu-id="aca80-143">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="aca80-144">Google Talk è attualmente l'unico partner XMPP supportato.</span><span class="sxs-lookup"><span data-stu-id="aca80-144">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="aca80-145">Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="aca80-145">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="aca80-146">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="aca80-146">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="aca80-147">Messenger fino alla data di arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="aca80-147">Messenger until the service shut down date.</span></span> <span data-ttu-id="aca80-148">Una data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="aca80-148">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="aca80-149">sono stati annunciati.</span><span class="sxs-lookup"><span data-stu-id="aca80-149">has been announced.</span></span> <span data-ttu-id="aca80-150">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="aca80-150">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="aca80-151">Questi scenari funzionano a condizione che tutti i server perimetrali nel pool siano in esecuzione, ma se un server perimetrale non è disponibile, tutte le richieste per questi scenari inviate a tale server avranno esito negativo, anziché essere instradate a un altro server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="aca80-151">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="aca80-152">Se si utilizza la messaggistica unificata di Exchange, è necessario utilizzare almeno Exchange 2013 per ottenere il supporto per il bilanciamento del carico DNS di Lync Server su Edge.</span><span class="sxs-lookup"><span data-stu-id="aca80-152">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="aca80-153">Se si utilizza una versione precedente di Exchange, gli utenti remoti non avranno funzionalità di failover per questi scenari di messaggistica unificata di Exchange:</span><span class="sxs-lookup"><span data-stu-id="aca80-153">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="aca80-154">Riproduzione della segreteria telefonica VoIP aziendale nel telefono</span><span class="sxs-lookup"><span data-stu-id="aca80-154">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="aca80-155">Trasferimento delle chiamate da un Operatore automatico messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="aca80-155">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="aca80-156">Tutti gli altri scenari di messaggistica unificata di Exchange funzioneranno correttamente.</span><span class="sxs-lookup"><span data-stu-id="aca80-156">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="aca80-p112">Per l'interfaccia perimetrale interna e per quella esterna è necessario utilizzare lo stesso tipo di bilanciamento del carico. Non è possibile utilizzare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra.</span><span class="sxs-lookup"><span data-stu-id="aca80-p112">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="aca80-159">Distribuzione del bilanciamento del carico DNS in pool di server perimetrali</span><span class="sxs-lookup"><span data-stu-id="aca80-159">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="aca80-160">Per distribuire il bilanciamento del carico DNS nell'interfaccia esterna del pool di server perimetrali, sono necessarie le voci DNS seguenti:</span><span class="sxs-lookup"><span data-stu-id="aca80-160">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="aca80-161">Per il servizio Access Edge, è necessaria una voce per ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="aca80-161">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="aca80-162">Ogni voce deve risolvere il nome di dominio completo del servizio Access Edge, ad esempio sip.contoso.com, nell'indirizzo IP del servizio Access Edge su uno dei server perimetrali del pool.</span><span class="sxs-lookup"><span data-stu-id="aca80-162">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="aca80-163">Per il servizio Web Conferencing Edge, è necessaria una voce per ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="aca80-163">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="aca80-164">Ogni voce deve risolvere il nome di dominio completo del servizio Web Conferencing Edge (ad esempio, webconf.contoso.com) nell'indirizzo IP del servizio Web Conferencing Edge in uno dei server perimetrali del pool.</span><span class="sxs-lookup"><span data-stu-id="aca80-164">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="aca80-165">Per il servizio audio/video Edge, è necessaria una voce per ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="aca80-165">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="aca80-166">Ogni voce deve risolvere il nome di dominio completo del servizio audio/video Edge (ad esempio, av.contoso.com) nell'indirizzo IP del servizio A/V Edge su uno dei server perimetrali nel pool.</span><span class="sxs-lookup"><span data-stu-id="aca80-166">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="aca80-167">Per distribuire il bilanciamento del carico DNS nell'interfaccia interna del pool di server perimetrali, è necessario aggiungere un record A DNS, che consente di risolvere il nome di dominio completo interno del pool di server perimetrali nell'indirizzo IP di ogni server del pool.</span><span class="sxs-lookup"><span data-stu-id="aca80-167">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="aca80-168">Utilizzo del bilanciamento del carico DNS in pool di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="aca80-168">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="aca80-p116">È possibile utilizzare il bilanciamento del carico DNS in pool di Mediation Server autonomi. Tutto il traffico SIP e multimediale viene bilanciato dal bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="aca80-p116">You can use DNS load balancing on stand-alone Mediation Server pools. All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="aca80-171">Per distribuire il bilanciamento del carico DNS in un pool di Mediation Server, è necessario effettuare il provisioning di DNS per risolvere il nome di dominio completo del pool (ad esempio, mediationpool1.contoso.com) negli indirizzi IP di tutti i server del pool (ad esempio 192.168.1.1, 192.168.1.2 e così via).</span><span class="sxs-lookup"><span data-stu-id="aca80-171">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="aca80-172">Blocco del traffico verso un server con bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="aca80-172">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="aca80-173">Se si utilizza il bilanciamento del carico DNS ed è necessario bloccare il traffico verso un computer specifico, non è sufficiente rimuovere solo le voci degli indirizzi IP dal nome di dominio completo del pool.</span><span class="sxs-lookup"><span data-stu-id="aca80-173">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="aca80-174">È necessario rimuovere anche la voce DNS per il computer.</span><span class="sxs-lookup"><span data-stu-id="aca80-174">You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="aca80-175">Si noti che per il traffico da server a server, Lync Server 2013 utilizza il bilanciamento del carico in grado di riconoscere la topologia.</span><span class="sxs-lookup"><span data-stu-id="aca80-175">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="aca80-176">I server leggono la topologia pubblicata nell'archivio di gestione centrale per ottenere i nomi di dominio completi dei server nella topologia e distribuiscono automaticamente il traffico tra i server.</span><span class="sxs-lookup"><span data-stu-id="aca80-176">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="aca80-177">Per bloccare un server dalla ricezione del traffico da server a server, è necessario rimuovere il server dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="aca80-177">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

