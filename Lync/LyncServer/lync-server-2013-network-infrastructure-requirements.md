---
title: Requisiti per l'infrastruttura di rete di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc1f74705469bf3a024d84848942eae972e0a629
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="4e532-102">Requisiti per l'infrastruttura di rete per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e532-102">Network infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e532-103">_**Argomento Ultima modifica:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="4e532-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="4e532-104">La scheda scheda di rete di ogni server nella topologia di Lync Server 2013 deve supportare almeno 1 Gigabit al secondo (Gbps).</span><span class="sxs-lookup"><span data-stu-id="4e532-104">The network adapter card of each server in the Lync Server 2013 topology must support at least 1 gigabit per second (Gbps).</span></span> <span data-ttu-id="4e532-105">In generale, è consigliabile connettere tutti i ruoli del server all'interno della topologia di Lync Server tramite una rete LAN (Local Area Network) a bassa latenza e ad alta larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="4e532-105">In general, you should connect all server roles within the Lync Server topology using a low latency and high bandwidth local area network (LAN).</span></span> <span data-ttu-id="4e532-106">Le dimensioni della LAN dipendono dalle dimensioni della topologia:</span><span class="sxs-lookup"><span data-stu-id="4e532-106">The size of the LAN is dependent on the size of the topology:</span></span>

  - <span data-ttu-id="4e532-107">Nelle topologie standard Edition i server devono essere in una rete che supporta 1 Gbps Ethernet o equivalente.</span><span class="sxs-lookup"><span data-stu-id="4e532-107">In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.</span></span>

  - <span data-ttu-id="4e532-108">Nelle topologie del pool Front-end la maggior parte dei server dovrebbe essere in una rete che supporta più di 1 Gbps, in particolare quando si supportano la condivisione di applicazioni e conferenze audio/video (A/V).</span><span class="sxs-lookup"><span data-stu-id="4e532-108">In Front End pool topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.</span></span>

<span data-ttu-id="4e532-109">Per l'integrazione PSTN (Public Switched Telephone Network), è possibile integrare tramite linee T1/E1 o trunking SIP.</span><span class="sxs-lookup"><span data-stu-id="4e532-109">For public switched telephone network (PSTN) integration, you can integrate by using either T1/E1 lines or SIP trunking.</span></span>

<div>

## <a name="audiovideo-network-requirements"></a><span data-ttu-id="4e532-110">Requisiti di rete audio/video</span><span class="sxs-lookup"><span data-stu-id="4e532-110">Audio/Video Network Requirements</span></span>

<span data-ttu-id="4e532-111">I requisiti di rete per audio/video (A/V) in una distribuzione di Lync Server includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e532-111">Network requirements for audio/video (A/V) in a Lync Server deployment include the following:</span></span>

  - <span data-ttu-id="4e532-112">Se si distribuisce un singolo Edge Server o un pool di Edge tramite il bilanciamento del carico DNS, è possibile configurare il firewall esterno come NAT.</span><span class="sxs-lookup"><span data-stu-id="4e532-112">If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the external firewall as a NAT.</span></span> <span data-ttu-id="4e532-113">Non è possibile configurare il firewall interno come NAT.</span><span class="sxs-lookup"><span data-stu-id="4e532-113">You cannot configure the internal firewall as a NAT.</span></span> <span data-ttu-id="4e532-114">Per informazioni dettagliate su questi requisiti, vedere [determinare i requisiti per il firewall e la porta a/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="4e532-114">For details about these requirements, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in the Planning documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4e532-115">Se si ha un pool di bordi e si usa un dispositivo di bilanciamento del carico hardware, è necessario usare gli indirizzi IP pubblici in tutti i server perimetrali e non è possibile usare il NAT per i server o il pool di dispositivi NAT, ad esempio il firewall o un altro dispositivo di infrastruttura che NAT inbou ND o traffico in uscita).</span><span class="sxs-lookup"><span data-stu-id="4e532-115">If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on each of the Edge Servers and you cannot use NAT for the servers or the pool at your NAT device (for example, the firewall, or other infrastructure device that would NAT inbound or outbound traffic).</span></span> <span data-ttu-id="4e532-116">Per informazioni dettagliate, vedere <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Edge consolidato basato su riassunto della porta con i dispositivi di bilanciamento del carico hardware in Lync Server 2013</A> nella documentazione relativa alla pianificazione per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="4e532-116">For details, see <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A> in the Planning for External User Access documentation.</span></span>

    
    </div>

  - <span data-ttu-id="4e532-117">Se l'organizzazione usa un'infrastruttura QoS (Quality of Service), il sottosistema multimediale è progettato per funzionare all'interno di questa infrastruttura esistente.</span><span class="sxs-lookup"><span data-stu-id="4e532-117">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span>

  - <span data-ttu-id="4e532-118">Se si usa Internet Protocol Security (IPsec), è consigliabile disabilitare IPsec sugli intervalli di porte usati per il traffico A/V.</span><span class="sxs-lookup"><span data-stu-id="4e532-118">If you use Internet Protocol security (IPsec), we recommend disabling IPsec over the port ranges used for A/V traffic.</span></span> <span data-ttu-id="4e532-119">Per informazioni dettagliate, vedere [Eccezioni IPsec in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="4e532-119">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

<span data-ttu-id="4e532-120">Per garantire una qualità media ottimale, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e532-120">To ensure optimal media quality, do the following:</span></span>

  - <span data-ttu-id="4e532-121">Eseguire il provisioning dei collegamenti di rete per supportare la velocità effettiva di 65 kilobit al secondo (Kbps) per flusso audio e 500 kbps per ogni flusso video, se abilitato, durante i periodi di utilizzo massimo.</span><span class="sxs-lookup"><span data-stu-id="4e532-121">Provision your network links to support throughput of 65 kilobits per second (Kbps) per audio stream and 500 Kbps per video stream, if enabled, during peak usage periods.</span></span> <span data-ttu-id="4e532-122">Una sessione audio o video bidirezionale è costituita da due flussi.</span><span class="sxs-lookup"><span data-stu-id="4e532-122">A bidirectional audio or video session consists of two streams.</span></span>

  - <span data-ttu-id="4e532-123">Per far fronte a picchi imprevisti nel traffico sopra questo livello e ad un maggiore utilizzo nel tempo, gli endpoint multimediali di Lync Server possono adattarsi alle diverse condizioni di rete e supportare carichi di tre volte la velocità effettiva (Vedi paragrafo precedente) per l'audio e il video mentre si è ancora mantenere una qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="4e532-123">To cope with unexpected spikes in traffic above this level and increased usage over time, Lync Server media endpoints can adapt to varying network conditions and support loads of three times the throughput (see previous paragraph) for audio and video while still retaining acceptable quality.</span></span> <span data-ttu-id="4e532-124">Tuttavia, non presupporre che questa adattabilità supporti una rete sottoposta a provisioning.</span><span class="sxs-lookup"><span data-stu-id="4e532-124">However, do not assume that this adaptability will support an under-provisioned network.</span></span> <span data-ttu-id="4e532-125">In una rete sottoposta a provisioning, la capacità degli endpoint multimediali di Lync Server di gestire in modo dinamico le diverse condizioni di rete, ad esempio la perdita temporanea di pacchetti elevati, viene ridotta.</span><span class="sxs-lookup"><span data-stu-id="4e532-125">In an under-provisioned network, the ability of the Lync Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.</span></span>

  - <span data-ttu-id="4e532-126">Per i collegamenti di rete in cui il provisioning è estremamente costoso e difficile, potrebbe essere necessario prendere in considerazione il provisioning per un volume di traffico più basso.</span><span class="sxs-lookup"><span data-stu-id="4e532-126">For network links where provisioning is extremely costly and difficult, you may need to consider provisioning for a lower volume of traffic.</span></span> <span data-ttu-id="4e532-127">In questo scenario, l'elasticità degli endpoint multimediali di Lync Server assorbe la differenza tra il volume del traffico e il livello di traffico massimo, a scapito di una certa riduzione della qualità vocale.</span><span class="sxs-lookup"><span data-stu-id="4e532-127">In this scenario, let the elasticity of the Lync Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality.</span></span> <span data-ttu-id="4e532-128">Inoltre, c'è una diminuzione dello spazio di lavoro altrimenti disponibile per assorbire picchi improvvisi nel traffico.</span><span class="sxs-lookup"><span data-stu-id="4e532-128">Also, there is a decrease in the headroom otherwise available to absorb sudden peaks in traffic.</span></span>

  - <span data-ttu-id="4e532-129">Per i collegamenti che non è possibile eseguire correttamente il provisioning a breve termine, ad esempio un sito con collegamenti WAN molto scarsi, è consigliabile disabilitare il video per alcuni utenti.</span><span class="sxs-lookup"><span data-stu-id="4e532-129">For links that cannot be correctly provisioned in the short term (for example, a site with very poor WAN links), consider disabling video for certain users.</span></span>

  - <span data-ttu-id="4e532-130">Eseguire il provisioning della rete per garantire un massimo ritardo finale (latenza) di 150 millisecondi (MS) in caricamento massimo.</span><span class="sxs-lookup"><span data-stu-id="4e532-130">Provision your network to ensure a maximum end-to-end delay (latency) of 150 milliseconds (ms) under peak load.</span></span> <span data-ttu-id="4e532-131">La latenza è l'unica compromissione della rete che i componenti multimediali di Lync Server non possono ridurre ed è importante trovare ed eliminare i punti deboli.</span><span class="sxs-lookup"><span data-stu-id="4e532-131">Latency is the one network impairment that Lync Server media components cannot reduce, and it is important to find and eliminate the weak points.</span></span>

  - <span data-ttu-id="4e532-132">Per i server che utilizzano software antivirus, includere tutti i server che utilizzano Lync Server nell'elenco delle eccezioni per garantire prestazioni e qualità audio ottimali.</span><span class="sxs-lookup"><span data-stu-id="4e532-132">For servers running antivirus software, include all servers running Lync Server in the exception list in order to provide optimal performance and audio quality.</span></span>

</div>

<div>

## <a name="conferencing-network-requirements"></a><span data-ttu-id="4e532-133">Requisiti di rete per i servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="4e532-133">Conferencing Network Requirements</span></span>

<span data-ttu-id="4e532-134">La larghezza di banda usata per scaricare il contenuto delle conferenze dal server Internet Information Services (IIS) dipende dalle dimensioni del contenuto caricato.</span><span class="sxs-lookup"><span data-stu-id="4e532-134">The bandwidth that is used to download conference content from the Internet Information Services (IIS) server depends on the size of the content that is uploaded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

