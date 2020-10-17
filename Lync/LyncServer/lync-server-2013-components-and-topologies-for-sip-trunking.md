---
title: 'Lync Server 2013: componenti e topologie per il trunking SIP'
description: 'Lync Server 2013: componenti e topologie per il trunking SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9d9c826539084a539d3efe7f143c335ec6d8f62
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549522"
---
# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="d3fc8-103">Componenti e topologie per il trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3fc8-103">Components and topologies for SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3fc8-104">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d3fc8-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d3fc8-105">Nella figura seguente viene illustrata la topologia di trunking SIP in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3fc8-105">The following figure depicts the SIP trunking topology in Lync Server.</span></span>

<span data-ttu-id="d3fc8-106">**Topologia di trunking SIP**</span><span class="sxs-lookup"><span data-stu-id="d3fc8-106">**SIP trunking topology**</span></span>

<span data-ttu-id="d3fc8-107">![Topologia del trunking SIP](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "Topologia del trunking SIP")</span><span class="sxs-lookup"><span data-stu-id="d3fc8-107">![SIP Trunking Topology](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP Trunking Topology")</span></span>

<span data-ttu-id="d3fc8-p101">Come illustrato nella figura, una rete privata virtuale (VPN, Virtual Private Network) IP viene utilizzata per la connettività tra l'azienda e il provider di servizi PSTN. Lo scopo di questa rete privata è quello di fornire connettività IP, migliorare la protezione e, facoltativamente, ottenere garanzie relative alla qualità del servizio. Data la natura delle VPN, non è necessario utilizzare TLS per il traffico di segnalazione SIP o SRTP per il traffico multimediale. Le connessioni tra l'azienda e il provider di servizi sono pertanto normali connessioni TCP per SIP e RTP (tramite UDP) per i contenuti multimediali potenzialmente inviati tramite una rete VPN IP. Accertarsi che le porte di tutti i firewall tra i router VPN siano aperte per consentire ai router VPN di comunicare e che gli indirizzi IP nei perimetri esterni dei router VPN consentano l'esecuzione del routing pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="d3fc8-p101">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider. The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees. Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic. Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN. Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d3fc8-113">Contattare il provider di servizi per determinare se fornisce supporto per la disponibilità elevata, incluso il failover.</span><span class="sxs-lookup"><span data-stu-id="d3fc8-113">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="d3fc8-114">In tal caso, sarà necessario determinare le procedure per configurarlo.</span><span class="sxs-lookup"><span data-stu-id="d3fc8-114">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="d3fc8-115">Ad esempio, è necessario configurare un solo indirizzo IP e un trunk SIP su ogni Mediation Server oppure è necessario configurare più trunk SIP su ogni Mediation Server?</span><span class="sxs-lookup"><span data-stu-id="d3fc8-115">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span><BR><span data-ttu-id="d3fc8-116">Se si dispone di più siti centrali, chiedere anche se il provider di servizi ha la possibilità di abilitare le connessioni da e verso un altro sito centrale.</span><span class="sxs-lookup"><span data-stu-id="d3fc8-116">If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d3fc8-117">Per il trunking SIP, è consigliabile distribuire i Mediation Server autonomi.</span><span class="sxs-lookup"><span data-stu-id="d3fc8-117">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="d3fc8-118">Per informazioni dettagliate, vedere <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and define Peers in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d3fc8-118">For details, see <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="d3fc8-119">Protezione del Mediation Server per il trunking SIP</span><span class="sxs-lookup"><span data-stu-id="d3fc8-119">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="d3fc8-p104">Per motivi di sicurezza è opportuno configurare una LAN virtuale (VLAN) per ogni connessione tra i due router VPN. La procedura per la configurazione di una VLAN varia in base al produttore del router. Per informazioni dettagliate, rivolgersi al fornitore del router.</span><span class="sxs-lookup"><span data-stu-id="d3fc8-p104">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers. The actual process for setting up a VLAN varies from one router manufacturer to another. For details, contact your router vendor.</span></span>

<span data-ttu-id="d3fc8-123">È consigliabile attenersi alle linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3fc8-123">We recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="d3fc8-124">Configurare una LAN virtuale (VLAN) tra il Mediation Server e il router VPN nella rete perimetrale (nota anche come DMZ, area demilitarizzata e subnet schermata).</span><span class="sxs-lookup"><span data-stu-id="d3fc8-124">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

  - <span data-ttu-id="d3fc8-125">Non consentire il trasferimento di pacchetti broadcast o multicast dal router alla VLAN.</span><span class="sxs-lookup"><span data-stu-id="d3fc8-125">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

  - <span data-ttu-id="d3fc8-126">Bloccare tutte le regole di routing che instradano il traffico dal router a Anywhere but Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d3fc8-126">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="d3fc8-127">Se si utilizza un server VPN, è consigliabile attenersi alle linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3fc8-127">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="d3fc8-128">Configurare una VLAN tra il server VPN e il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d3fc8-128">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

  - <span data-ttu-id="d3fc8-129">Non consentire la trasmissione di pacchetti broadcast o multicast dal server VPN alla VLAN.</span><span class="sxs-lookup"><span data-stu-id="d3fc8-129">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

  - <span data-ttu-id="d3fc8-130">Blocca tutte le regole di routing che instradano il traffico del server VPN ovunque tranne il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d3fc8-130">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

  - <span data-ttu-id="d3fc8-131">Crittografare i dati sulla VPN utilizzando Generic Routing Encapsulation (GRE).</span><span class="sxs-lookup"><span data-stu-id="d3fc8-131">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

