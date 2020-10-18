---
title: 'Lync Server 2013: linee guida per la distribuzione di Mediation Server'
description: 'Lync Server 2013: linee guida per la distribuzione di Mediation Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8198431b24714666c9411029aecd12835014fef4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575772"
---
# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="779e1-103">Linee guida per la distribuzione di Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="779e1-103">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="779e1-104">_**Ultimo argomento modificato:** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="779e1-104">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="779e1-105">Questo argomento descrive le linee guida per la pianificazione della distribuzione di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="779e1-105">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="779e1-106">Dopo aver esaminato queste linee guida, è consigliabile utilizzare lo strumento di pianificazione per creare e visualizzare le possibili topologie alternative, che possono essere utilizzate come modelli per l'aspetto della topologia sartoriale finale che si decide di distribuire.</span><span class="sxs-lookup"><span data-stu-id="779e1-106">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="779e1-107">Mediation Server collocato o autonomo?</span><span class="sxs-lookup"><span data-stu-id="779e1-107">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="779e1-108">Per impostazione predefinita, Mediation Server è collocato nel server Standard Edition o Front End Server in un pool Front-End nei siti centrali.</span><span class="sxs-lookup"><span data-stu-id="779e1-108">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="779e1-109">Il numero di chiamate PSTN (Public Switched Telephone Network) che è possibile gestire e il numero di computer necessari nel pool dipendono dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="779e1-109">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="779e1-110">Il numero di peer gateway che il pool di Mediation Server controlla</span><span class="sxs-lookup"><span data-stu-id="779e1-110">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="779e1-111">I periodi di traffico ad alto volume tramite quei gateway</span><span class="sxs-lookup"><span data-stu-id="779e1-111">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="779e1-112">La percentuale di chiamate che sono chiamate con il supporto bypassare il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="779e1-112">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="779e1-113">Durante la pianificazione, tenere conto dei requisiti di elaborazione dei contenuti multimediali per le chiamate PSTN e le conferenze A/V che non sono configurate per il bypass multimediale, nonché l'elaborazione necessaria per gestire le interazioni di segnalazione per il numero di chiamate in orario di occupato che devono essere supportate.</span><span class="sxs-lookup"><span data-stu-id="779e1-113">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="779e1-114">Se la CPU non è sufficiente, è necessario distribuire un pool autonomo di Mediation Server. i gateway PSTN, IP-PBX e SBCs dovranno essere suddivisi in sottoinsiemi controllati dai Mediation Server collocati in un pool e nei Mediation Server autonomi in uno o più pool autonomi.</span><span class="sxs-lookup"><span data-stu-id="779e1-114">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="779e1-115">Se sono stati distribuiti gateway PSTN, IP-PBX o Session Border Controller (SBCs) che non supportano le funzionalità corrette per interagire con un pool di Mediation Server, tra cui i seguenti, dovranno essere associati a un pool autonomo costituito da un singolo Mediation Server:</span><span class="sxs-lookup"><span data-stu-id="779e1-115">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="779e1-116">Eseguire il bilanciamento del carico DNS (Domain Name System) di Network layer su Mediation Server in un pool (o altrimenti instradare il traffico in modo uniforme a tutti i Mediation Server in un pool)</span><span class="sxs-lookup"><span data-stu-id="779e1-116">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="779e1-117">Accettazione del traffico proveniente da qualsiasi server Mediation Server in un pool</span><span class="sxs-lookup"><span data-stu-id="779e1-117">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="779e1-118">È possibile utilizzare Microsoft Lync Server 2013, strumento di pianificazione per valutare se la collocazione del Mediation Server con il pool Front End è in grado di gestire il carico.</span><span class="sxs-lookup"><span data-stu-id="779e1-118">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="779e1-119">Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="779e1-119">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="779e1-120">Considerazioni relative al sito centrale e al sito derivato</span><span class="sxs-lookup"><span data-stu-id="779e1-120">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="779e1-p105">I server Mediation Server nel sito centrale possono essere utilizzati per instradare le chiamate per IP-PBX o gateway PSTN nei siti derivati. Se tuttavia si distribuiscono trunk SIP, è necessario distribuire un server Mediation Server presso il sito in cui ogni trunk termina. Per fare in modo che un server Mediation Server nel sito centrale instradi le chiamate per un IP-PBX o un gateway PSTN in un sito derivato, non è necessario utilizzare Media Bypass. Se tuttavia è possibile abilitare Media Bypass, sarà possibile ridurre la latenza del percorso del contenuto multimediale e, di conseguenza, migliorare la qualità multimediale in quanto non sarà più necessario che il percorso del contenuto multimediale segua il percorso di segnalazione. Media Bypass consente inoltre di diminuire il carico di elaborazione nel pool.</span><span class="sxs-lookup"><span data-stu-id="779e1-p105">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites. If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates. Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass. However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path. Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="779e1-126">Il bypass multimediale non interagisce con ogni gateway PSTN, ogni IP-PBX e ogni SBC.</span><span class="sxs-lookup"><span data-stu-id="779e1-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="779e1-127">Microsoft ha testato una serie di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con i sistemi IP-PBX Cisco.</span><span class="sxs-lookup"><span data-stu-id="779e1-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="779e1-128">Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A> .</span><span class="sxs-lookup"><span data-stu-id="779e1-128">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="779e1-129">Se è necessaria la resilienza del sito derivato, è necessario distribuire nel sito derivato un Survivable Branch Appliance o una combinazione di Front End Server, Mediation Server e gateway.</span><span class="sxs-lookup"><span data-stu-id="779e1-129">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="779e1-130">(L'assunzione con resilienza del sito di succursale è che la presenza e la conferenza non sono resilienti nel sito). Per istruzioni sulla pianificazione dei siti di succursale per la voce, vedere [pianificazione della resilienza vocale del sito di succursale in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="779e1-130">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="779e1-131">Per le interazioni con un sistema IP-PBX, se il sistema IP-PBX non supporta correttamente le interazioni tra i media iniziali con più finestre di dialogo iniziali e le interazioni RFC 3960, è possibile che vengano ritagliate le prime parole del messaggio di saluto per le chiamate in arrivo dal sistema IP-PBX agli endpoint di Lync.</span><span class="sxs-lookup"><span data-stu-id="779e1-131">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="779e1-132">Questo comportamento può essere più grave se un server Mediation Server in un sito centrale instrada le chiamate per un sistema IP-PBX in cui la route termina in un sito derivato, in quanto è necessario più tempo per il completamento dei segnali.</span><span class="sxs-lookup"><span data-stu-id="779e1-132">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="779e1-133">Se si verifica questo comportamento, la distribuzione di un Mediation Server nel sito di succursale è l'unico modo per ridurre il ritaglio delle prime parole.</span><span class="sxs-lookup"><span data-stu-id="779e1-133">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="779e1-134">Infine, se nel sito centrale è presente un sistema PBX TDM o se il sistema IP-PBX richiede un gateway PSTN, è necessario distribuire un gateway nella route di chiamata che connette il server Mediation Server e il sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="779e1-134">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="779e1-135">Per migliorare le prestazioni dei supporti di Mediation Server autonomo, è necessario abilitare il formato RSS (Receive-Side Scaling) nelle schede di rete su questi server.</span><span class="sxs-lookup"><span data-stu-id="779e1-135">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="779e1-136">RSS consente la gestione parallela dei pacchetti in ingresso da parte di più processori del server.</span><span class="sxs-lookup"><span data-stu-id="779e1-136">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="779e1-137">Per informazioni dettagliate, vedere la sezione relativa ai miglioramenti della scala di ricezione in Windows Server all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A> .</span><span class="sxs-lookup"><span data-stu-id="779e1-137">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="779e1-138">Per informazioni dettagliate su come abilitare RSS, vedere la documentazione relativa alla scheda di rete.</span><span class="sxs-lookup"><span data-stu-id="779e1-138">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

