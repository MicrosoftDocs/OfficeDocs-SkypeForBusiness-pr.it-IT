---
title: 'Lync Server 2013: Componenti e topologie per Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62516645266f67b7be61154b45afd00107ec3814
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="af488-102">Componenti e topologie per Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af488-102">Components and topologies for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af488-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="af488-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="af488-104">In questo argomento vengono descritti i componenti in cui è dipendente il Mediation Server e le topologie in cui è possibile distribuire il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="af488-104">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="af488-105">Dipendenze</span><span class="sxs-lookup"><span data-stu-id="af488-105">Dependencies</span></span>

<span data-ttu-id="af488-106">Il Mediation Server ha le dipendenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="af488-106">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="af488-107">**Registrar.**</span><span class="sxs-lookup"><span data-stu-id="af488-107">**Registrar.**</span></span> <span data-ttu-id="af488-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="af488-108">Required.</span></span> <span data-ttu-id="af488-109">Il registrar è l'hop successivo per la segnalazione nelle interazioni di Mediation Server con la rete Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af488-109">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="af488-110">Si noti che Mediation Server può essere collocato in un server front-end insieme al registrar, oltre ad essere installato in un pool autonomo costituito solo da server di mediazione.</span><span class="sxs-lookup"><span data-stu-id="af488-110">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="af488-111">Il registrar è collocato con un Mediation Server e un gateway PSTN in un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="af488-111">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="af488-112">**Server di monitoraggio.**</span><span class="sxs-lookup"><span data-stu-id="af488-112">**Monitoring Server.**</span></span> <span data-ttu-id="af488-113">Facoltativo, ma altamente raccomandato.</span><span class="sxs-lookup"><span data-stu-id="af488-113">Optional but highly recommended.</span></span> <span data-ttu-id="af488-114">Il server di monitoraggio consente al Mediation Server di registrare le metriche di qualità associate alle proprie sessioni multimediali.</span><span class="sxs-lookup"><span data-stu-id="af488-114">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="af488-115">**Edge Server.**</span><span class="sxs-lookup"><span data-stu-id="af488-115">**Edge Server.**</span></span> <span data-ttu-id="af488-116">Obbligatorio per il supporto degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="af488-116">Required for external user support.</span></span> <span data-ttu-id="af488-117">Il server perimetrale consente al Mediation Server di interagire con gli utenti che si trovano dietro un NAT o un firewall.</span><span class="sxs-lookup"><span data-stu-id="af488-117">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="af488-118">Tecnologie</span><span class="sxs-lookup"><span data-stu-id="af488-118">Topologies</span></span>

<span data-ttu-id="af488-119">Lync Server 2013, Mediation Server è collocato per impostazione predefinita con un'istanza del registrar in un server Standard Edition, un pool Front end o un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="af488-119">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="af488-120">Tutti i Mediation Server in un pool Front-end devono essere configurati in modo identico.</span><span class="sxs-lookup"><span data-stu-id="af488-120">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="af488-121">In caso di problemi di prestazioni, può essere preferibile distribuire uno o più server di mediazione in un pool autonomo dedicato.</span><span class="sxs-lookup"><span data-stu-id="af488-121">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="af488-122">In alternativa, se si distribuisce il trunking SIP, è consigliabile distribuire un pool di Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="af488-122">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="af488-123">Se si distribuiscono connessioni SIP dirette a un gateway PSTN qualificato che supporta il bypass multimediale e il bilanciamento del carico DNS, non è necessario disporre di un pool di Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="af488-123">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="af488-124">Un pool di Mediation Server autonomo non è necessario perché i gateway qualificati sono in grado di bilanciamento del carico DNS in un pool di server di mediazione e possono ricevere traffico da qualsiasi Mediation Server in un pool.</span><span class="sxs-lookup"><span data-stu-id="af488-124">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="af488-125">È anche consigliabile collocare il Mediation Server in un pool Front-end quando si sono distribuiti IP-PBX o connettersi a un SBC (Session Border Controller) di un provider di telefonia Internet, purché siano soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="af488-125">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="af488-126">IP-PBX o SBC è configurato per ricevere il traffico da qualsiasi Mediation Server nel pool e può instradare il traffico uniformemente a tutti i server di mediazione nel pool.</span><span class="sxs-lookup"><span data-stu-id="af488-126">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="af488-127">IP-PBX non supporta il bypass multimediale, ma il pool Front-end che ospita il Mediation Server può gestire la transcodifica vocale per le chiamate a cui il bypass multimediale non si applica.</span><span class="sxs-lookup"><span data-stu-id="af488-127">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="af488-128">È possibile usare Microsoft Lync Server 2013, strumento di pianificazione per valutare se il pool di front end in cui si vuole collocare il Mediation Server può gestire il carico.</span><span class="sxs-lookup"><span data-stu-id="af488-128">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="af488-129">Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="af488-129">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="af488-130">Per informazioni dettagliate sulla topologia da distribuire, vedere [linee guida per la distribuzione di Mediation Server in Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="af488-130">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="af488-131">La figura seguente mostra una semplice topologia costituita da due siti collegati da un collegamento WAN.</span><span class="sxs-lookup"><span data-stu-id="af488-131">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="af488-132">Mediation Server è collocato con il registrar in un pool Front-End nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="af488-132">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="af488-133">I Mediation Server del sito 1 controllano sia il gateway PSTN sul sito 1 che il gateway nel sito 2.</span><span class="sxs-lookup"><span data-stu-id="af488-133">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="af488-134">In questa topologia, il bypass multimediale è abilitato globalmente per l'uso delle informazioni sul sito e le aree geografiche e i trunk per ogni gateway PSTN (GW1 e GW2) hanno un bypass abilitato.</span><span class="sxs-lookup"><span data-stu-id="af488-134">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="af488-135">**Esempio di siti collegati da un collegamento WAN a un Mediation Server presso il sito 1 e un gateway PSTN sul sito 2**</span><span class="sxs-lookup"><span data-stu-id="af488-135">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="af488-136">![Topologia vocale con Mediation Server e gateway WAN](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Topologia vocale con Mediation Server e gateway WAN")</span><span class="sxs-lookup"><span data-stu-id="af488-136">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="af488-137">Nella figura seguente è illustrata una semplice topologia in cui il Mediation Server è collocato con il registrar nel pool Front-end del sito 1 ed è collegato direttamente al protocollo IP-PBX nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="af488-137">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="af488-138">In questa figura il Mediation Server controlla anche un gateway PSTN sul sito 2.</span><span class="sxs-lookup"><span data-stu-id="af488-138">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="af488-139">Supponiamo che gli utenti di Lync esistano in entrambi i siti 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="af488-139">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="af488-140">Si supponga inoltre che IP-PBX disponga di un processore multimediale associato che deve essere attraversato da tutti gli elementi multimediali provenienti da endpoint di Lync prima di essere inviati agli endpoint multimediali controllati da IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="af488-140">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="af488-141">In questa topologia, il bypass multimediale è abilitato globalmente per l'uso di informazioni sul sito e le aree geografiche e i Trunks per il PBX e il gateway PSTN sono abilitati per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="af488-141">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="af488-142">**Esempio di siti collegati da un collegamento WAN con un Mediation Server presso il sito 1 e un PBX presso il sito 2**</span><span class="sxs-lookup"><span data-stu-id="af488-142">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="af488-143">![Topologia vocale con Mediation Server e PBX WAN](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Topologia vocale con Mediation Server e PBX WAN")</span><span class="sxs-lookup"><span data-stu-id="af488-143">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="af488-144">Per informazioni dettagliate sulla pianificazione delle topologie PBX, vedere [linee guida per la distribuzione di Mediation Server in Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) e [Opzioni di distribuzione SIP dirette in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span><span class="sxs-lookup"><span data-stu-id="af488-144">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="af488-145">L'ultima figura in questo argomento Mostra una topologia in cui il Mediation Server è connesso all'SBC di un provider di servizi di telefonia Internet.</span><span class="sxs-lookup"><span data-stu-id="af488-145">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="af488-146">Per informazioni dettagliate sulle topologie trunk SIP, vedere [trunking SIP in Lync Server 2013](lync-server-2013-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="af488-146">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

