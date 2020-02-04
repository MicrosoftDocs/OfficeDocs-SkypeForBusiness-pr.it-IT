---
title: 'Lync Server 2013: Pianificazione della resilienza vocale del sito centrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbeda869c078e6adfce18088545428170b356980
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="639b5-102">Pianificazione della resilienza vocale del sito centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="639b5-102">Planning for central site voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="639b5-103">_**Argomento Ultima modifica:** 2013-10-30_</span><span class="sxs-lookup"><span data-stu-id="639b5-103">_**Topic Last Modified:** 2013-10-30_</span></span>

<span data-ttu-id="639b5-104">Sempre più spesso, le aziende hanno più siti distribuiti in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="639b5-104">Increasingly, enterprises have multiple sites spread across the globe.</span></span> <span data-ttu-id="639b5-105">La gestione dei servizi di emergenza, l'accesso al supporto tecnico e la possibilità di svolgere attività commerciali critiche quando un sito centrale è fuori servizio sono essenziali per qualsiasi soluzione di resilienza vocale aziendale.</span><span class="sxs-lookup"><span data-stu-id="639b5-105">Maintaining emergency services, access to help desk, and the ability to conduct critical business tasks when a central site is out of service is essential for any Enterprise Voice resiliency solution.</span></span> <span data-ttu-id="639b5-106">Quando un sito centrale diventa non disponibile, è necessario che siano soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="639b5-106">When a central site becomes unavailable, the following conditions must be met:</span></span>

  - <span data-ttu-id="639b5-107">Il failover vocale deve essere specificato.</span><span class="sxs-lookup"><span data-stu-id="639b5-107">Voice failover must be provided.</span></span>

  - <span data-ttu-id="639b5-108">Gli utenti che normalmente si iscrivono con il pool Front-end presso il sito centrale devono essere in grado di eseguire la registrazione con un pool di front end alternativo.</span><span class="sxs-lookup"><span data-stu-id="639b5-108">Users who ordinarily register with the Front End pool at the central site must be able to register with an alternative Front End pool.</span></span> <span data-ttu-id="639b5-109">Questa operazione può essere eseguita creando più record SRV DNS, ognuno dei quali viene risolto in un pool di Director o in un pool di front-end in ognuno dei siti centrali.</span><span class="sxs-lookup"><span data-stu-id="639b5-109">This can be done by creating multiple DNS SRV records, each of which resolves to a Director pool or Front End pool in each of your central sites.</span></span> <span data-ttu-id="639b5-110">È possibile modificare la priorità e i pesi dei record SRV in modo che gli utenti serviti da tale sito centrale ottengano il relativo Director e il pool Front end prima di quelli presenti in altri record SRV.</span><span class="sxs-lookup"><span data-stu-id="639b5-110">You can adjust the priority and weights of the SRV records so that users who are served by that central site get the corresponding Director and Front End pool ahead of those in other SRV records.</span></span>

  - <span data-ttu-id="639b5-111">Le chiamate da e verso gli utenti che si trovano in altri siti devono essere reinstradate alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="639b5-111">Calls to and from users located at other sites must be rerouted to the PSTN.</span></span>

<span data-ttu-id="639b5-112">Questo argomento descrive la soluzione consigliata per la protezione della resilienza vocale del sito centrale.</span><span class="sxs-lookup"><span data-stu-id="639b5-112">This topic describes the recommended solution for securing central site voice resiliency.</span></span>

<div>

## <a name="architecture-and-topology"></a><span data-ttu-id="639b5-113">Architettura e topologia</span><span class="sxs-lookup"><span data-stu-id="639b5-113">Architecture and Topology</span></span>

<span data-ttu-id="639b5-114">La pianificazione della resilienza vocale in un sito centrale richiede una conoscenza di base del ruolo centrale svolto dal registrar di Lync Server 2013 per abilitare il failover vocale.</span><span class="sxs-lookup"><span data-stu-id="639b5-114">Planning for voice resiliency at a central site requires a basic understanding of the central role played by the Lync Server 2013 Registrar in enabling voice failover.</span></span> <span data-ttu-id="639b5-115">Il registrar di Lync Server è un ruolo del server che consente la registrazione e l'autenticazione del client e fornisce servizi di routing.</span><span class="sxs-lookup"><span data-stu-id="639b5-115">The Lync Server Registrar is a server role that enables client registration and authentication and provides routing services.</span></span> <span data-ttu-id="639b5-116">Si trova insieme ad altri componenti in un server standard, Front End Server, Director o Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="639b5-116">It resides along with other components on a Standard Edition server, Front End Server, Director, or Survivable Branch Appliance.</span></span> <span data-ttu-id="639b5-117">Un pool di registrar è costituito da servizi di registrazione eseguiti nel pool Front-end e residenti nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="639b5-117">A Registrar pool consists of Registrar Services running on the Front End pool and residing at the same site.</span></span> <span data-ttu-id="639b5-118">Il pool Front-end deve essere in bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="639b5-118">The Front End pool must be load balanced.</span></span> <span data-ttu-id="639b5-119">È consigliabile il bilanciamento del carico DNS, ma il bilanciamento del carico hardware è accettabile.</span><span class="sxs-lookup"><span data-stu-id="639b5-119">DNS load balancing is recommended, but hardware load balancing is acceptable.</span></span> <span data-ttu-id="639b5-120">Un client Lync individua il pool Front-end tramite il meccanismo di individuazione seguente:</span><span class="sxs-lookup"><span data-stu-id="639b5-120">A Lync client discovers the Front End pool through the following discovery mechanism:</span></span>

1.  <span data-ttu-id="639b5-121">Record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="639b5-121">DNS SRV record</span></span>

2.  <span data-ttu-id="639b5-122">Servizio Web AutoDiscovery (nuovo in Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="639b5-122">Autodiscovery Web Service (new in Lync Server 2013)</span></span>

3.  <span data-ttu-id="639b5-123">Opzione DHCP 120</span><span class="sxs-lookup"><span data-stu-id="639b5-123">DHCP option 120</span></span>

<span data-ttu-id="639b5-124">Dopo che il client Lync si connette al pool Front-End, viene indirizzato dal bilanciamento del carico a uno dei server front-end nel pool.</span><span class="sxs-lookup"><span data-stu-id="639b5-124">After the Lync client connects to the Front End pool, it is directed by the load balancer to one of the Front End Servers in the pool.</span></span> <span data-ttu-id="639b5-125">Il server front-end, a sua volta, reindirizza il client a un registrar preferito nel pool.</span><span class="sxs-lookup"><span data-stu-id="639b5-125">That Front End Server, in turn, redirects the client to a preferred Registrar in the pool.</span></span>

<span data-ttu-id="639b5-126">Ogni utente abilitato per VoIP aziendale viene assegnato a un pool di registrar specifico, che diventa il pool di registrar principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="639b5-126">Each user enabled for Enterprise Voice is assigned to a particular Registrar pool, which becomes that user’s primary Registrar pool.</span></span> <span data-ttu-id="639b5-127">In un sito specifico, centinaia o migliaia di utenti condividono in genere un singolo pool di registrar principale.</span><span class="sxs-lookup"><span data-stu-id="639b5-127">At a given site, hundreds or thousands of users typically share a single primary Registrar pool.</span></span> <span data-ttu-id="639b5-128">Per tenere conto del consumo di risorse del sito centrale da parte di tutti gli utenti del sito della filiale che si basano sul sito centrale per presenza, conferenza o failover, è consigliabile considerare ogni utente del sito filiale come se l'utente fosse un utente registrato nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="639b5-128">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as though the user were a user registered with the central site.</span></span> <span data-ttu-id="639b5-129">Attualmente non esistono limiti al numero di utenti del sito succursale, inclusi gli utenti registrati con un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="639b5-129">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>

<span data-ttu-id="639b5-130">Per garantire la resilienza vocale in caso di errore di un sito centrale, il pool di registrar principale deve avere un unico pool di registrar di backup designato situato in un altro sito.</span><span class="sxs-lookup"><span data-stu-id="639b5-130">To assure voice resiliency in the event of a central site failure, the primary Registrar pool must have a single designated backup Registrar pool located at another site.</span></span> <span data-ttu-id="639b5-131">Il backup può essere configurato usando le impostazioni di resilienza del generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="639b5-131">The backup can be configured by using Topology Builder resiliency settings.</span></span> <span data-ttu-id="639b5-132">Supponendo che un collegamento WAN resiliente tra i due siti, gli utenti il cui pool di registrar principale non è più disponibile vengano automaticamente indirizzati al pool di registrar di backup.</span><span class="sxs-lookup"><span data-stu-id="639b5-132">Assuming a resilient WAN link between the two sites, users whose primary Registrar pool is no longer available are automatically directed to the backup Registrar pool.</span></span>

<span data-ttu-id="639b5-133">I passaggi seguenti descrivono il processo di individuazione e registrazione del client:</span><span class="sxs-lookup"><span data-stu-id="639b5-133">The following steps describe the client discovery and registration process:</span></span>

1.  <span data-ttu-id="639b5-134">Un client individua Lync Server tramite i record SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="639b5-134">A client discovers Lync Server through DNS SRV records.</span></span> <span data-ttu-id="639b5-135">In Lync Server 2013 i record SRV DNS possono essere configurati in grado di restituire più di un FQDN alla query SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="639b5-135">In Lync Server 2013, DNS SRV records can be configured to return more than one FQDN to the DNS SRV query.</span></span> <span data-ttu-id="639b5-136">Ad esempio, se Enterprise Contoso ha tre siti centrali (Nord America, Europa e Asia-Pacifico) e un pool di Director in ogni sito centrale, i record SRV DNS possono puntare agli FQDN del pool di Director in ognuna delle tre posizioni.</span><span class="sxs-lookup"><span data-stu-id="639b5-136">For example, if enterprise Contoso has three central sites (North America, Europe, and Asia-Pacific) and a Director pool at each central site, DNS SRV records can point to the Director pool FQDNs in each of the three locations.</span></span> <span data-ttu-id="639b5-137">Purché il pool di Director in una delle posizioni sia disponibile, il client può connettersi al primo server Lync hop.</span><span class="sxs-lookup"><span data-stu-id="639b5-137">As long as the Director pool in one of the locations is available, the client can connect to the first hop Lync Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="639b5-138">L'uso di un pool di Director è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="639b5-138">Using a Director pool is optional.</span></span> <span data-ttu-id="639b5-139">È invece possibile usare un pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="639b5-139">A Front End pool can be used instead.</span></span>

    
    </div>

2.  <span data-ttu-id="639b5-140">Il pool di Director informa il client Lync sul pool di registrar principale dell'utente e sul pool di registrar di backup.</span><span class="sxs-lookup"><span data-stu-id="639b5-140">The Director pool informs the Lync client about the user’s primary Registrar pool and backup Registrar pool.</span></span>

3.  <span data-ttu-id="639b5-141">Il client Lync tenta innanzitutto di connettersi al pool di registrar principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="639b5-141">The Lync client attempts to connect to the user’s primary Registrar pool first.</span></span> <span data-ttu-id="639b5-142">Se il pool di registrar principale è disponibile, il registrar accetta la registrazione.</span><span class="sxs-lookup"><span data-stu-id="639b5-142">If the primary Registrar pool is available, the Registrar accepts the registration.</span></span> <span data-ttu-id="639b5-143">Se il pool di registrar principale non è disponibile, il client Lync tenterà di connettersi al pool di registrazione di backup.</span><span class="sxs-lookup"><span data-stu-id="639b5-143">If the primary Registrar pool is unavailable, the Lync client attempts to connect to the backup Registrar pool.</span></span> <span data-ttu-id="639b5-144">Se il pool di registrar di backup è disponibile e ha determinato che il pool di registrar principale dell'utente non è disponibile (rilevando una mancanza di heartbeat per un intervallo di failover specificato), il pool di registrar accetta la registrazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="639b5-144">If the backup Registrar pool is available and has determined that the user’s primary Registrar pool is unavailable (by detecting a lack of heartbeat for a specified failover interval) the backup Registrar pool accepts the user’s registration.</span></span> <span data-ttu-id="639b5-145">Dopo che il registrar di backup rileva che il registrar principale è di nuovo disponibile, il pool di registrazione backup reindirizza i client Lync di failover nel pool principale.</span><span class="sxs-lookup"><span data-stu-id="639b5-145">After the backup Registrar detects that the primary Registrar is again available, the backup Registrar pool will redirect failover Lync clients to their primary pool.</span></span>

<span data-ttu-id="639b5-146">La figura seguente mostra la topologia consigliata per garantire la resilienza del sito centrale.</span><span class="sxs-lookup"><span data-stu-id="639b5-146">The following figure shows the recommended topology for assuring central site resiliency.</span></span> <span data-ttu-id="639b5-147">I due siti sono collegati da un collegamento WAN resiliente.</span><span class="sxs-lookup"><span data-stu-id="639b5-147">The two sites are connected by a resilient WAN link.</span></span> <span data-ttu-id="639b5-148">Se il sito centrale diventa non disponibile, gli utenti assegnati a tale pool vengono indirizzati al sito di backup per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="639b5-148">If the central site becomes unavailable, users who are assigned to that pool are directed to the backup site for registration.</span></span>

<span data-ttu-id="639b5-149">**Topologia consigliata per la resilienza vocale del sito centrale**</span><span class="sxs-lookup"><span data-stu-id="639b5-149">**Recommended topology for central site voice resiliency**</span></span>

<span data-ttu-id="639b5-150">![Topologia per la resilienza vocale del sito centrale](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topologia per la resilienza vocale del sito centrale")</span><span class="sxs-lookup"><span data-stu-id="639b5-150">![Topology for central site voice resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topology for central site voice resliency")</span></span>

</div>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="639b5-151">Requisiti e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="639b5-151">Requirements and Recommendations</span></span>

<span data-ttu-id="639b5-152">I requisiti e le raccomandazioni seguenti per l'implementazione della resilienza vocale del sito centrale sono appropriati per la maggior parte delle organizzazioni:</span><span class="sxs-lookup"><span data-stu-id="639b5-152">The following requirements and recommendations for implementing central site voice resiliency are appropriate for most organizations:</span></span>

  - <span data-ttu-id="639b5-153">I siti in cui risiedono i pool di registrar primari e di backup devono essere connessi da un collegamento WAN resiliente.</span><span class="sxs-lookup"><span data-stu-id="639b5-153">The sites in which the primary and backup Registrar pools reside should be connected by a resilient WAN link.</span></span>

  - <span data-ttu-id="639b5-154">Ogni sito centrale deve contenere un pool di registrar costituito da uno o più registrar.</span><span class="sxs-lookup"><span data-stu-id="639b5-154">Each central site must contain a Registrar pool consisting of one or more Registrars.</span></span>

  - <span data-ttu-id="639b5-155">Ogni pool di registrar deve essere bilanciato tramite bilanciamento del carico DNS, bilanciamento del carico hardware o entrambi.</span><span class="sxs-lookup"><span data-stu-id="639b5-155">Each Registrar pool must be load-balanced by using DNS load balancing, hardware load balancing, or both.</span></span> <span data-ttu-id="639b5-156">Per informazioni dettagliate sulla pianificazione della configurazione del bilanciamento del carico, vedere [requisiti di bilanciamento del carico per Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="639b5-156">For detailed information about planning your load balancing configuration, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="639b5-157">Ogni utente deve essere assegnato a un pool di registrar principale usando il cmdlet **Set-CsUser** di Lync Server Management Shell o il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="639b5-157">Each user must be assigned to a primary Registrar pool by using either the Lync Server Management Shell **set-CsUser** cmdlet or the Lync Server Control Panel.</span></span>

  - <span data-ttu-id="639b5-158">Il pool di registrar principale deve avere un singolo pool di registrar di backup situato in un sito centrale diverso.</span><span class="sxs-lookup"><span data-stu-id="639b5-158">The primary Registrar pool must have a single backup Registrar pool located in a different central site.</span></span>

  - <span data-ttu-id="639b5-159">Il pool di registrar principale deve essere configurato per il failover nel pool di registrazione di backup.</span><span class="sxs-lookup"><span data-stu-id="639b5-159">The primary Registrar pool must be configured to fail over to the backup Registrar pool.</span></span> <span data-ttu-id="639b5-160">Per impostazione predefinita, il registrar principale è impostato per il failover nel pool di registrar di backup dopo un intervallo di 300 secondi.</span><span class="sxs-lookup"><span data-stu-id="639b5-160">By default, the primary Registrar is set to fail over to the backup Registrar pool after an interval of 300 seconds.</span></span> <span data-ttu-id="639b5-161">Puoi modificare questo intervallo usando il generatore di topologia di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="639b5-161">You can change this interval by using the Lync Server 2013 Topology Builder.</span></span>

  - <span data-ttu-id="639b5-162">Configurare una route di failover, come descritto nella sezione "[configurazione di una route di failover in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)" nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="639b5-162">Configure a failover route, as described in the “[Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)” topic in the Planning documentation.</span></span> <span data-ttu-id="639b5-163">Quando si configura la route, specificare un gateway che si trova in un sito diverso dal gateway specificato nella route principale.</span><span class="sxs-lookup"><span data-stu-id="639b5-163">When configuring the route, specify a gateway that is located at a different site from the gateway specified in the primary route.</span></span>

  - <span data-ttu-id="639b5-164">Se il sito centrale conteneva il server di gestione principale e probabilmente il sito è in calo per un periodo prolungato, sarà necessario reinstallare gli strumenti di gestione nel sito di backup. in caso contrario, non sarà possibile modificare le impostazioni di gestione.</span><span class="sxs-lookup"><span data-stu-id="639b5-164">If the central site contained your primary management server and the site is likely to be down for an extended period, you will need to reinstall your management tools at the backup site; otherwise, you won’t be able to change any management settings.</span></span>

</div>

<div>

## <a name="dependencies"></a><span data-ttu-id="639b5-165">Dipendenze</span><span class="sxs-lookup"><span data-stu-id="639b5-165">Dependencies</span></span>

<span data-ttu-id="639b5-166">Lync Server dipende dai componenti di infrastruttura e software seguenti per assicurare la resilienza vocale:</span><span class="sxs-lookup"><span data-stu-id="639b5-166">Lync Server depends on the following infrastructure and software components to assure voice resiliency:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="639b5-167"><strong>Componente</strong></span><span class="sxs-lookup"><span data-stu-id="639b5-167"><strong>Component</strong></span></span></p></td>
<td><p><span data-ttu-id="639b5-168"><strong>Funzionale</strong></span><span class="sxs-lookup"><span data-stu-id="639b5-168"><strong>Functional</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="639b5-169">DNS</span><span class="sxs-lookup"><span data-stu-id="639b5-169">DNS</span></span></p></td>
<td><p><span data-ttu-id="639b5-170">Risoluzione di record SRV e record per la connettività server-server e client-server</span><span class="sxs-lookup"><span data-stu-id="639b5-170">Resolving SRV records and A records for server-server and server-client connectivity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="639b5-171">Servizi Web Exchange e Exchange (EWS)</span><span class="sxs-lookup"><span data-stu-id="639b5-171">Exchange and Exchange Web Services (EWS)</span></span></p></td>
<td><p><span data-ttu-id="639b5-172">Archiviazione contatti; dati del calendario</span><span class="sxs-lookup"><span data-stu-id="639b5-172">Contact storage; calendar data</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="639b5-173">Servizi Web di Exchange e messaggistica unificata</span><span class="sxs-lookup"><span data-stu-id="639b5-173">Exchange Unified Messaging and Exchange Web Services</span></span></p></td>
<td><p><span data-ttu-id="639b5-174">Registri delle chiamate, elenco della segreteria telefonica, casella vocale</span><span class="sxs-lookup"><span data-stu-id="639b5-174">Call logs, voice mail list, voice mail</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="639b5-175">Opzioni DHCP 120</span><span class="sxs-lookup"><span data-stu-id="639b5-175">DHCP Options 120</span></span></p></td>
<td><p><span data-ttu-id="639b5-176">Se DNS SRV non è disponibile, il client tenterà di usare l'opzione DHCP 120 per individuare il registrar.</span><span class="sxs-lookup"><span data-stu-id="639b5-176">If DNS SRV is unavailable, the client will attempt to use DHCP Option 120 to discover the Registrar.</span></span> <span data-ttu-id="639b5-177">Affinché questo funzioni, è necessario configurare un server DHCP o abilitare il protocollo DHCP di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="639b5-177">For this to work, either a DHCP server must be configured or Lync Server 2013 DHCP must be enabled.</span></span> <span data-ttu-id="639b5-178">Per informazioni dettagliate, vedere Requisiti hardware e software per la resilienza dei siti di succursale in <a href="lync-server-2013-branch-site-resiliency-requirements.md">requisiti di resilienza dei siti di filiale per la sezione Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="639b5-178">For details, see Hardware and Software Requirements for Branch-Site Resiliency in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</a> section.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a><span data-ttu-id="639b5-179">Funzionalità vocali Survivable</span><span class="sxs-lookup"><span data-stu-id="639b5-179">Survivable Voice Features</span></span>

<span data-ttu-id="639b5-180">Se sono stati implementati i requisiti e le raccomandazioni precedenti, le funzionalità vocali seguenti verranno fornite dal pool di registrazione di backup:</span><span class="sxs-lookup"><span data-stu-id="639b5-180">If the preceding requirements and recommendations have been implemented, the following voice features will be provided by the backup Registrar pool:</span></span>

  - <span data-ttu-id="639b5-181">Chiamate PSTN in uscita</span><span class="sxs-lookup"><span data-stu-id="639b5-181">Outbound PSTN calls</span></span>

  - <span data-ttu-id="639b5-182">Chiamate PSTN in ingresso, se il provider del servizio di telefonia supporta la possibilità di eseguire il failover in un sito di backup</span><span class="sxs-lookup"><span data-stu-id="639b5-182">Inbound PSTN calls, if the telephony service provider supports the ability to fail over to a backup site</span></span>

  - <span data-ttu-id="639b5-183">Chiamate aziendali tra utenti sia nello stesso sito che tra due siti diversi</span><span class="sxs-lookup"><span data-stu-id="639b5-183">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="639b5-184">Gestione delle chiamate di base, incluso il blocco delle chiamate, il recupero e il trasferimento</span><span class="sxs-lookup"><span data-stu-id="639b5-184">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="639b5-185">Messaggistica istantanea con due parti e condivisione di audio e video tra utenti nello stesso sito</span><span class="sxs-lookup"><span data-stu-id="639b5-185">Two-party instant messaging and sharing audio and video between users at the same site</span></span>

  - <span data-ttu-id="639b5-186">Inoltro di chiamata, squillo simultaneo di endpoint, delegazione delle chiamate e servizi di chiamata del team, ma solo se entrambe le parti per chiamare delegazione o tutti i membri del team sono configurate nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="639b5-186">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if both parties to call delegation, or all team members, are configured at the same site.</span></span>

  - <span data-ttu-id="639b5-187">I telefoni e i client esistenti continuano a funzionare.</span><span class="sxs-lookup"><span data-stu-id="639b5-187">Existing phones and clients continue to work.</span></span>

  - <span data-ttu-id="639b5-188">Registrazione dettagli chiamata (CDR)</span><span class="sxs-lookup"><span data-stu-id="639b5-188">Call detail recording (CDR)</span></span>

  - <span data-ttu-id="639b5-189">Autenticazione e autorizzazione</span><span class="sxs-lookup"><span data-stu-id="639b5-189">Authentication and authorization</span></span>

<span data-ttu-id="639b5-190">A seconda del modo in cui sono configurate, le funzionalità vocali seguenti potrebbero non funzionare quando un sito centrale principale non è più in servizio:</span><span class="sxs-lookup"><span data-stu-id="639b5-190">Depending on how they are configured, the following voice features may or may not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="639b5-191">Deposito e recupero della segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="639b5-191">Voice mail deposit and retrieval</span></span>
    
    <span data-ttu-id="639b5-192">Se si vuole rendere disponibile la messaggistica unificata di Exchange quando il sito centrale principale non è in servizio, è necessario eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="639b5-192">If you want to make Exchange UM available when the primary central site is out of service, you must do one of the following:</span></span>
    
      - <span data-ttu-id="639b5-193">Modificare i record SRV DNS in modo che i server di messaggistica unificata di Exchange nel sito centrale puntino ai server di messaggistica unificata di Exchange in un altro sito.</span><span class="sxs-lookup"><span data-stu-id="639b5-193">Change DNS SRV records so that the Exchange UM servers at the central site point to backup Exchange UM servers at another site.</span></span>
    
      - <span data-ttu-id="639b5-194">Configurare il dial plan di messaggistica unificata di Exchange di ogni utente per includere i server di messaggistica unificata di Exchange sia nel sito centrale che nel sito di backup, ma designa i server di messaggistica unificata di Exchange come disabilitati.</span><span class="sxs-lookup"><span data-stu-id="639b5-194">Configure each user’s Exchange UM dial plan to include Exchange UM servers at both the central site and the backup site, but designate the backup Exchange UM servers as disabled.</span></span> <span data-ttu-id="639b5-195">Se il sito principale diventa non disponibile, l'amministratore di Exchange deve contrassegnare i server di messaggistica unificata di Exchange nel sito di backup come abilitato.</span><span class="sxs-lookup"><span data-stu-id="639b5-195">If the primary site becomes unavailable, the Exchange administrator has to mark the Exchange UM servers at the backup site as enabled.</span></span>
    
    <span data-ttu-id="639b5-196">Se nessuna delle soluzioni precedenti è possibile, la messaggistica unificata di Exchange non sarà disponibile in caso il sito centrale diventi non disponibile.</span><span class="sxs-lookup"><span data-stu-id="639b5-196">If neither of the preceding solutions is possible, then Exchange UM will not be available in the event the central site becomes unavailable.</span></span>

  - <span data-ttu-id="639b5-197">Conferenze di tutti i tipi</span><span class="sxs-lookup"><span data-stu-id="639b5-197">Conferencing of all types</span></span>
    
    <span data-ttu-id="639b5-198">Un utente che ha eseguito il failover in un sito di backup può partecipare a una conferenza creata o ospitata da un organizzatore il cui pool è disponibile, ma non può creare o ospitare una conferenza nel proprio pool principale, che non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="639b5-198">A user who has failed over to a backup site can join a conference that is created or hosted by an organizer whose pool is available but cannot create or host a conference on his or her own primary pool, which is no longer available.</span></span> <span data-ttu-id="639b5-199">Analogamente, altri utenti non possono partecipare a conferenze ospitate nel pool principale dell'utente interessato.</span><span class="sxs-lookup"><span data-stu-id="639b5-199">Similarly, others users cannot join conferences that are hosted on the affected user’s primary pool.</span></span>

<span data-ttu-id="639b5-200">Le funzionalità vocali seguenti non funzionano quando un sito centrale principale non è più in servizio:</span><span class="sxs-lookup"><span data-stu-id="639b5-200">The following voice features do not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="639b5-201">Operatore automatico conferenza</span><span class="sxs-lookup"><span data-stu-id="639b5-201">Conference Auto-Attendant</span></span>

  - <span data-ttu-id="639b5-202">Presenza e routing basato su DND</span><span class="sxs-lookup"><span data-stu-id="639b5-202">Presence and DND-based routing</span></span>

  - <span data-ttu-id="639b5-203">Aggiornamento delle impostazioni di inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="639b5-203">Updating call forwarding settings</span></span>

  - <span data-ttu-id="639b5-204">Servizio Response Group e parcheggio delle chiamate</span><span class="sxs-lookup"><span data-stu-id="639b5-204">Response Group service and Call Park</span></span>

  - <span data-ttu-id="639b5-205">Provisioning di nuovi telefoni e client</span><span class="sxs-lookup"><span data-stu-id="639b5-205">Provisioning new phones and clients</span></span>

  - <span data-ttu-id="639b5-206">Ricerca Web Rubrica</span><span class="sxs-lookup"><span data-stu-id="639b5-206">Address Book Web Search</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="639b5-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="639b5-207">See Also</span></span>


[<span data-ttu-id="639b5-208">Pianificazione della resilienza vocale del sito di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="639b5-208">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

