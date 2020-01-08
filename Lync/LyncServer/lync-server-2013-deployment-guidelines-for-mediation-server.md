---
title: 'Lync Server 2013: linee guida per la distribuzione di Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 400f8cceeb86d407297b3f564c01266a477ca0ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="830e0-102">Linee guida per la distribuzione di Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="830e0-102">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="830e0-103">_**Argomento Ultima modifica:** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="830e0-103">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="830e0-104">Questo argomento descrive le linee guida per la pianificazione della distribuzione di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="830e0-104">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="830e0-105">Dopo aver rivisto queste linee guida, è consigliabile usare lo strumento di pianificazione per creare e visualizzare le possibili topologie alternative, che possono essere usate come modelli per l'aspetto della topologia sartoriale finale che si decide di distribuire.</span><span class="sxs-lookup"><span data-stu-id="830e0-105">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="830e0-106">Mediation Server collocato o autonomo?</span><span class="sxs-lookup"><span data-stu-id="830e0-106">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="830e0-107">Mediation Server è collocato per impostazione predefinita nel server Standard Edition o front end server in un pool Front-end presso i siti centrali.</span><span class="sxs-lookup"><span data-stu-id="830e0-107">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="830e0-108">Il numero di chiamate PSTN (Public Switched Telephone Network) che è possibile gestire e il numero di computer necessari nel pool dipenderà dalle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="830e0-108">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="830e0-109">Numero di peer gateway che il pool di Mediation Server controlla</span><span class="sxs-lookup"><span data-stu-id="830e0-109">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="830e0-110">I periodi di traffico ad alto volume tramite questi gateway</span><span class="sxs-lookup"><span data-stu-id="830e0-110">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="830e0-111">Percentuale di chiamate che vengono chiamate il cui elemento multimediale ignora il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="830e0-111">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="830e0-112">Durante la pianificazione, assicurati di tenere conto dei requisiti per l'elaborazione dei contenuti multimediali per le chiamate PSTN e le conferenze A/V non configurate per il bypass multimediale, nonché l'elaborazione necessaria per gestire le interazioni di segnalazione per il numero di chiamate in orario occupato che devono essere supportate.</span><span class="sxs-lookup"><span data-stu-id="830e0-112">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="830e0-113">Se la CPU non è sufficiente, è necessario distribuire un pool autonomo di Mediation Server; i gateway PSTN, IP-PBX e SBCs dovranno essere divisi in subset controllati dai server di mediazione collocati in un pool e i Mediation Server autonomi in uno o più pool autonomi.</span><span class="sxs-lookup"><span data-stu-id="830e0-113">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="830e0-114">Se sono stati distribuiti gateway PSTN, IP-PBX o Session Border Controller (SBCs) che non supportano le funzionalità corrette per interagire con un pool di server di mediazione, inclusi i seguenti, sarà necessario associarli a un pool autonomo costituito da di un singolo Mediation Server:</span><span class="sxs-lookup"><span data-stu-id="830e0-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="830e0-115">Eseguire il bilanciamento del carico DNS (Network layer Domain Name System) in Mediation Servers in un pool (o in caso contrario instradare il traffico in modo uniforme a tutti i Mediation Server in un pool)</span><span class="sxs-lookup"><span data-stu-id="830e0-115">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="830e0-116">Accettare il traffico da qualsiasi Mediation Server in un pool</span><span class="sxs-lookup"><span data-stu-id="830e0-116">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="830e0-117">È possibile usare Microsoft Lync Server 2013, strumento di pianificazione per valutare se la collocazione di Mediation Server con il pool Front-end può gestire il carico.</span><span class="sxs-lookup"><span data-stu-id="830e0-117">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="830e0-118">Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="830e0-118">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="830e0-119">Considerazioni sul sito centrale e sulla filiale</span><span class="sxs-lookup"><span data-stu-id="830e0-119">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="830e0-120">I Mediation Server nel sito centrale possono essere usati per instradare le chiamate per i PBX IP o i gateway PSTN nei siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="830e0-120">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="830e0-121">Se si distribuiscono trunk SIP, tuttavia, è necessario distribuire un Mediation Server nel sito in cui ogni trunk termina.</span><span class="sxs-lookup"><span data-stu-id="830e0-121">If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="830e0-122">L'uso di un Mediation Server presso la route del sito centrale richiede un gateway IP-PBX o PSTN presso un sito di succursale non richiede l'utilizzo di bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="830e0-122">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass.</span></span> <span data-ttu-id="830e0-123">Tuttavia, se è possibile abilitare il bypass multimediale, in questo modo si ridurrà la latenza del percorso multimediale e, di conseguenza, si tradurrebbe in una qualità multimediale migliorata perché il percorso del supporto non è più necessario per seguire il percorso di segnalazione.</span><span class="sxs-lookup"><span data-stu-id="830e0-123">However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path.</span></span> <span data-ttu-id="830e0-124">Il bypass multimediale ridurrà anche il carico di elaborazione nel pool.</span><span class="sxs-lookup"><span data-stu-id="830e0-124">Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="830e0-125">Il bypass multimediale non si interagisce con ogni gateway PSTN, IP-PBX e SBC.</span><span class="sxs-lookup"><span data-stu-id="830e0-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="830e0-126">Microsoft ha testato un set di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con Cisco IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="830e0-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="830e0-127">Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program-Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>at.</span><span class="sxs-lookup"><span data-stu-id="830e0-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="830e0-128">Se è necessaria la resilienza del sito di succursale, è necessario distribuire un Survivable Branch Appliance o una combinazione di un server front-end, un Mediation Server e un gateway nel sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="830e0-128">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="830e0-129">Il presupposto con la resilienza del sito di succursale è che la presenza e i servizi di conferenza non sono resilienti nel sito. Per indicazioni sulla pianificazione del sito di succursale per la voce, vedere [pianificazione della resilienza vocale del sito di succursale in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="830e0-129">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="830e0-130">Per le interazioni con un IP-PBX, se l'IP-PBX non supporta correttamente le interazioni multimediali iniziali con più finestre di dialogo iniziali e interazioni RFC 3960, può essere possibile ritagliare le prime parole del messaggio di saluto per le chiamate in arrivo da IP-PBX agli endpoint di Lync.</span><span class="sxs-lookup"><span data-stu-id="830e0-130">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="830e0-131">Questo comportamento può essere più grave se un Mediation Server presso un sito centrale sta instradando le chiamate per un IP-PBX in cui la route termina in un sito di succursale, perché è necessario più tempo per il completamento della segnalazione.</span><span class="sxs-lookup"><span data-stu-id="830e0-131">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="830e0-132">Se si verifica questo comportamento, la distribuzione di un Mediation Server presso il sito della filiale è l'unico modo per ridurre il ritaglio delle prime parole.</span><span class="sxs-lookup"><span data-stu-id="830e0-132">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="830e0-133">Infine, se il sito centrale ha un PBX TDM o se il tuo IP-PBX non elimina la necessità di un gateway PSTN, devi distribuire un gateway sulla route di chiamata che connette Mediation Server e il PBX.</span><span class="sxs-lookup"><span data-stu-id="830e0-133">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="830e0-134">Per migliorare le prestazioni multimediali di Mediation Server autonomo, è consigliabile abilitare l'RSS (Receive-Side Scaling) sulle schede di rete in questi server.</span><span class="sxs-lookup"><span data-stu-id="830e0-134">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="830e0-135">RSS consente ai pacchetti in arrivo di essere gestiti in parallelo da più processori nel server.</span><span class="sxs-lookup"><span data-stu-id="830e0-135">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="830e0-136">Per informazioni dettagliate, vedere "miglioramenti al ridimensionamento sul lato ricezione in Windows Server <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="830e0-136">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="830e0-137">Per informazioni dettagliate su come abilitare l'RSS, vedere la documentazione della scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="830e0-137">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

