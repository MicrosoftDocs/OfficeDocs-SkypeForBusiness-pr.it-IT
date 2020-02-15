---
title: 'Lync Server 2013: opzioni di distribuzione del gateway PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e4d8f35ecf2b384ad51482547b22baad63fcf31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="5a88a-102">Opzioni di distribuzione di gateway PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a88a-102">PSTN gateway deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a88a-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5a88a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="5a88a-104">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="5a88a-104">PSTN Gateways</span></span>

<span data-ttu-id="5a88a-105">I gateway PSTN (Public Switched Telephone Network) sono componenti hardware di terze parti che convertono i segnali e i dati multimediali tra l'infrastruttura VoIP aziendale e la rete PSTN direttamente o mediante connessione a trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="5a88a-105">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="5a88a-106">In entrambe le topologie il gateway termina la rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="5a88a-106">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="5a88a-107">Il gateway è isolato nella propria subnet ed è connesso alla rete aziendale tramite il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="5a88a-107">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="5a88a-108">Un'organizzazione con più siti in genere distribuisce uno o più gateway in ogni sito.</span><span class="sxs-lookup"><span data-stu-id="5a88a-108">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="5a88a-109">I siti di succursale possono connettersi alla rete PSTN tramite un gateway o tramite un Survivable Branch Appliance, che combina gateway e server in una singola casella.</span><span class="sxs-lookup"><span data-stu-id="5a88a-109">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="5a88a-110">Se i siti di succursale utilizzano un gateway, è necessario che il servizio di registrazione e Mediation Server siano necessari nel sito, a meno che il collegamento WAN non sia resiliente.</span><span class="sxs-lookup"><span data-stu-id="5a88a-110">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="5a88a-111">Uno o più Mediation Server, che sono collocati nei Front End Server, possono instradare le chiamate per uno o più gateway in ogni sito.</span><span class="sxs-lookup"><span data-stu-id="5a88a-111">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="5a88a-112">È consigliabile che il servizio di registrazione, il Mediation Server e il gateway richiesti nel sito siano distribuiti come Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="5a88a-112">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="5a88a-113">Determinare il numero, le dimensioni e la posizione dei gateway PSTN è forse la decisione più importante e costosa che è necessario apportare quando si pianifica l'infrastruttura VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="5a88a-113">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="5a88a-114">Di seguito sono riportate le principali domande da prendere in considerazione.</span><span class="sxs-lookup"><span data-stu-id="5a88a-114">Here are the main questions to consider.</span></span> <span data-ttu-id="5a88a-115">Tenere presente che le risposte a queste domande sono tutte interdipendenti</span><span class="sxs-lookup"><span data-stu-id="5a88a-115">Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="5a88a-116">Quanti gateway PSTN sono necessari?</span><span class="sxs-lookup"><span data-stu-id="5a88a-116">How many PSTN gateways are needed?</span></span> <span data-ttu-id="5a88a-117">La risposta dipende dal numero di utenti, dal numero previsto di chiamate simultanee (carico del traffico) e dal numero di siti (ogni sito ne ha bisogno).</span><span class="sxs-lookup"><span data-stu-id="5a88a-117">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="5a88a-118">Quali dimensioni devono essere i gateway?</span><span class="sxs-lookup"><span data-stu-id="5a88a-118">What size should the gateways be?</span></span> <span data-ttu-id="5a88a-119">La risposta dipende dal numero di utenti nel sito e dal carico di traffico.</span><span class="sxs-lookup"><span data-stu-id="5a88a-119">The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="5a88a-120">Dove devono essere ubicati i gateway?</span><span class="sxs-lookup"><span data-stu-id="5a88a-120">Where should the gateways be located?</span></span> <span data-ttu-id="5a88a-121">La risposta dipende in parte dalla topologia e in parte dalla distribuzione geografica dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5a88a-121">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="5a88a-122">È inoltre consigliabile prendere in considerazione le opzioni di topologia del gateway (per informazioni dettagliate, vedere Topologie del gateway più avanti in questo argomento).</span><span class="sxs-lookup"><span data-stu-id="5a88a-122">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="5a88a-123">Supporto dei trunk M:N</span><span class="sxs-lookup"><span data-stu-id="5a88a-123">M:N Trunk Support</span></span>

<span data-ttu-id="5a88a-124">I Mediation Server possono instradare le chiamate tramite più gateway, Session Border Controller (SBCs) forniti da provider di servizi di telefonia Internet o una combinazione di due.</span><span class="sxs-lookup"><span data-stu-id="5a88a-124">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="5a88a-125">Inoltre, più Mediation Server nel pool è in grado di interagire con più gateway.</span><span class="sxs-lookup"><span data-stu-id="5a88a-125">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="5a88a-126">La route logica definita tra un Mediation Server e un gateway è denominata *trunk*.</span><span class="sxs-lookup"><span data-stu-id="5a88a-126">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="5a88a-127">Quando un utente interno inserisce una chiamata PSTN, la logica di routing in uscita nel pool Front End sceglie il trunk da instradare oltre tutte le combinazioni possibili che potrebbero essere disponibili per il routing di quella chiamata specifica.</span><span class="sxs-lookup"><span data-stu-id="5a88a-127">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="5a88a-128">Con il bilanciamento del carico DNS, se una chiamata non riesce a raggiungere un gateway a causa di un problema con un determinato Mediation Server nel pool, la chiamata verrà ritentata in un Mediation server alternativo nel pool.</span><span class="sxs-lookup"><span data-stu-id="5a88a-128">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="5a88a-129">Per informazioni dettagliate sulla pianificazione di più gateway, vedere [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span><span class="sxs-lookup"><span data-stu-id="5a88a-129">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="5a88a-130">Per informazioni dettagliate sull'altro miglioramento del routing in uscita, vedere [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="5a88a-130">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="5a88a-131">Topologie di gateway</span><span class="sxs-lookup"><span data-stu-id="5a88a-131">Gateway Topologies</span></span>

<span data-ttu-id="5a88a-132">Se si considerano le questioni fondamentali della distribuzione di gateway, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="5a88a-132">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="5a88a-133">Contare i siti in cui si desidera fornire la connettività PSTN tramite VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="5a88a-133">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="5a88a-134">Stimare il traffico in ogni sito (numero di utenti e numero medio di chiamate all'ora per utente).</span><span class="sxs-lookup"><span data-stu-id="5a88a-134">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="5a88a-135">Distribuire uno o più gateway in ogni sito per gestire il traffico previsto.</span><span class="sxs-lookup"><span data-stu-id="5a88a-135">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="5a88a-136">La topologia del gateway distribuito risultante è illustrata nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="5a88a-136">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="5a88a-137">**Topologia del gateway distribuito**</span><span class="sxs-lookup"><span data-stu-id="5a88a-137">**Distributed gateway topology**</span></span>

<span data-ttu-id="5a88a-138">![Diagramma della topologia di gateway distribuiti](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Diagramma della topologia di gateway distribuiti")</span><span class="sxs-lookup"><span data-stu-id="5a88a-138">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="5a88a-139">Con questa topologia, le chiamate tra i lavoratori di ogni sito e tra i siti vengono instradate all'interno della rete Intranet.</span><span class="sxs-lookup"><span data-stu-id="5a88a-139">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="5a88a-140">Le chiamate alla rete PSTN vengono instradate tramite la Network IP dell'organizzazione ai gateway più vicini alla posizione dei numeri di destinazione. Ma cosa succede se l'organizzazione supporta decine o centinaia o addirittura migliaia di siti distribuiti in uno o più continenti, come fanno molte istituzioni finanziarie e altre imprese di grandi dimensioni?</span><span class="sxs-lookup"><span data-stu-id="5a88a-140">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="5a88a-141">In questi casi, la distribuzione di un gateway separato in ogni sito non è pratico.</span><span class="sxs-lookup"><span data-stu-id="5a88a-141">In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="5a88a-142">Per risolvere questo problema, molte società di grandi dimensioni preferiscono distribuire uno o più siti centrali di telefonia di grandi dimensioni, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="5a88a-142">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="5a88a-143">**Topologia del sito centrale di telefonia**</span><span class="sxs-lookup"><span data-stu-id="5a88a-143">**Telephony central site topology**</span></span>

<span data-ttu-id="5a88a-144">![Topologia del gateway Data Center](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Topologia del gateway Data Center")</span><span class="sxs-lookup"><span data-stu-id="5a88a-144">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="5a88a-145">In questa topologia, numerosi gateway di grandi dimensioni sufficienti per ospitare il carico utente previsto vengono distribuiti in ogni sito centrale.</span><span class="sxs-lookup"><span data-stu-id="5a88a-145">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="5a88a-146">Tutte le chiamate agli utenti nell'organizzazione vengono inoltrate dal provider di servizi telefonici della società a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="5a88a-146">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="5a88a-147">La logica di routing nel sito centrale determina se la chiamata deve essere instradata attraverso la rete Intranet o la rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="5a88a-147">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="5a88a-148">Posizione del gateway</span><span class="sxs-lookup"><span data-stu-id="5a88a-148">Gateway Location</span></span>

<span data-ttu-id="5a88a-149">Il percorso del gateway può anche determinare i tipi di gateway scelti e il modo in cui vengono configurati.</span><span class="sxs-lookup"><span data-stu-id="5a88a-149">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="5a88a-150">Sono disponibili dozzine di protocolli PSTN, nessuno dei quali è uno standard mondiale.</span><span class="sxs-lookup"><span data-stu-id="5a88a-150">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="5a88a-151">Se tutti i gateway sono situati in un singolo paese/area geografica, non si tratta di un problema, ma se si individuano i gateway in diversi paesi/aree geografiche, è necessario configurarli in base agli standard PSTN di quel paese/area geografica.</span><span class="sxs-lookup"><span data-stu-id="5a88a-151">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="5a88a-152">Inoltre, i gateway certificati per l'operazione, ad esempio il Canada, potrebbero non essere certificati in India, Brasile o nell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="5a88a-152">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="5a88a-153">Dimensione e numero del gateway</span><span class="sxs-lookup"><span data-stu-id="5a88a-153">Gateway Size and Number</span></span>

<span data-ttu-id="5a88a-154">I gateway PSTN che la maggior parte delle organizzazioni valuterà la distribuzione di un intervallo di dimensioni da 2 a fino a 960 porte.</span><span class="sxs-lookup"><span data-stu-id="5a88a-154">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="5a88a-155">(Esistono anche gateway più grandi, ma questi sono utilizzati principalmente dai provider di servizi di telefonia). Quando si valuta il numero di porte richieste dall'organizzazione, utilizzare le linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a88a-155">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="5a88a-156">Le organizzazioni con utilizzo di telefonia chiaro (una chiamata PSTN per utente all'ora) devono allocare una porta per ogni 15 utenti.</span><span class="sxs-lookup"><span data-stu-id="5a88a-156">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="5a88a-157">Ad esempio, se si dispone di 20 utenti, sarà necessario un gateway con due porte.</span><span class="sxs-lookup"><span data-stu-id="5a88a-157">For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="5a88a-158">Le organizzazioni con un utilizzo di telefonia moderato (due chiamate PSTN per utente all'ora) devono allocare una porta per ogni 10 utenti.</span><span class="sxs-lookup"><span data-stu-id="5a88a-158">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="5a88a-159">Ad esempio, se si dispone di 100 utenti, sarà necessario un totale di 10 porte allocate tra uno o più gateway.</span><span class="sxs-lookup"><span data-stu-id="5a88a-159">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="5a88a-160">Le organizzazioni con un utilizzo pesante della telefonia (tre o più chiamate PSTN per utente all'ora) devono allocare una porta per ogni cinque utenti.</span><span class="sxs-lookup"><span data-stu-id="5a88a-160">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="5a88a-161">Ad esempio, se si dispone di 47.000 utenti, sarà necessario un totale di 9.400 porte allocate tra almeno 10 gateway di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="5a88a-161">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="5a88a-162">È possibile acquisire ulteriori porte quando aumenta il numero di utenti o la quantità di traffico nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5a88a-162">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="5a88a-163">Per un determinato numero di utenti che è necessario supportare, è possibile scegliere di distribuire meno, gateway più grandi o più piccoli.</span><span class="sxs-lookup"><span data-stu-id="5a88a-163">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="5a88a-164">Come regola generale, è consigliabile un minimo di due gateway per un'organizzazione per mantenere la disponibilità se un gateway ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5a88a-164">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="5a88a-165">Ogni gateway PSTN distribuito deve disporre di almeno un Mediation Server corrispondente.</span><span class="sxs-lookup"><span data-stu-id="5a88a-165">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

