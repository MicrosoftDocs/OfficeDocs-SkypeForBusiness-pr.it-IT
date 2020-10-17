---
title: 'Lync Server 2013: pianificazione della resilienza vocale del sito centrale'
description: 'Lync Server 2013: pianificazione della resilienza vocale del sito centrale.'
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
ms.openlocfilehash: dd41943212459311abdb64b3ed77c918539d082d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567382"
---
# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="31535-103">Pianificazione della resilienza vocale del sito centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31535-103">Planning for central site voice resiliency in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31535-104">_**Ultimo argomento modificato:** 2013-10-30_</span><span class="sxs-lookup"><span data-stu-id="31535-104">_**Topic Last Modified:** 2013-10-30_</span></span>

<span data-ttu-id="31535-105">Le aziende dispongono sempre più spesso di diversi siti sparsi in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="31535-105">Increasingly, enterprises have multiple sites spread across the globe.</span></span> <span data-ttu-id="31535-106">La gestione dei servizi di emergenza, l'accesso al supporto tecnico e la possibilità di svolgere attività aziendali critiche quando un sito centrale è fuori servizio è essenziale per qualsiasi soluzione di resilienza VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="31535-106">Maintaining emergency services, access to help desk, and the ability to conduct critical business tasks when a central site is out of service is essential for any Enterprise Voice resiliency solution.</span></span> <span data-ttu-id="31535-107">Quando un sito centrale diventa non disponibile, devono essere soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="31535-107">When a central site becomes unavailable, the following conditions must be met:</span></span>

  - <span data-ttu-id="31535-108">Deve essere predisposto il failover dei servizi vocali.</span><span class="sxs-lookup"><span data-stu-id="31535-108">Voice failover must be provided.</span></span>

  - <span data-ttu-id="31535-109">Gli utenti che normalmente si iscrivono al pool Front End nel sito centrale devono essere in grado di registrarsi con un pool Front End alternativo.</span><span class="sxs-lookup"><span data-stu-id="31535-109">Users who ordinarily register with the Front End pool at the central site must be able to register with an alternative Front End pool.</span></span> <span data-ttu-id="31535-110">A tale scopo, è possibile creare più record SRV DNS, ognuno dei quali viene risolto in un pool di server Director o in un pool Front end in ognuno dei siti centrali.</span><span class="sxs-lookup"><span data-stu-id="31535-110">This can be done by creating multiple DNS SRV records, each of which resolves to a Director pool or Front End pool in each of your central sites.</span></span> <span data-ttu-id="31535-111">È possibile modificare la priorità e i pesi dei record SRV in modo che gli utenti serviti da tale sito centrale ottengano il server Director e il pool Front end corrispondenti rispetto a quelli presenti in altri record SRV.</span><span class="sxs-lookup"><span data-stu-id="31535-111">You can adjust the priority and weights of the SRV records so that users who are served by that central site get the corresponding Director and Front End pool ahead of those in other SRV records.</span></span>

  - <span data-ttu-id="31535-112">Le chiamate verso e da utenti in altri siti devono essere reindirizzate al PSTN.</span><span class="sxs-lookup"><span data-stu-id="31535-112">Calls to and from users located at other sites must be rerouted to the PSTN.</span></span>

<span data-ttu-id="31535-113">Questo argomento descrive la soluzione consigliata per la protezione della resilienza dei servizi vocali del sito centrale.</span><span class="sxs-lookup"><span data-stu-id="31535-113">This topic describes the recommended solution for securing central site voice resiliency.</span></span>

<div>

## <a name="architecture-and-topology"></a><span data-ttu-id="31535-114">Architettura e topologia</span><span class="sxs-lookup"><span data-stu-id="31535-114">Architecture and Topology</span></span>

<span data-ttu-id="31535-115">La pianificazione della resilienza vocale in un sito centrale richiede una conoscenza di base del ruolo centrale svolto dal registrar di Lync Server 2013 per abilitare il failover vocale.</span><span class="sxs-lookup"><span data-stu-id="31535-115">Planning for voice resiliency at a central site requires a basic understanding of the central role played by the Lync Server 2013 Registrar in enabling voice failover.</span></span> <span data-ttu-id="31535-116">Il servizio di registrazione di Lync Server è un ruolo del server che consente la registrazione e l'autenticazione dei client e fornisce servizi di routing.</span><span class="sxs-lookup"><span data-stu-id="31535-116">The Lync Server Registrar is a server role that enables client registration and authentication and provides routing services.</span></span> <span data-ttu-id="31535-117">Esso risiede insieme ad altri componenti di un server Standard Edition, Front End Server, Director o Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="31535-117">It resides along with other components on a Standard Edition server, Front End Server, Director, or Survivable Branch Appliance.</span></span> <span data-ttu-id="31535-118">Un pool di registrazione è costituito da servizi di registrazione in esecuzione nel pool Front end e risiede nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="31535-118">A Registrar pool consists of Registrar Services running on the Front End pool and residing at the same site.</span></span> <span data-ttu-id="31535-119">Il pool Front end deve essere bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="31535-119">The Front End pool must be load balanced.</span></span> <span data-ttu-id="31535-120">È consigliabile usare il bilanciamento del carico DNS, ma una soluzione di bilanciamento del carico hardware è comunque accettabile.</span><span class="sxs-lookup"><span data-stu-id="31535-120">DNS load balancing is recommended, but hardware load balancing is acceptable.</span></span> <span data-ttu-id="31535-121">Un client Lync individua il pool Front end tramite il meccanismo di individuazione seguente:</span><span class="sxs-lookup"><span data-stu-id="31535-121">A Lync client discovers the Front End pool through the following discovery mechanism:</span></span>

1.  <span data-ttu-id="31535-122">Record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="31535-122">DNS SRV record</span></span>

2.  <span data-ttu-id="31535-123">Servizio Web di individuazione automatica (nuovo in Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="31535-123">Autodiscovery Web Service (new in Lync Server 2013)</span></span>

3.  <span data-ttu-id="31535-124">Opzione DHCP 120</span><span class="sxs-lookup"><span data-stu-id="31535-124">DHCP option 120</span></span>

<span data-ttu-id="31535-125">Dopo la connessione del client Lync al pool Front End, il bilanciamento del carico viene indirizzato a uno dei front end server nel pool.</span><span class="sxs-lookup"><span data-stu-id="31535-125">After the Lync client connects to the Front End pool, it is directed by the load balancer to one of the Front End Servers in the pool.</span></span> <span data-ttu-id="31535-126">Il front end server, a sua sua scelta, reindirizza il client a un registrar preferito nel pool.</span><span class="sxs-lookup"><span data-stu-id="31535-126">That Front End Server, in turn, redirects the client to a preferred Registrar in the pool.</span></span>

<span data-ttu-id="31535-127">Ogni utente abilitato per VoIP aziendale viene assegnato a un pool di registrazione specifico, che diventa il pool di registrazione principale di tale utente.</span><span class="sxs-lookup"><span data-stu-id="31535-127">Each user enabled for Enterprise Voice is assigned to a particular Registrar pool, which becomes that user’s primary Registrar pool.</span></span> <span data-ttu-id="31535-128">In ogni sito, un singolo pool di registrazione principale è solitamente condiviso da centinaia o migliaia di utenti.</span><span class="sxs-lookup"><span data-stu-id="31535-128">At a given site, hundreds or thousands of users typically share a single primary Registrar pool.</span></span> <span data-ttu-id="31535-129">Per pianificare il consumo delle risorse del sito centrale da parte di eventuali utenti di siti di succursale che si basano sul sito centrale per i servizi di presenza, conferenza o failover, è consigliabile considerare ogni utente di sito di succursale come se fosse un utente registrato nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="31535-129">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as though the user were a user registered with the central site.</span></span> <span data-ttu-id="31535-130">Al momento non sono presenti limiti al numero di utenti di siti di succursale, compresi gli utenti registrati con un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="31535-130">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>

<span data-ttu-id="31535-131">Per garantire la resilienza dei servizi vocali in caso di errore del sito centrale, per il pool di registrazione principale deve esistere un singolo pool di registrazione di backup designato in un altro sito.</span><span class="sxs-lookup"><span data-stu-id="31535-131">To assure voice resiliency in the event of a central site failure, the primary Registrar pool must have a single designated backup Registrar pool located at another site.</span></span> <span data-ttu-id="31535-132">Il backup può essere configurato utilizzando le impostazioni di resilienza del generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="31535-132">The backup can be configured by using Topology Builder resiliency settings.</span></span> <span data-ttu-id="31535-133">Presupponendo l'esistenza di un collegamento WAN resiliente tra due siti, gli utenti per cui non è più disponibile il pool di registrazione principale verranno reindirizzati automaticamente al pool di registrazione di backup.</span><span class="sxs-lookup"><span data-stu-id="31535-133">Assuming a resilient WAN link between the two sites, users whose primary Registrar pool is no longer available are automatically directed to the backup Registrar pool.</span></span>

<span data-ttu-id="31535-134">I passaggi seguenti descrivono il processo di individuazione e registrazione dei client:</span><span class="sxs-lookup"><span data-stu-id="31535-134">The following steps describe the client discovery and registration process:</span></span>

1.  <span data-ttu-id="31535-135">Un client individua Lync Server tramite record DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="31535-135">A client discovers Lync Server through DNS SRV records.</span></span> <span data-ttu-id="31535-136">In Lync Server 2013, i record DNS SRV possono essere configurati in modo da restituire più FQDN alla query DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="31535-136">In Lync Server 2013, DNS SRV records can be configured to return more than one FQDN to the DNS SRV query.</span></span> <span data-ttu-id="31535-137">Ad esempio, se l'azienda Contoso dispone di tre siti centrali (Nord America, Europa e Asia-Pacifico) e un pool di server Director in ogni sito centrale, i record DNS SRV possono puntare ai nomi FQDN del pool di server Director in ognuna delle tre posizioni.</span><span class="sxs-lookup"><span data-stu-id="31535-137">For example, if enterprise Contoso has three central sites (North America, Europe, and Asia-Pacific) and a Director pool at each central site, DNS SRV records can point to the Director pool FQDNs in each of the three locations.</span></span> <span data-ttu-id="31535-138">Fintanto che il pool di server Director in uno dei percorsi è disponibile, il client può connettersi al primo server Lync hop.</span><span class="sxs-lookup"><span data-stu-id="31535-138">As long as the Director pool in one of the locations is available, the client can connect to the first hop Lync Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31535-139">L'utilizzo di un pool di server Director è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="31535-139">Using a Director pool is optional.</span></span> <span data-ttu-id="31535-140">È invece possibile utilizzare un pool Front end.</span><span class="sxs-lookup"><span data-stu-id="31535-140">A Front End pool can be used instead.</span></span>

    
    </div>

2.  <span data-ttu-id="31535-141">Il pool di server Director informa il client Lync del pool di registrazione principale e del pool di registrazione di backup dell'utente.</span><span class="sxs-lookup"><span data-stu-id="31535-141">The Director pool informs the Lync client about the user’s primary Registrar pool and backup Registrar pool.</span></span>

3.  <span data-ttu-id="31535-142">Il client Lync tenta innanzitutto di connettersi al pool di registrazione principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="31535-142">The Lync client attempts to connect to the user’s primary Registrar pool first.</span></span> <span data-ttu-id="31535-143">Se è disponibile, la registrazione viene accettata.</span><span class="sxs-lookup"><span data-stu-id="31535-143">If the primary Registrar pool is available, the Registrar accepts the registration.</span></span> <span data-ttu-id="31535-144">Se il pool di registrazione principale non è disponibile, il client Lync tenta di connettersi al pool di registrazione di backup.</span><span class="sxs-lookup"><span data-stu-id="31535-144">If the primary Registrar pool is unavailable, the Lync client attempts to connect to the backup Registrar pool.</span></span> <span data-ttu-id="31535-145">Se questo è disponibile e ha verificato la non disponibilità del pool principale (rilevando la mancanza di un heartbeat per un intervallo di failover specificato), il pool di registrazione di backup accetta la registrazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="31535-145">If the backup Registrar pool is available and has determined that the user’s primary Registrar pool is unavailable (by detecting a lack of heartbeat for a specified failover interval) the backup Registrar pool accepts the user’s registration.</span></span> <span data-ttu-id="31535-146">Dopo che il registrar di backup ha rilevato che il servizio di registrazione primario è di nuovo disponibile, il pool di registrazione di backup reindirizza i client Lync di failover al pool primario.</span><span class="sxs-lookup"><span data-stu-id="31535-146">After the backup Registrar detects that the primary Registrar is again available, the backup Registrar pool will redirect failover Lync clients to their primary pool.</span></span>

<span data-ttu-id="31535-p110">Nella figura seguente viene illustrata la topologia consigliata per garantire la resilienza del sito centrale. I due siti sono connessi tramite un collegamento WAN resiliente. Se il sito centrale diventa non disponibile, gli utenti assegnati a tale pool vengono indirizzati al sito di backup per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="31535-p110">The following figure shows the recommended topology for assuring central site resiliency. The two sites are connected by a resilient WAN link. If the central site becomes unavailable, users who are assigned to that pool are directed to the backup site for registration.</span></span>

<span data-ttu-id="31535-150">**Topologia consigliata per la resilienza dei servizi vocali del sito centrale**</span><span class="sxs-lookup"><span data-stu-id="31535-150">**Recommended topology for central site voice resiliency**</span></span>

<span data-ttu-id="31535-151">![Topologia per la resilienza vocale del sito centrale](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topologia per la resilienza vocale del sito centrale")</span><span class="sxs-lookup"><span data-stu-id="31535-151">![Topology for central site voice resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topology for central site voice resliency")</span></span>

</div>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="31535-152">Requisiti e raccomandazioni</span><span class="sxs-lookup"><span data-stu-id="31535-152">Requirements and Recommendations</span></span>

<span data-ttu-id="31535-153">I requisiti e le raccomandazioni seguenti per l'implementazione della resilienza dei servizi vocali del sito centrale sono appropriati per la maggior parte delle organizzazioni:</span><span class="sxs-lookup"><span data-stu-id="31535-153">The following requirements and recommendations for implementing central site voice resiliency are appropriate for most organizations:</span></span>

  - <span data-ttu-id="31535-154">I siti in cui risiedono i pool di registrazione principale e di backup dovrebbero essere connessi tramite un collegamento WAN resiliente.</span><span class="sxs-lookup"><span data-stu-id="31535-154">The sites in which the primary and backup Registrar pools reside should be connected by a resilient WAN link.</span></span>

  - <span data-ttu-id="31535-155">Ogni sito centrale deve contenere un pool di registrazione composto da una o più funzioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="31535-155">Each central site must contain a Registrar pool consisting of one or more Registrars.</span></span>

  - <span data-ttu-id="31535-156">Per ogni pool di registrazione è necessario utilizzare il bilanciamento del carico DNS, il bilanciamento del carico hardware o entrambi.</span><span class="sxs-lookup"><span data-stu-id="31535-156">Each Registrar pool must be load-balanced by using DNS load balancing, hardware load balancing, or both.</span></span> <span data-ttu-id="31535-157">Per informazioni dettagliate sulla pianificazione della configurazione del bilanciamento del carico, vedere [requisiti per il bilanciamento del carico per Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31535-157">For detailed information about planning your load balancing configuration, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="31535-158">Ogni utente deve essere assegnato a un pool di registrazione principale utilizzando il cmdlet **Set-CsUser** di Lync Server Management Shell o il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="31535-158">Each user must be assigned to a primary Registrar pool by using either the Lync Server Management Shell **set-CsUser** cmdlet or the Lync Server Control Panel.</span></span>

  - <span data-ttu-id="31535-159">Per il pool di registrazione principale deve esistere un singolo pool di registrazione di backup posizionato in un diverso sito centrale.</span><span class="sxs-lookup"><span data-stu-id="31535-159">The primary Registrar pool must have a single backup Registrar pool located in a different central site.</span></span>

  - <span data-ttu-id="31535-160">Il pool di registrazione principale deve essere configurato per il failover sul pool di registrazione di backup.</span><span class="sxs-lookup"><span data-stu-id="31535-160">The primary Registrar pool must be configured to fail over to the backup Registrar pool.</span></span> <span data-ttu-id="31535-161">Per impostazione predefinita, il pool principale è impostato per eseguire il failover sul pool di back dopo un intervallo di 300 secondi.</span><span class="sxs-lookup"><span data-stu-id="31535-161">By default, the primary Registrar is set to fail over to the backup Registrar pool after an interval of 300 seconds.</span></span> <span data-ttu-id="31535-162">È possibile modificare questo intervallo utilizzando il generatore di topologie di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="31535-162">You can change this interval by using the Lync Server 2013 Topology Builder.</span></span>

  - <span data-ttu-id="31535-163">Configurare una route di failover, come descritto nell'argomento "[configurazione di una route di failover in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)" nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="31535-163">Configure a failover route, as described in the “[Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)” topic in the Planning documentation.</span></span> <span data-ttu-id="31535-164">Durante la configurazione della route specificare un gateway posizionato in un sito diverso da quello del gateway impostato nella route principale.</span><span class="sxs-lookup"><span data-stu-id="31535-164">When configuring the route, specify a gateway that is located at a different site from the gateway specified in the primary route.</span></span>

  - <span data-ttu-id="31535-165">Se il sito centrale ospita il server di gestione principale ed è probabile che il sito rimanga inattivo per un lungo periodo, sarà necessario reinstallare gli strumenti di gestione nel sito di backup. In caso contrario, non sarà possibile apportare alcuna modifica alle impostazioni di gestione.</span><span class="sxs-lookup"><span data-stu-id="31535-165">If the central site contained your primary management server and the site is likely to be down for an extended period, you will need to reinstall your management tools at the backup site; otherwise, you won’t be able to change any management settings.</span></span>

</div>

<div>

## <a name="dependencies"></a><span data-ttu-id="31535-166">Dipendenze</span><span class="sxs-lookup"><span data-stu-id="31535-166">Dependencies</span></span>

<span data-ttu-id="31535-167">Lync Server dipende dai seguenti componenti di infrastruttura e software per garantire la resilienza vocale:</span><span class="sxs-lookup"><span data-stu-id="31535-167">Lync Server depends on the following infrastructure and software components to assure voice resiliency:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31535-168"><strong>Componente</strong></span><span class="sxs-lookup"><span data-stu-id="31535-168"><strong>Component</strong></span></span></p></td>
<td><p><span data-ttu-id="31535-169"><strong>Funzionale</strong></span><span class="sxs-lookup"><span data-stu-id="31535-169"><strong>Functional</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31535-170">DNS</span><span class="sxs-lookup"><span data-stu-id="31535-170">DNS</span></span></p></td>
<td><p><span data-ttu-id="31535-171">Risoluzione dei record SRV e A per la connettività tra server e tra server e client</span><span class="sxs-lookup"><span data-stu-id="31535-171">Resolving SRV records and A records for server-server and server-client connectivity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31535-172">Exchange e Servizi Web Exchange</span><span class="sxs-lookup"><span data-stu-id="31535-172">Exchange and Exchange Web Services (EWS)</span></span></p></td>
<td><p><span data-ttu-id="31535-173">Archiviazione dei contatti; dati del calendario</span><span class="sxs-lookup"><span data-stu-id="31535-173">Contact storage; calendar data</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31535-174">Messaggistica unificata di Exchange e Servizi Web Exchange</span><span class="sxs-lookup"><span data-stu-id="31535-174">Exchange Unified Messaging and Exchange Web Services</span></span></p></td>
<td><p><span data-ttu-id="31535-175">Registri chiamate, segreteria telefonica e messaggi di segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="31535-175">Call logs, voice mail list, voice mail</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31535-176">Opzione DHCP 120</span><span class="sxs-lookup"><span data-stu-id="31535-176">DHCP Options 120</span></span></p></td>
<td><p><span data-ttu-id="31535-177">Se non sono disponibili record DNS SRV, il client tenterà di utilizzare l'opzione DHCP 120 per individuare la funzione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="31535-177">If DNS SRV is unavailable, the client will attempt to use DHCP Option 120 to discover the Registrar.</span></span> <span data-ttu-id="31535-178">Affinché ciò funzioni, è necessario configurare un server DHCP oppure è necessario abilitare il protocollo DHCP di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="31535-178">For this to work, either a DHCP server must be configured or Lync Server 2013 DHCP must be enabled.</span></span> <span data-ttu-id="31535-179">Per informazioni dettagliate, vedere Requisiti hardware e software per Branch-Site resilienza nei <a href="lync-server-2013-branch-site-resiliency-requirements.md">requisiti di resilienza dei siti di succursale per Lync Server 2013</a> sezione.</span><span class="sxs-lookup"><span data-stu-id="31535-179">For details, see Hardware and Software Requirements for Branch-Site Resiliency in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</a> section.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a><span data-ttu-id="31535-180">Funzionalità vocali disponibili</span><span class="sxs-lookup"><span data-stu-id="31535-180">Survivable Voice Features</span></span>

<span data-ttu-id="31535-181">Se si implementano i requisiti e le raccomandazioni precedenti, il pool di registrazione di backup renderà disponibili le funzionalità vocali seguenti:</span><span class="sxs-lookup"><span data-stu-id="31535-181">If the preceding requirements and recommendations have been implemented, the following voice features will be provided by the backup Registrar pool:</span></span>

  - <span data-ttu-id="31535-182">Chiamate PSTN in uscita</span><span class="sxs-lookup"><span data-stu-id="31535-182">Outbound PSTN calls</span></span>

  - <span data-ttu-id="31535-183">Chiamate PSTN in entrata, se il provider di servizi di telefonia supporta il failover su un sito di backup.</span><span class="sxs-lookup"><span data-stu-id="31535-183">Inbound PSTN calls, if the telephony service provider supports the ability to fail over to a backup site</span></span>

  - <span data-ttu-id="31535-184">Chiamate Enterprise tra utenti dello stesso sito e di due siti diversi</span><span class="sxs-lookup"><span data-stu-id="31535-184">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="31535-185">Gestione di base delle chiamate inclusi la messa in attesa, il recupero e il trasferimento</span><span class="sxs-lookup"><span data-stu-id="31535-185">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="31535-186">Messaggistica istantanea tra due parti e condivisione di audio e video tra utenti nello stesso sito</span><span class="sxs-lookup"><span data-stu-id="31535-186">Two-party instant messaging and sharing audio and video between users at the same site</span></span>

  - <span data-ttu-id="31535-187">Inoltro di chiamata, squillo simultaneo degli endpoint, delega delle chiamate e servizi di intercettazione team, ma solo se entrambe le parti della delega, oppure tutti i membri del team, sono configurati nello stesso sito</span><span class="sxs-lookup"><span data-stu-id="31535-187">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if both parties to call delegation, or all team members, are configured at the same site.</span></span>

  - <span data-ttu-id="31535-188">I telefoni ei client esistenti continuano a funzionare.</span><span class="sxs-lookup"><span data-stu-id="31535-188">Existing phones and clients continue to work.</span></span>

  - <span data-ttu-id="31535-189">Registrazione dettagli chiamata (CDR)</span><span class="sxs-lookup"><span data-stu-id="31535-189">Call detail recording (CDR)</span></span>

  - <span data-ttu-id="31535-190">Autenticazione e autorizzazione</span><span class="sxs-lookup"><span data-stu-id="31535-190">Authentication and authorization</span></span>

<span data-ttu-id="31535-191">A seconda della modalità di configurazione, le funzionalità vocali seguenti potrebbero o meno funzionare quando un sito centrale principale è fuori servizio:</span><span class="sxs-lookup"><span data-stu-id="31535-191">Depending on how they are configured, the following voice features may or may not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="31535-192">Recapito e recupero di messaggi di segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="31535-192">Voice mail deposit and retrieval</span></span>
    
    <span data-ttu-id="31535-193">Se si desidera rendere disponibile la messaggistica unificata di Exchange quando il sito centrale principale è fuori servizio, è necessario eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="31535-193">If you want to make Exchange UM available when the primary central site is out of service, you must do one of the following:</span></span>
    
      - <span data-ttu-id="31535-194">Modificare i record DNS SRV in modo che i server di messaggistica unificata di Exchange nel sito centrale puntino ai server di messaggistica unificata di Exchange di backup in un altro sito.</span><span class="sxs-lookup"><span data-stu-id="31535-194">Change DNS SRV records so that the Exchange UM servers at the central site point to backup Exchange UM servers at another site.</span></span>
    
      - <span data-ttu-id="31535-195">Configurare il dial plan di messaggistica unificata di Exchange di ogni utente per includere i server di messaggistica unificata di Exchange sia nel sito centrale che nel sito di backup, ma designare i server di messaggistica unificata di Exchange come disabilitati.</span><span class="sxs-lookup"><span data-stu-id="31535-195">Configure each user’s Exchange UM dial plan to include Exchange UM servers at both the central site and the backup site, but designate the backup Exchange UM servers as disabled.</span></span> <span data-ttu-id="31535-196">Se il sito principale diventa non disponibile, l'amministratore di Exchange deve contrassegnare i server di messaggistica unificata di Exchange nel sito di backup come abilitato.</span><span class="sxs-lookup"><span data-stu-id="31535-196">If the primary site becomes unavailable, the Exchange administrator has to mark the Exchange UM servers at the backup site as enabled.</span></span>
    
    <span data-ttu-id="31535-197">Se nessuna delle soluzioni precedenti è possibile, la messaggistica unificata di Exchange non sarà disponibile nel caso in cui il sito centrale diventerà non disponibile.</span><span class="sxs-lookup"><span data-stu-id="31535-197">If neither of the preceding solutions is possible, then Exchange UM will not be available in the event the central site becomes unavailable.</span></span>

  - <span data-ttu-id="31535-198">Conferenze di tutti i tipi</span><span class="sxs-lookup"><span data-stu-id="31535-198">Conferencing of all types</span></span>
    
    <span data-ttu-id="31535-p116">Un utente reindirizzato su un sito di backup per il failover può partecipare a una conferenza creata e ospitata da un organizzatore assegnato a un pool disponibile, ma non può creare o ospitare una conferenza nel suo pool principale, che non è più disponibile. In modo analogo, altri utenti non potranno partecipare alle conferenze ospitate nel pool principale dell'utente interessato dal problema.</span><span class="sxs-lookup"><span data-stu-id="31535-p116">A user who has failed over to a backup site can join a conference that is created or hosted by an organizer whose pool is available but cannot create or host a conference on his or her own primary pool, which is no longer available. Similarly, others users cannot join conferences that are hosted on the affected user’s primary pool.</span></span>

<span data-ttu-id="31535-201">Le funzionalità vocali seguenti non sono disponibili quando un sito centrale principale è fuori servizio:</span><span class="sxs-lookup"><span data-stu-id="31535-201">The following voice features do not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="31535-202">Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="31535-202">Conference Auto-Attendant</span></span>

  - <span data-ttu-id="31535-203">Routing basato su DNS e basato sulla presenza</span><span class="sxs-lookup"><span data-stu-id="31535-203">Presence and DND-based routing</span></span>

  - <span data-ttu-id="31535-204">Aggiornamento delle impostazioni di inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="31535-204">Updating call forwarding settings</span></span>

  - <span data-ttu-id="31535-205">Response Group Service e parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="31535-205">Response Group service and Call Park</span></span>

  - <span data-ttu-id="31535-206">Provisioning di nuovi telefoni e client</span><span class="sxs-lookup"><span data-stu-id="31535-206">Provisioning new phones and clients</span></span>

  - <span data-ttu-id="31535-207">Ricerca Web nella Rubrica</span><span class="sxs-lookup"><span data-stu-id="31535-207">Address Book Web Search</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="31535-208">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31535-208">See Also</span></span>


[<span data-ttu-id="31535-209">Pianificazione della resilienza vocale del sito di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31535-209">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

