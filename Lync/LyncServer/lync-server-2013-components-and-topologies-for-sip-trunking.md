---
title: 'Lync Server 2013: Componenti e topologie per il trunking SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc1b80078f942f3f70957a7af6b27b7dd9210046
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="89903-102">Componenti e topologie per il trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89903-102">Components and topologies for SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89903-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="89903-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="89903-104">Nella figura seguente viene illustrata la topologia di trunking SIP in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89903-104">The following figure depicts the SIP trunking topology in Lync Server.</span></span>

<span data-ttu-id="89903-105">**Topologia di trunking SIP**</span><span class="sxs-lookup"><span data-stu-id="89903-105">**SIP trunking topology**</span></span>

<span data-ttu-id="89903-106">(images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "Topologia di trunking") SIP ![topologia]trunking SIP</span><span class="sxs-lookup"><span data-stu-id="89903-106">![SIP Trunking Topology](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP Trunking Topology")</span></span>

<span data-ttu-id="89903-107">Come illustrato nel diagramma, per la connettività tra la rete aziendale e il provider di servizi PSTN (Public Switched Telephone Network) viene usata una rete privata virtuale IP (VPN).</span><span class="sxs-lookup"><span data-stu-id="89903-107">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider.</span></span> <span data-ttu-id="89903-108">Lo scopo di questa rete privata è offrire connettività IP, migliorare la sicurezza e, facoltativamente, ottenere garanzie di qualità del servizio (QoS).</span><span class="sxs-lookup"><span data-stu-id="89903-108">The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees.</span></span> <span data-ttu-id="89903-109">A causa della natura di una VPN, non è necessario usare Transport Layer Security (TLS) per il traffico di segnalazione SIP o il protocollo di trasporto in tempo reale (SRTP) sicuro per il traffico multimediale.</span><span class="sxs-lookup"><span data-stu-id="89903-109">Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic.</span></span> <span data-ttu-id="89903-110">Le connessioni tra l'organizzazione e il provider di servizi sono quindi costituite da connessioni TCP semplici per SIP e per il protocollo RTP (Plain Real-Time Transport Protocol) (tramite UDP) per i contenuti multimediali tramite una rete VPN IP.</span><span class="sxs-lookup"><span data-stu-id="89903-110">Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN.</span></span> <span data-ttu-id="89903-111">Assicurarsi che tutti i firewall tra i router VPN dispongano delle porte aperte per consentire ai router VPN di comunicare e che gli indirizzi IP sui bordi esterni dei router VPN siano instradabili pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="89903-111">Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="89903-112">Contattare il provider di servizi per determinare se fornisce il supporto per l'elevata disponibilità, incluso il failover.</span><span class="sxs-lookup"><span data-stu-id="89903-112">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="89903-113">In caso affermativo, dovrai determinare le procedure per configurarlo.</span><span class="sxs-lookup"><span data-stu-id="89903-113">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="89903-114">Ad esempio, è necessario configurare un solo indirizzo IP e un trunk SIP in ogni Mediation Server oppure è necessario configurare più trunk SIP in ogni Mediation Server?</span><span class="sxs-lookup"><span data-stu-id="89903-114">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span><BR><span data-ttu-id="89903-115">Se si hanno più siti centrali, chiedere anche se il provider di servizi ha la possibilità di abilitare le connessioni da e verso un altro sito centrale.</span><span class="sxs-lookup"><span data-stu-id="89903-115">If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="89903-116">Per il trunking SIP consigliamo vivamente di distribuire server di mediazione autonomi.</span><span class="sxs-lookup"><span data-stu-id="89903-116">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="89903-117">Per informazioni dettagliate, vedere <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">distribuzione di Mediation Server e definizione di peer in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="89903-117">For details, see <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="89903-118">Protezione del server Mediation per il trunking SIP</span><span class="sxs-lookup"><span data-stu-id="89903-118">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="89903-119">Per motivi di sicurezza, è necessario configurare una LAN virtuale (VLAN) per ogni connessione tra i due router VPN.</span><span class="sxs-lookup"><span data-stu-id="89903-119">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers.</span></span> <span data-ttu-id="89903-120">Il processo effettivo per la configurazione di una VLAN varia da un produttore di router a un altro.</span><span class="sxs-lookup"><span data-stu-id="89903-120">The actual process for setting up a VLAN varies from one router manufacturer to another.</span></span> <span data-ttu-id="89903-121">Per informazioni dettagliate, contattare il fornitore del router.</span><span class="sxs-lookup"><span data-stu-id="89903-121">For details, contact your router vendor.</span></span>

<span data-ttu-id="89903-122">Ti consigliamo di seguire queste linee guida:</span><span class="sxs-lookup"><span data-stu-id="89903-122">We recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="89903-123">Configurare una LAN virtuale (VLAN) tra il Mediation Server e il router VPN nella rete perimetrale (nota anche come DMZ, zona demilitarizzata e subnet schermata).</span><span class="sxs-lookup"><span data-stu-id="89903-123">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

  - <span data-ttu-id="89903-124">Non consentire il trasferimento di pacchetti broadcast o multicast dal router alla VLAN.</span><span class="sxs-lookup"><span data-stu-id="89903-124">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

  - <span data-ttu-id="89903-125">Bloccare le regole di routing che instradano il traffico dal router a un punto qualsiasi ma al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="89903-125">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="89903-126">Se si usa un server VPN, è consigliabile seguire queste linee guida:</span><span class="sxs-lookup"><span data-stu-id="89903-126">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="89903-127">Configurare una VLAN tra il server VPN e il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="89903-127">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

  - <span data-ttu-id="89903-128">Non consentire la trasmissione di pacchetti broadcast o multicast dal server VPN alla VLAN.</span><span class="sxs-lookup"><span data-stu-id="89903-128">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

  - <span data-ttu-id="89903-129">Bloccare qualsiasi regola di routing che instrada il traffico del server VPN ovunque, eccetto il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="89903-129">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

  - <span data-ttu-id="89903-130">Crittografare i dati nella rete VPN usando Generic Routing Encapsulation (GRE).</span><span class="sxs-lookup"><span data-stu-id="89903-130">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

