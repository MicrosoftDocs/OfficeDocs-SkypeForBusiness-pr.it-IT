---
title: "Lync Server 2013: scenari per l'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e9a2f60b2273cf8d43833226ede66a2a90478a6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="1741b-102">Scenari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1741b-102">Scenarios for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1741b-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1741b-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1741b-104">Se si fornisce l'accesso degli utenti esterni per Lync Server 2013, è necessario distribuire almeno un server perimetrale e un proxy inverso nella rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="1741b-104">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="1741b-105">Facoltativamente, è possibile distribuire un server Director o un pool di server Director nella rete interna.</span><span class="sxs-lookup"><span data-stu-id="1741b-105">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="1741b-106">Se è necessaria una maggiore capacità rispetto a un singolo server perimetrale in grado di fornire o se è necessaria una disponibilità elevata per la distribuzione del server perimetrale, è possibile configurare il bilanciamento del carico e distribuire più server perimetrali in un pool con bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="1741b-106">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="1741b-107">Se nell'organizzazione sono presenti più data center, è possibile disporre di distribuzioni di server perimetrali o pool di Edge in più di una posizione.</span><span class="sxs-lookup"><span data-stu-id="1741b-107">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="1741b-108">Tuttavia, è possibile designare solo una delle distribuzioni di server perimetrali come route di Federazione.</span><span class="sxs-lookup"><span data-stu-id="1741b-108">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="1741b-109">In questa sezione vengono definiti gli scenari per le distribuzioni di server perimetrali e le sezioni di pianificazione vengono mappate ai possibili scenari.</span><span class="sxs-lookup"><span data-stu-id="1741b-109">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="1741b-110">Ad esempio, se la distribuzione richiede disponibilità elevata, Federazione con contatti di messaggistica e presenza estensibili e mobilità Lync, è necessario selezionare le voci corrispondenti nella tabella seguente in grado di soddisfare questi requisiti e utilizzare la sezioni di pianificazione a cui viene fatto riferimento per definire la distribuzione, come illustrato nel diagramma di flusso seguente.</span><span class="sxs-lookup"><span data-stu-id="1741b-110">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="1741b-111">**Processo di selezione degli scenari di distribuzione di server perimetrali**</span><span class="sxs-lookup"><span data-stu-id="1741b-111">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="1741b-112">![Diagramma di flusso di distribuzione di esempio](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Diagramma di flusso di distribuzione di esempio")</span><span class="sxs-lookup"><span data-stu-id="1741b-112">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="1741b-113">Utilizzando questo processo, è possibile pianificare e documentare la configurazione di tutte le funzionalità possibili che si intende distribuire per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1741b-113">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="1741b-114">Tuttavia, è possibile aggiungere servizi di Federazione e mobilità dopo aver distribuito il server perimetrale e aver confermato l'operazione corretta prima di aggiungere altre caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="1741b-114">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="1741b-115">Il processo di aggiunta di funzionalità a una distribuzione di server perimetrali esistente è incluso nella sezione distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1741b-115">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="1741b-116">Per informazioni dettagliate sulla distribuzione, vedere [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) includendo la pianificazione per queste funzionalità durante il processo di pianificazione iniziale, è possibile prepararsi per i requisiti DNS, del firewall e dei certificati per le caratteristiche aggiunte, che consentono di acquisire i certificati e configurare i requisiti DNS e porta/protocollo in anticipo.</span><span class="sxs-lookup"><span data-stu-id="1741b-116">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="1741b-117">Se si prevede di installare i server perimetrali e il proxy inverso e quindi aggiungere le funzionalità in un secondo momento (ad esempio, Federazione e mobilità), determinare quali certificati saranno necessari per tutti i servizi dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1741b-117">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="1741b-118">La pianificazione e l'acquisizione dei certificati per tutte le funzionalità in anticipo, inizialmente distribuite o meno, consente di evitare di dover ordinare nuovi certificati per soddisfare i requisiti di federazione, ovvero nei server perimetrali, o il proxy inverso, ovvero per la mobilità Services).</span><span class="sxs-lookup"><span data-stu-id="1741b-118">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1741b-119">Tutti i servizi perimetrali vengono eseguiti su ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="1741b-119">All edge services run on each Edge Server.</span></span> <span data-ttu-id="1741b-120">Non è possibile suddividere i servizi tra due server perimetrali diversi.</span><span class="sxs-lookup"><span data-stu-id="1741b-120">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="1741b-121">Se si distribuisce un pool di server perimetrali per la scalabilità, tutti i servizi perimetrali vengono distribuiti su tutti i server perimetrali del pool.</span><span class="sxs-lookup"><span data-stu-id="1741b-121">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="1741b-122">La Federazione XMPP, Office Communications Server e la Federazione di Lync Server, la connettività per la messaggistica istantanea pubblica e la mobilità client sono servizi aggiuntivi che possono essere distribuiti dopo la distribuzione del primo server perimetrale o del pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="1741b-122">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="1741b-123">I servizi Mobility sono una funzionalità che utilizza il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="1741b-123">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="1741b-124">L'installazione dei servizi per dispositivi mobili non consente di aggiungere funzionalità ai server perimetrali, ma richiede la riconfigurazione del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="1741b-124">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="1741b-125">La colonna <STRONG>obiettivo di installazione</STRONG> che elenca queste caratteristiche fornisce indicazioni sulla pianificazione nella colonna associata nella <STRONG>sezione pianificazione server perimetrale o sezioni</STRONG> per la pianificazione simultanea di queste funzionalità da distribuire quando i server perimetrali sono installati e configurati.</span><span class="sxs-lookup"><span data-stu-id="1741b-125">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="1741b-126">Identificazione e associazione degli obiettivi di pianificazione</span><span class="sxs-lookup"><span data-stu-id="1741b-126">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1741b-127">Obiettivo dell'installazione</span><span class="sxs-lookup"><span data-stu-id="1741b-127">Installation goal</span></span></th>
<th><span data-ttu-id="1741b-128">Documentazione relativa alla pianificazione del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="1741b-128">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1741b-p107">Si è deciso che un solo server sia sufficiente per i servizi perimetrali nell'infrastruttura. Si intende inoltre utilizzare indirizzi IP privati per le interfacce esterne dei server perimetrali con NAT su Internet.</span><span class="sxs-lookup"><span data-stu-id="1741b-p107">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="1741b-131">Utilizzare questa sezione per la pianificazione se si sta distribuendo un singolo server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="1741b-131">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="1741b-132">Verrà distribuito un server perimetrale con indirizzi IP privati assegnati al server perimetrale e verrà utilizzato NAT per fornire gli indirizzi IP pubblici per gli utenti esterni su Internet.</span><span class="sxs-lookup"><span data-stu-id="1741b-132">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="1741b-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Singolo server perimetrale consolidato con indirizzi IP privati e NAT in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1741b-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1741b-p109">Si è deciso che un solo server sia sufficiente per i servizi perimetrali nell'infrastruttura. Si intende inoltre utilizzare indirizzi IP pubblici per le interfacce esterne dei server perimetrali su Internet.</span><span class="sxs-lookup"><span data-stu-id="1741b-p109">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="1741b-136">Utilizzare questa sezione per la pianificazione se si sta distribuendo un singolo server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="1741b-136">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="1741b-137">Verrà distribuito un server perimetrale con indirizzi IP pubblici assegnati al server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="1741b-137">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="1741b-138">Anziché NAT, in questo scenario si utilizzerà il routing.</span><span class="sxs-lookup"><span data-stu-id="1741b-138">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="1741b-139">L'indirizzo IP pubblico effettivo del server perimetrale viene reso disponibile per le connessioni utente esterne.</span><span class="sxs-lookup"><span data-stu-id="1741b-139">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="1741b-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Perimetro consolidato singolo con indirizzi IP pubblici in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1741b-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1741b-p111">Si è deciso che l'elevata disponibilità dei servizi perimetrali è importante per gli utenti e si distribuiranno due o più server perimetrali nel pool. Si intende inoltre utilizzare indirizzi IP privati per le interfacce esterne dei server perimetrali con NAT su Internet.</span><span class="sxs-lookup"><span data-stu-id="1741b-p111">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool. You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="1741b-143">Utilizzare questa sezione per la pianificazione se si sta distribuendo un pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="1741b-143">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="1741b-144">Verranno distribuiti i server perimetrali con indirizzi IP privati assegnati al server perimetrale, utilizzando il bilanciamento del carico DNS per distribuire la comunicazione nel pool.</span><span class="sxs-lookup"><span data-stu-id="1741b-144">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="1741b-145">Si utilizzerà NAT per fornire indirizzi IP pubblici per gli utenti esterni in Internet.</span><span class="sxs-lookup"><span data-stu-id="1741b-145">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="1741b-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1741b-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1741b-147">Si è deciso che l'elevata disponibilità dei servizi perimetrali è importante per gli utenti e si distribuiranno due o più server perimetrali nel pool.</span><span class="sxs-lookup"><span data-stu-id="1741b-147">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="1741b-148">Si intende anche utilizzare indirizzi IP pubblici per le interfacce esterne del server perimetrale su Internet.</span><span class="sxs-lookup"><span data-stu-id="1741b-148">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="1741b-149">Utilizzare questa sezione per la pianificazione se si sta distribuendo un pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="1741b-149">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="1741b-150">Verranno distribuiti i server perimetrali con indirizzi IP pubblici assegnati al server perimetrale, utilizzando il bilanciamento del carico DNS per distribuire le comunicazioni tra il pool.</span><span class="sxs-lookup"><span data-stu-id="1741b-150">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="1741b-151">Anziché NAT, si utilizzerà il routing per fornire indirizzi IP pubblici per gli utenti esterni in Internet.</span><span class="sxs-lookup"><span data-stu-id="1741b-151">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="1741b-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1741b-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1741b-153">È stato deciso che la disponibilità elevata dei servizi perimetrali è importante per gli utenti e che verranno distribuiti due o più server perimetrali in questo pool utilizzando un dispositivo di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="1741b-153">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="1741b-154">Utilizzare questa sezione per la pianificazione se si sta distribuendo un pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="1741b-154">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="1741b-155">Verranno distribuiti i server perimetrali con indirizzi IP pubblici assegnati al server perimetrale, utilizzando dispositivi di bilanciamento del carico hardware per distribuire le comunicazioni tra il pool.</span><span class="sxs-lookup"><span data-stu-id="1741b-155">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="1741b-156">Anziché NAT, si utilizzerà il routing per fornire indirizzi IP pubblici per gli utenti esterni in Internet.</span><span class="sxs-lookup"><span data-stu-id="1741b-156">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="1741b-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Perimetro consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1741b-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1741b-158">Gli scenari di federazione consentono di pianificare la funzionalità per estendere i tipi di partner con cui possono comunicare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1741b-158">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="1741b-159">Federazione di Lync Server</span><span class="sxs-lookup"><span data-stu-id="1741b-159">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="1741b-160">Federazione di Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="1741b-160">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="1741b-161">Connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="1741b-161">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="1741b-162">Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="1741b-162">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1741b-163">Pianificazione per gli scenari di federazione</span><span class="sxs-lookup"><span data-stu-id="1741b-163">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="1741b-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 e Office Communications Server Federation</a></span><span class="sxs-lookup"><span data-stu-id="1741b-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="1741b-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Pianificazione della connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1741b-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="1741b-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Pianificazione della Federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1741b-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1741b-167">I servizi Mobility vengono offerti tramite il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="1741b-167">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="1741b-168">I servizi che consentono la mobilità per gli utenti esterni sono distribuiti nel front end server o nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="1741b-168">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="1741b-169">Per abilitare i servizi Mobility per gli utenti esterni, creare regole di pubblicazione o modificare quelle esistenti nel proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="1741b-169">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="1741b-170"><a href="lync-server-2013-planning-for-mobility.md">Pianificazione della funzionalità per dispositivi mobili in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1741b-170"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="1741b-171">Nelle sezioni Scenari di seguito sono illustrate architetture di riferimento, esempi di DNS, definizioni di porte/protocolli e requisiti di certificati.</span><span class="sxs-lookup"><span data-stu-id="1741b-171">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="1741b-172">Sono inoltre inclusi diagrammi per esigenze relative a DNS, definizioni di porte/protocolli e certificati.</span><span class="sxs-lookup"><span data-stu-id="1741b-172">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="1741b-173">I diagrammi offrono un modello da compilare e distribuire ad altri team (ad esempio il team di rete, il team di infrastruttura di chiave pubblica e il team di distribuzione server dell'organizzazione).</span><span class="sxs-lookup"><span data-stu-id="1741b-173">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="1741b-174">L'obiettivo dei diagrammi consiste nel migliorare la comunicazione e nel garantire il corretto funzionamento quando si comunicano gli elementi di configurazione del server perimetrale necessari agli utenti che eseguono la configurazione effettiva.</span><span class="sxs-lookup"><span data-stu-id="1741b-174">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="1741b-175">Si consiglia di utilizzare i diagrammi e le architetture di riferimento associate per pianificare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1741b-175">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

