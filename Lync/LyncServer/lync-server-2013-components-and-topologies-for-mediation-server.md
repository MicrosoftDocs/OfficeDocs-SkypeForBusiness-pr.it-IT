---
title: 'Lync Server 2013: componenti e topologie per Mediation Server'
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
ms.openlocfilehash: a1b6c824da8eccaec0cb48450b0d81dddcc60f99
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="dd0af-102">Componenti e topologie per Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd0af-102">Components and topologies for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd0af-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="dd0af-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="dd0af-104">In questo argomento vengono descritti i componenti in base ai quali il Mediation Server è dipendente e le topologie in cui è possibile distribuire Mediation Server</span><span class="sxs-lookup"><span data-stu-id="dd0af-104">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="dd0af-105">Dipendenze</span><span class="sxs-lookup"><span data-stu-id="dd0af-105">Dependencies</span></span>

<span data-ttu-id="dd0af-106">Il Mediation Server presenta le dipendenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd0af-106">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="dd0af-107">**Registrar.**</span><span class="sxs-lookup"><span data-stu-id="dd0af-107">**Registrar.**</span></span> <span data-ttu-id="dd0af-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dd0af-108">Required.</span></span> <span data-ttu-id="dd0af-109">Il servizio di registrazione è l'hop successivo per la segnalazione nelle interazioni di Mediation Server con la rete Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd0af-109">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="dd0af-110">Si noti che Mediation Server può essere collocato in un front end server insieme al registrar, oltre ad essere installato in un pool autonomo costituito da solo Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="dd0af-110">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="dd0af-111">Il servizio di registrazione è collocato con un Mediation Server e un gateway PSTN in un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="dd0af-111">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="dd0af-112">**Monitoring Server.**</span><span class="sxs-lookup"><span data-stu-id="dd0af-112">**Monitoring Server.**</span></span> <span data-ttu-id="dd0af-113">Facoltativo ma consigliato.</span><span class="sxs-lookup"><span data-stu-id="dd0af-113">Optional but highly recommended.</span></span> <span data-ttu-id="dd0af-114">Il Monitoring Server consente al Mediation Server di registrare le metriche di qualità associate alle sessioni multimediali.</span><span class="sxs-lookup"><span data-stu-id="dd0af-114">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="dd0af-115">**Edge server (Server perimetrale).**</span><span class="sxs-lookup"><span data-stu-id="dd0af-115">**Edge Server.**</span></span> <span data-ttu-id="dd0af-116">Obbligatorio per il supporto degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="dd0af-116">Required for external user support.</span></span> <span data-ttu-id="dd0af-117">Il server perimetrale consente al Mediation Server di interagire con gli utenti che si trovano dietro un NAT o un firewall.</span><span class="sxs-lookup"><span data-stu-id="dd0af-117">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="dd0af-118">Topologie</span><span class="sxs-lookup"><span data-stu-id="dd0af-118">Topologies</span></span>

<span data-ttu-id="dd0af-119">Lync Server 2013, Mediation Server è collocato per impostazione predefinita con un'istanza del servizio di registrazione in un server Standard Edition, in un pool Front end o in un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="dd0af-119">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="dd0af-120">Tutti i Mediation Server in un pool Front end devono essere configurati in modo identico.</span><span class="sxs-lookup"><span data-stu-id="dd0af-120">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="dd0af-121">Se le prestazioni sono un problema, potrebbe essere preferibile distribuire uno o più Mediation Server in un pool autonomo dedicato.</span><span class="sxs-lookup"><span data-stu-id="dd0af-121">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="dd0af-122">In alternativa, se si sta distribuendo il trunking SIP, è consigliabile distribuire un pool Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="dd0af-122">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="dd0af-123">Se si distribuiscono connessioni SIP dirette a un gateway PSTN qualificato che supporta il bypass multimediale e il bilanciamento del carico DNS, non è necessario disporre di un pool Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="dd0af-123">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="dd0af-124">Ciò è dovuto al fatto che i gateway qualificati possono effettuare il bilanciamento del carico DNS in un pool di Mediation Server e ricevere traffico da qualsiasi Mediation Server di un pool.</span><span class="sxs-lookup"><span data-stu-id="dd0af-124">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="dd0af-125">È inoltre consigliabile collocare il Mediation Server in un pool Front End se sono stati distribuiti sistemi IP-PBX o si effettua la connessione al Session Border Controller (SBC) di un provider di servizi di telefonia Internet, purché vengano soddisfatte una o più delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd0af-125">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="dd0af-126">Il sistema IP-PBX o SBC è configurato per la ricezione di traffico da qualsiasi server Mediation Server nel pool e può eseguire il routing del traffico in modo uniforme a tutti i server Mediation Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="dd0af-126">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="dd0af-127">Il sistema IP-PBX non supporta il bypass multimediale, ma il pool Front end che ospita il Mediation Server è in grado di gestire la transcodifica vocale per le chiamate a cui non si applica il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="dd0af-127">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="dd0af-128">È possibile utilizzare Microsoft Lync Server 2013, strumento di pianificazione per valutare se il pool Front end in cui si desidera collocare il Mediation Server è in grado di gestire il carico.</span><span class="sxs-lookup"><span data-stu-id="dd0af-128">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="dd0af-129">Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="dd0af-129">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="dd0af-130">Per informazioni dettagliate sulla distribuzione della topologia, vedere [Deployment Guidelines for Mediation Server in Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="dd0af-130">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="dd0af-131">Nella figura seguente viene illustrata una semplice topologia costituita da due siti connessi tramite un collegamento WAN.</span><span class="sxs-lookup"><span data-stu-id="dd0af-131">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="dd0af-132">Mediation Server è collocato con il servizio di registrazione in un pool Front End nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="dd0af-132">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="dd0af-133">I Mediation Server nel sito 1 controllano sia il gateway PSTN nel sito 1 che il gateway nel sito 2.</span><span class="sxs-lookup"><span data-stu-id="dd0af-133">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="dd0af-134">In questa topologia il bypass multimediale è abilitato a livello globale per utilizzare informazioni su siti e aree ed è abilitato anche per i trunk a ogni gateway PSTN (GW1 e GW2).</span><span class="sxs-lookup"><span data-stu-id="dd0af-134">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="dd0af-135">**Esempio di siti connessi tramite un collegamento WAN a un server Mediation Server nel sito 1 e a un gateway PSTN nel sito 2**</span><span class="sxs-lookup"><span data-stu-id="dd0af-135">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="dd0af-136">![Topologia vocale con gateway WAN Mediation Server](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Topologia vocale con gateway WAN Mediation Server")</span><span class="sxs-lookup"><span data-stu-id="dd0af-136">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="dd0af-137">Nella figura seguente viene illustrata una topologia semplice in cui il Mediation Server è collocato con il servizio di registrazione nel pool Front end del sito 1 e dispone di una connessione SIP diretta al sistema IP-PBX nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="dd0af-137">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="dd0af-138">In questa figura, Mediation Server controlla anche un gateway PSTN nel sito 2.</span><span class="sxs-lookup"><span data-stu-id="dd0af-138">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="dd0af-139">Si supponga che gli utenti di Lync esistano in entrambi i siti 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="dd0af-139">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="dd0af-140">Si supponga inoltre che il sistema IP-PBX disponga di un processore multimediale associato che deve essere attraversato da tutti i supporti provenienti da endpoint di Lync prima di essere inviati agli endpoint multimediali controllati dall'IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="dd0af-140">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="dd0af-141">In questa topologia, il bypass multimediale è abilitato a livello globale per l'utilizzo delle informazioni relative a siti e aree geografiche, mentre i trunk del PBX e del gateway PSTN dispongono del bypass multimediale abilitato.</span><span class="sxs-lookup"><span data-stu-id="dd0af-141">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="dd0af-142">**Esempio di siti connessi tramite un collegamento WAN a un server Mediation Server nel sito 1 e a un sistema PBX nel sito 2**</span><span class="sxs-lookup"><span data-stu-id="dd0af-142">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="dd0af-143">![Topologia vocale Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Topologia vocale Mediation Server WAN PBX")</span><span class="sxs-lookup"><span data-stu-id="dd0af-143">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="dd0af-144">Per informazioni dettagliate sulla pianificazione delle topologie PBX, vedere [Deployment Guidelines for Mediation Server in Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) e [Direct SIP Deployment Options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span><span class="sxs-lookup"><span data-stu-id="dd0af-144">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="dd0af-145">Nell'ultima figura di questo argomento viene illustrata una topologia in cui Mediation Server è connesso all'SBC di un provider di servizi di telefonia Internet.</span><span class="sxs-lookup"><span data-stu-id="dd0af-145">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="dd0af-146">Per informazioni dettagliate sulle topologie trunk SIP, vedere [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="dd0af-146">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

