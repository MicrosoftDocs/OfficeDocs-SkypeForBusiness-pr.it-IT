---
title: Requisiti dell'infrastruttura di rete di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea383a77ff8d6089e2a01d7fb00df434f6d805e5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="a8870-102">Requisiti dell'infrastruttura di rete per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8870-102">Network infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8870-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="a8870-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="a8870-104">La scheda della scheda di rete di ogni server nella topologia di Lync Server 2013 deve supportare almeno 1 Gigabit al secondo (Gbps).</span><span class="sxs-lookup"><span data-stu-id="a8870-104">The network adapter card of each server in the Lync Server 2013 topology must support at least 1 gigabit per second (Gbps).</span></span> <span data-ttu-id="a8870-105">In generale, è consigliabile connettere tutti i ruoli del server nella topologia di Lync Server con una bassa latenza e una rete LAN (Local Area Network) di larghezza di banda elevata.</span><span class="sxs-lookup"><span data-stu-id="a8870-105">In general, you should connect all server roles within the Lync Server topology using a low latency and high bandwidth local area network (LAN).</span></span> <span data-ttu-id="a8870-106">Le dimensioni della rete LAN dipendono da quelle della topologia:</span><span class="sxs-lookup"><span data-stu-id="a8870-106">The size of the LAN is dependent on the size of the topology:</span></span>

  - <span data-ttu-id="a8870-107">Nelle topologie standard Edition i server devono trovarsi in una rete che supporta 1 Gbps Ethernet o equivalente.</span><span class="sxs-lookup"><span data-stu-id="a8870-107">In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.</span></span>

  - <span data-ttu-id="a8870-108">Nelle topologie del pool Front End, la maggior parte dei server deve trovarsi in una rete che supporta più di 1 Gbps, soprattutto quando si supportano le conferenze audio/video (A/V) e la condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a8870-108">In Front End pool topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.</span></span>

<span data-ttu-id="a8870-109">È possibile supportare l'integrazione della rete PSTN (Public Switched Telephone Network) utilizzando linee T1/E1 o il trunking SIP.</span><span class="sxs-lookup"><span data-stu-id="a8870-109">For public switched telephone network (PSTN) integration, you can integrate by using either T1/E1 lines or SIP trunking.</span></span>

<div>

## <a name="audiovideo-network-requirements"></a><span data-ttu-id="a8870-110">Requisiti di rete audio/video</span><span class="sxs-lookup"><span data-stu-id="a8870-110">Audio/Video Network Requirements</span></span>

<span data-ttu-id="a8870-111">I requisiti di rete per audio/video (A/V) in una distribuzione di Lync Server includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a8870-111">Network requirements for audio/video (A/V) in a Lync Server deployment include the following:</span></span>

  - <span data-ttu-id="a8870-112">Se si sta distribuendo un singolo server perimetrale o un pool di Edge utilizzando il bilanciamento del carico DNS, è possibile configurare il firewall esterno come NAT.</span><span class="sxs-lookup"><span data-stu-id="a8870-112">If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the external firewall as a NAT.</span></span> <span data-ttu-id="a8870-113">Non è possibile configurare il firewall interno come NAT.</span><span class="sxs-lookup"><span data-stu-id="a8870-113">You cannot configure the internal firewall as a NAT.</span></span> <span data-ttu-id="a8870-114">Per informazioni dettagliate su questi requisiti, vedere [Determine External a/V firewall and Port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a8870-114">For details about these requirements, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in the Planning documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a8870-115">Se si dispone di un pool di server perimetrali e si utilizza un dispositivo di bilanciamento del carico hardware, è necessario utilizzare gli indirizzi IP pubblici su ciascuno dei server perimetrali e non è possibile utilizzare il NAT per il pool o il gruppo del computer NAT (ad esempio, il firewall o un altro dispositivo di infrastruttura che NAT inbou traffico in uscita o ND).</span><span class="sxs-lookup"><span data-stu-id="a8870-115">If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on each of the Edge Servers and you cannot use NAT for the servers or the pool at your NAT device (for example, the firewall, or other infrastructure device that would NAT inbound or outbound traffic).</span></span> <span data-ttu-id="a8870-116">Per informazioni dettagliate, vedere <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Riepilogo delle porte-Edge consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync Server 2013</A> nella documentazione relativa alla pianificazione per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="a8870-116">For details, see <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A> in the Planning for External User Access documentation.</span></span>

    
    </div>

  - <span data-ttu-id="a8870-117">Se nell'organizzazione è prevista un'infrastruttura di qualità del servizio (QoS), il sottosistema multimediale è progettato per essere utilizzato nell'infrastruttura esistente.</span><span class="sxs-lookup"><span data-stu-id="a8870-117">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span>

  - <span data-ttu-id="a8870-118">Se si utilizza IPSec (Internet Protocol security), è consigliabile disabilitarlo per gli intervalli di porte usati per il traffico A/V.</span><span class="sxs-lookup"><span data-stu-id="a8870-118">If you use Internet Protocol security (IPsec), we recommend disabling IPsec over the port ranges used for A/V traffic.</span></span> <span data-ttu-id="a8870-119">Per informazioni dettagliate, vedere [IPSec Exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a8870-119">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

<span data-ttu-id="a8870-120">Per garantire una qualità multimediale ottimale, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8870-120">To ensure optimal media quality, do the following:</span></span>

  - <span data-ttu-id="a8870-p105">Effettuare il provisioning dei collegamenti di rete in modo da supportare la velocità effettiva di 65 kilobit al secondo (Kbps) per flusso audio e 500 Kbps per flusso video, se abilitati, durante i periodi di picco di utilizzo. Una sessione audio o video bidirezionale è costituita da due flussi.</span><span class="sxs-lookup"><span data-stu-id="a8870-p105">Provision your network links to support throughput of 65 kilobits per second (Kbps) per audio stream and 500 Kbps per video stream, if enabled, during peak usage periods. A bidirectional audio or video session consists of two streams.</span></span>

  - <span data-ttu-id="a8870-123">Per far fronte a picchi imprevisti nel traffico al di sopra di questo livello e aumentare l'utilizzo nel tempo, gli endpoint multimediali di Lync Server possono adattarsi a diverse condizioni di rete e supportare carichi pari a tre volte la velocità effettiva (vedere il paragrafo precedente) per l'audio e il video, mentre ancora mantenere la qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="a8870-123">To cope with unexpected spikes in traffic above this level and increased usage over time, Lync Server media endpoints can adapt to varying network conditions and support loads of three times the throughput (see previous paragraph) for audio and video while still retaining acceptable quality.</span></span> <span data-ttu-id="a8870-124">Questa adattabilità non deve tuttavia lasciar supporre che venga supportata una rete sottodimensionata.</span><span class="sxs-lookup"><span data-stu-id="a8870-124">However, do not assume that this adaptability will support an under-provisioned network.</span></span> <span data-ttu-id="a8870-125">In una rete sottoposta a provisioning, la capacità degli endpoint multimediali di Lync Server di gestire dinamicamente le diverse condizioni di rete, ad esempio la perdita temporanea di pacchetti elevati, è ridotta.</span><span class="sxs-lookup"><span data-stu-id="a8870-125">In an under-provisioned network, the ability of the Lync Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.</span></span>

  - <span data-ttu-id="a8870-126">Per i collegamenti di rete in cui il provisioning è un'operazione estremamente costosa e difficile, potrebbe essere necessario valutare la possibilità di effettuare il provisioning per un volume di traffico inferiore.</span><span class="sxs-lookup"><span data-stu-id="a8870-126">For network links where provisioning is extremely costly and difficult, you may need to consider provisioning for a lower volume of traffic.</span></span> <span data-ttu-id="a8870-127">In questo scenario, lasciare che l'elasticità degli endpoint multimediali di Lync Server assorba la differenza tra il volume del traffico e il livello di traffico di picco, a scapito di una certa riduzione della qualità vocale.</span><span class="sxs-lookup"><span data-stu-id="a8870-127">In this scenario, let the elasticity of the Lync Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality.</span></span> <span data-ttu-id="a8870-128">Si verifica inoltre una riduzione della capacità aggiuntiva altrimenti disponibile per assorbire picchi di traffico improvvisi.</span><span class="sxs-lookup"><span data-stu-id="a8870-128">Also, there is a decrease in the headroom otherwise available to absorb sudden peaks in traffic.</span></span>

  - <span data-ttu-id="a8870-129">Per i collegamenti di cui non è possibile effettuare correttamente il provisioning in tempi brevi, ad esempio un sito con collegamenti WAN insufficienti, valutare la possibilità di disabilitare la funzionalità video per alcuni utenti.</span><span class="sxs-lookup"><span data-stu-id="a8870-129">For links that cannot be correctly provisioned in the short term (for example, a site with very poor WAN links), consider disabling video for certain users.</span></span>

  - <span data-ttu-id="a8870-130">Eseguire il provisioning della rete per garantire un massimo ritardo end-to-end (latenza) di 150 millisecondi (MS) sotto carico di picco.</span><span class="sxs-lookup"><span data-stu-id="a8870-130">Provision your network to ensure a maximum end-to-end delay (latency) of 150 milliseconds (ms) under peak load.</span></span> <span data-ttu-id="a8870-131">Latenza è l'unica compromissione della rete che i componenti multimediali di Lync Server non possono ridurre ed è importante individuare ed eliminare i punti deboli.</span><span class="sxs-lookup"><span data-stu-id="a8870-131">Latency is the one network impairment that Lync Server media components cannot reduce, and it is important to find and eliminate the weak points.</span></span>

  - <span data-ttu-id="a8870-132">Per i server che eseguono il software antivirus, includere tutti i server che eseguono Lync Server nell'elenco delle eccezioni per garantire prestazioni ottimali e qualità audio.</span><span class="sxs-lookup"><span data-stu-id="a8870-132">For servers running antivirus software, include all servers running Lync Server in the exception list in order to provide optimal performance and audio quality.</span></span>

</div>

<div>

## <a name="conferencing-network-requirements"></a><span data-ttu-id="a8870-133">Requisiti di rete per le conferenze</span><span class="sxs-lookup"><span data-stu-id="a8870-133">Conferencing Network Requirements</span></span>

<span data-ttu-id="a8870-134">La larghezza di banda utilizzata per scaricare il contenuto delle conferenze dal server Internet Information Services (IIS) dipende dalle dimensioni del contenuto caricato.</span><span class="sxs-lookup"><span data-stu-id="a8870-134">The bandwidth that is used to download conference content from the Internet Information Services (IIS) server depends on the size of the content that is uploaded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

