---
title: "Lync Server 2013: Scenari per l'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27e4f7410d7038971c6ddefe1af1c7b3ecd97ab9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="d4050-102">Scenari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4050-102">Scenarios for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4050-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d4050-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="d4050-104">Per consentire l'accesso degli utenti esterni per Lync Server 2013, è necessario distribuire almeno un server perimetrale e un proxy inverso nella rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d4050-104">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="d4050-105">Facoltativamente, è possibile distribuire un pool di Director o Director nella rete interna.</span><span class="sxs-lookup"><span data-stu-id="d4050-105">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="d4050-106">Se è necessaria una maggiore capacità rispetto a un singolo Edge Server o se è necessaria una disponibilità elevata per la distribuzione di Edge Server, è possibile configurare il bilanciamento del carico e distribuire più Edge Server in un pool di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="d4050-106">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="d4050-107">Se l'organizzazione ha più centri dati, è possibile avere distribuzioni Edge Server o pool Edge in più di una posizione.</span><span class="sxs-lookup"><span data-stu-id="d4050-107">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="d4050-108">Tuttavia, solo una delle distribuzioni di Edge Server può essere designata come route della Federazione.</span><span class="sxs-lookup"><span data-stu-id="d4050-108">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="d4050-109">Questa sezione definisce gli scenari per le distribuzioni di Edge Server e associa le sezioni di pianificazione ai possibili scenari.</span><span class="sxs-lookup"><span data-stu-id="d4050-109">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="d4050-110">Ad esempio, se la distribuzione richiede disponibilità elevata, Federazione con contatti di messaggistica e presenza estensibili (XMPP) e mobilità Lync, è necessario selezionare le voci corrispondenti nella tabella seguente che soddisfi questi requisiti e usi l' sezioni di pianificazione a cui viene fatto riferimento per definire la distribuzione, come illustrato nel diagramma di flusso seguente.</span><span class="sxs-lookup"><span data-stu-id="d4050-110">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="d4050-111">**Processo di selezione dello scenario di distribuzione di Edge Server**</span><span class="sxs-lookup"><span data-stu-id="d4050-111">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="d4050-112">![](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Diagramma") di flusso distribuzione di esempio</span><span class="sxs-lookup"><span data-stu-id="d4050-112">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="d4050-113">Usando questo processo, puoi pianificare e documentare la configurazione di tutte le funzionalità potenziali che intendi distribuire per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d4050-113">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="d4050-114">È tuttavia possibile aggiungere servizi di Federazione e mobilità dopo avere distribuito il server perimetrale e aver confermato l'operazione corretta prima di aggiungere altre funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d4050-114">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="d4050-115">Il processo di aggiunta di funzionalità a una distribuzione di Edge Server esistente è incluso nella sezione distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d4050-115">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="d4050-116">Per informazioni dettagliate sulla distribuzione, vedere [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) includendo la pianificazione per queste funzionalità durante il processo di pianificazione iniziale, è possibile prepararsi per i requisiti DNS, firewall e certificato per le funzionalità aggiunte, che consentono di acquisire i certificati e configurare preventivamente i requisiti DNS e di protocollo.</span><span class="sxs-lookup"><span data-stu-id="d4050-116">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d4050-117">Se si prevede di installare gli Edge Server e il proxy inverso e quindi di aggiungere funzionalità in un secondo momento, ad esempio la Federazione e la mobilità, determinare quali certificati saranno necessari per tutti i servizi dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d4050-117">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="d4050-118">La pianificazione e l'acquisizione dei certificati per tutte le caratteristiche in anticipo, inizialmente distribuiti o meno, consente di evitare di dover ordinare nuovi certificati per soddisfare i requisiti della Federazione (ovvero, negli Edge Server) o del proxy inverso, ovvero per la mobilità Services).</span><span class="sxs-lookup"><span data-stu-id="d4050-118">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d4050-119">Tutti i servizi Edge vengono eseguiti in ogni Edge Server.</span><span class="sxs-lookup"><span data-stu-id="d4050-119">All edge services run on each Edge Server.</span></span> <span data-ttu-id="d4050-120">I servizi non possono essere divisi tra due diversi Edge Server.</span><span class="sxs-lookup"><span data-stu-id="d4050-120">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="d4050-121">Se si distribuisce un pool di Edge per la scalabilità, tutti i servizi Edge vengono distribuiti in ogni server perimetrale del pool.</span><span class="sxs-lookup"><span data-stu-id="d4050-121">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="d4050-122">La Federazione XMPP, Office Communications Server e la federazione Lync Server, la connettività per messaggistica istantanea pubblica e la mobilità dei client sono servizi aggiuntivi che possono essere distribuiti dopo la distribuzione del primo Edge Server o del pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="d4050-122">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="d4050-123">Servizi mobili è una funzionalità che usa il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d4050-123">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="d4050-124">L'installazione di servizi di mobilità non consente di aggiungere funzionalità agli Edge Server, ma richiede la riconfigurazione del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d4050-124">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="d4050-125">La colonna <STRONG>obiettivo di installazione</STRONG> che elenca queste caratteristiche fornisce indicazioni per la pianificazione nella colonna associata in <STRONG>sezione o sezioni pianificazione di Edge Server</STRONG> per la pianificazione contemporanea di queste funzionalità da distribuire quando i server perimetrali sono installati e configurati.</span><span class="sxs-lookup"><span data-stu-id="d4050-125">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="d4050-126">Identificare e mappare gli obiettivi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="d4050-126">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4050-127">Obiettivo di installazione</span><span class="sxs-lookup"><span data-stu-id="d4050-127">Installation goal</span></span></th>
<th><span data-ttu-id="d4050-128">Documentazione sulla pianificazione di Edge Server</span><span class="sxs-lookup"><span data-stu-id="d4050-128">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4050-129">È stato deciso che un singolo server è sufficiente per i servizi Edge nell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="d4050-129">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="d4050-130">Si intende anche usare indirizzi IP privati per le interfacce esterne di Edge Server con NAT su Internet.</span><span class="sxs-lookup"><span data-stu-id="d4050-130">You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="d4050-131">Usare questa sezione per la pianificazione se si distribuisce un singolo Edge Server nel perimetro.</span><span class="sxs-lookup"><span data-stu-id="d4050-131">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="d4050-132">Si distribuirà un server perimetrale con indirizzi IP privati assegnati all'Edge Server e si utilizzerà NAT per specificare gli indirizzi IP pubblici per gli utenti esterni su Internet.</span><span class="sxs-lookup"><span data-stu-id="d4050-132">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="d4050-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Singola topologia perimetrale consolidata con indirizzi IP privati e NAT in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d4050-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4050-134">È stato deciso che un singolo server è sufficiente per i servizi Edge nell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="d4050-134">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="d4050-135">Si intende anche usare indirizzi IP pubblici per le interfacce esterne di Edge Server a Internet.</span><span class="sxs-lookup"><span data-stu-id="d4050-135">You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="d4050-136">Usare questa sezione per la pianificazione se si distribuisce un singolo Edge Server nel perimetro.</span><span class="sxs-lookup"><span data-stu-id="d4050-136">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="d4050-137">Verrà distribuito un server perimetrale con indirizzi IP pubblici assegnati all'Edge Server.</span><span class="sxs-lookup"><span data-stu-id="d4050-137">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="d4050-138">Al posto di NAT si userà il routing in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="d4050-138">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="d4050-139">L'indirizzo IP pubblico effettivo del server perimetrale viene reso disponibile per le connessioni degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="d4050-139">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="d4050-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d4050-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4050-141">È stato deciso che l'elevata disponibilità dei servizi Edge è importante per gli utenti e si distribuiscono due o più server perimetrali in questo pool.</span><span class="sxs-lookup"><span data-stu-id="d4050-141">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="d4050-142">Si intende anche usare indirizzi IP privati per le interfacce esterne di Edge Server con NAT su Internet.</span><span class="sxs-lookup"><span data-stu-id="d4050-142">You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="d4050-143">Usare questa sezione per la pianificazione se si distribuisce un pool di Edge Server nel perimetro.</span><span class="sxs-lookup"><span data-stu-id="d4050-143">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="d4050-144">Gli Edge Server verranno distribuiti con indirizzi IP privati assegnati all'Edge Server, usando il bilanciamento del carico DNS per distribuire le comunicazioni nel pool.</span><span class="sxs-lookup"><span data-stu-id="d4050-144">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="d4050-145">Si utilizzerà NAT per specificare gli indirizzi IP pubblici per gli utenti esterni su Internet.</span><span class="sxs-lookup"><span data-stu-id="d4050-145">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="d4050-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d4050-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4050-147">È stato deciso che l'elevata disponibilità dei servizi Edge è importante per gli utenti e si distribuiscono due o più server perimetrali in questo pool.</span><span class="sxs-lookup"><span data-stu-id="d4050-147">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="d4050-148">Si intende anche usare indirizzi IP pubblici per le interfacce esterne di Edge Server a Internet.</span><span class="sxs-lookup"><span data-stu-id="d4050-148">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="d4050-149">Usare questa sezione per la pianificazione se si distribuisce un pool di Edge Server nel perimetro.</span><span class="sxs-lookup"><span data-stu-id="d4050-149">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="d4050-150">Gli Edge Server verranno distribuiti con indirizzi IP pubblici assegnati all'Edge Server, usando il bilanciamento del carico DNS per distribuire le comunicazioni nel pool.</span><span class="sxs-lookup"><span data-stu-id="d4050-150">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="d4050-151">Invece di NAT, userai routing per specificare gli indirizzi IP pubblici per gli utenti esterni su Internet.</span><span class="sxs-lookup"><span data-stu-id="d4050-151">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="d4050-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d4050-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4050-153">È stato deciso che l'elevata disponibilità dei servizi Edge è importante per gli utenti e si distribuiscono due o più server perimetrali in questo pool usando un dispositivo di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="d4050-153">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="d4050-154">Usare questa sezione per la pianificazione se si distribuisce un pool di Edge Server nel perimetro.</span><span class="sxs-lookup"><span data-stu-id="d4050-154">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="d4050-155">Gli Edge Server verranno distribuiti con indirizzi IP pubblici assegnati all'Edge Server, usando i dispositivi di bilanciamento del carico hardware per distribuire le comunicazioni nel pool.</span><span class="sxs-lookup"><span data-stu-id="d4050-155">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="d4050-156">Invece di NAT, userai routing per specificare gli indirizzi IP pubblici per gli utenti esterni su Internet.</span><span class="sxs-lookup"><span data-stu-id="d4050-156">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="d4050-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Topologia perimetrale consolidata con scalabilità implementata e servizi di bilanciamento del carico hardware in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d4050-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4050-158">Gli scenari federativi consentono di pianificare la funzionalità che estenderà i tipi di partner con cui gli utenti possono comunicare.</span><span class="sxs-lookup"><span data-stu-id="d4050-158">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="d4050-159">Federazione Lync Server</span><span class="sxs-lookup"><span data-stu-id="d4050-159">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="d4050-160">Office Communications Server Federation</span><span class="sxs-lookup"><span data-stu-id="d4050-160">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="d4050-161">Connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="d4050-161">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="d4050-162">Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="d4050-162">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d4050-163">Pianificazione per gli scenari federativi</span><span class="sxs-lookup"><span data-stu-id="d4050-163">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="d4050-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Pianificazione per Lync Server 2013 e Office Communications Server Federation</a></span><span class="sxs-lookup"><span data-stu-id="d4050-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="d4050-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Pianificazione della connettività di messaggistica istantanea pubblica in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d4050-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="d4050-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Pianificazione della Federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d4050-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4050-167">I servizi di mobilità vengono offerti tramite il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d4050-167">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="d4050-168">I servizi che consentono la mobilità per gli utenti esterni vengono distribuiti nel server front-end o nel pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="d4050-168">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="d4050-169">Per abilitare i servizi di mobilità per gli utenti esterni, è possibile creare o modificare le regole di pubblicazione esistenti nel proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d4050-169">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="d4050-170"><a href="lync-server-2013-planning-for-mobility.md">Pianificazione della versione per dispositivi mobili in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d4050-170"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="d4050-171">Nelle sezioni seguenti scenari sono disponibili architetture di riferimento, ad esempio DNS, definizioni di porta/protocollo e requisiti di certificato.</span><span class="sxs-lookup"><span data-stu-id="d4050-171">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="d4050-172">Sono inclusi anche i diagrammi per le definizioni DNS, di porta/protocollo e per le esigenze dei certificati.</span><span class="sxs-lookup"><span data-stu-id="d4050-172">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="d4050-173">I diagrammi forniranno un modello per compilare e distribuire ad altri team, ad esempio il team di rete dell'organizzazione, il team di infrastruttura a chiave pubblica e il team di distribuzione del server.</span><span class="sxs-lookup"><span data-stu-id="d4050-173">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="d4050-174">L'obiettivo dei diagrammi è migliorare la comunicazione e garantire il successo quando si comunicano gli elementi di configurazione del server perimetrale necessari alle persone che faranno il lavoro di configurazione effettivo.</span><span class="sxs-lookup"><span data-stu-id="d4050-174">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="d4050-175">È consigliabile usare i diagrammi e le architetture di riferimento associate per pianificare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d4050-175">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

