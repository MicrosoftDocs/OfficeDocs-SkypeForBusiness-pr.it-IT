---
title: 'Lync Server 2013: componente Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1f3476f8b4e99b2abccb67f1d75446a126df03d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a><span data-ttu-id="b2e34-102">Componente Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2e34-102">Mediation Server component in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2e34-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b2e34-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="b2e34-104">È necessario distribuire Lync Server 2013, Mediation Server se si distribuisce il carico di lavoro VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="b2e34-104">You must deploy Lync Server 2013, Mediation Server if you deploy the Enterprise Voice workload.</span></span> <span data-ttu-id="b2e34-105">Questa sezione descrive le funzionalità di base, le dipendenze, le topologie base e le linee guida per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b2e34-105">This section describes basic functionality, dependencies, basic topologies, and planning guidelines.</span></span>

<span data-ttu-id="b2e34-106">Il Mediation Server traduce la segnalazione e, in alcune configurazioni, il supporto tra l'infrastruttura di Lync Server 2013, le infrastrutture VoIP aziendale e un gateway PSTN (Public Switched Telephone Network) o un trunk SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="b2e34-106">The Mediation Server translates signaling and, in some configurations, media between your internal Lync Server 2013, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="b2e34-107">Sul lato Lync Server 2013, Mediation Server è in ascolto su un unico indirizzo di trasporto Mutual TLS (MTLS).</span><span class="sxs-lookup"><span data-stu-id="b2e34-107">On the Lync Server 2013 side, Mediation Server listens on a single mutual TLS (MTLS) transport address.</span></span> <span data-ttu-id="b2e34-108">Sul lato del gateway, Mediation Server è in ascolto su tutte le porte di ascolto associate associate ai trunk definiti nel documento di topologia.</span><span class="sxs-lookup"><span data-stu-id="b2e34-108">On the gateway side, Mediation Server listens on all associated listening ports associated with trunks defined in the Topology document.</span></span> <span data-ttu-id="b2e34-109">Tutti i gateway qualificati devono supportare TLS, ma possono abilitare anche TCP.</span><span class="sxs-lookup"><span data-stu-id="b2e34-109">All qualified gateways must support TLS, but can enable TCP as well.</span></span> <span data-ttu-id="b2e34-110">TCP è supportato per i gateway che non supportano TLS.</span><span class="sxs-lookup"><span data-stu-id="b2e34-110">TCP is supported for gateways that do not support TLS.</span></span>

<span data-ttu-id="b2e34-111">Se si ha anche un PBX (Public Branch Exchange) esistente nell'ambiente, Mediation Server gestisce le chiamate tra gli utenti di VoIP aziendale e il PBX.</span><span class="sxs-lookup"><span data-stu-id="b2e34-111">If you also have an existing Public Branch Exchange (PBX) in your environment, Mediation Server handles calls between Enterprise Voice users and the PBX.</span></span> <span data-ttu-id="b2e34-112">Se il PBX è un IP-PBX, è possibile creare una connessione SIP diretta tra il PBX e il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="b2e34-112">If your PBX is an IP-PBX, you can create a direct SIP connection between the PBX and Mediation Server.</span></span> <span data-ttu-id="b2e34-113">Se il PBX è un PBX TDM (Time Division Multiplex), è necessario distribuire anche un gateway PSTN tra Mediation Server e il PBX.</span><span class="sxs-lookup"><span data-stu-id="b2e34-113">If your PBX is a Time Division Multiplex (TDM) PBX, you must also deploy a PSTN gateway between Mediation Server and the PBX.</span></span>

<span data-ttu-id="b2e34-114">Il Mediation Server è collocato con il front end server per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b2e34-114">The Mediation Server is collocated with the Front End Server by default.</span></span> <span data-ttu-id="b2e34-115">Il Mediation Server può essere distribuito anche in un pool autonomo per motivi di prestazioni oppure se si distribuisce il trunking SIP, in questo caso è consigliabile usare il pool autonomo.</span><span class="sxs-lookup"><span data-stu-id="b2e34-115">The Mediation Server can also be deployed in a stand-alone pool for performance reasons, or if you deploy SIP trunking, in which case the stand-alone pool is strongly recommended.</span></span>

<span data-ttu-id="b2e34-116">Se si distribuiscono connessioni SIP dirette a un gateway PSTN qualificato che supporta il bypass multimediale e il bilanciamento del carico DNS, non è necessario disporre di un pool di Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="b2e34-116">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="b2e34-117">Un pool di Mediation Server autonomo non è necessario perché i gateway qualificati sono in grado di bilanciamento del carico DNS in un pool di server di mediazione e possono ricevere traffico da qualsiasi Mediation Server in un pool.</span><span class="sxs-lookup"><span data-stu-id="b2e34-117">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="b2e34-118">È anche consigliabile collocare il Mediation Server in un pool Front-end quando si sono distribuiti IP-PBX o connettersi a un SBC (Session Border Controller) di un provider di telefonia Internet, purché siano soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2e34-118">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="b2e34-119">IP-PBX o SBC è configurato per ricevere il traffico da qualsiasi Mediation Server nel pool e può instradare il traffico uniformemente a tutti i server di mediazione nel pool.</span><span class="sxs-lookup"><span data-stu-id="b2e34-119">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="b2e34-120">IP-PBX non supporta il bypass multimediale, ma il pool Front-end che ospita il Mediation Server può gestire la transcodifica vocale per le chiamate a cui il bypass multimediale non si applica.</span><span class="sxs-lookup"><span data-stu-id="b2e34-120">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="b2e34-121">È possibile usare Microsoft Lync Server 2013, strumento di pianificazione per valutare se il pool di front end in cui si vuole collocare il Mediation Server può gestire il carico.</span><span class="sxs-lookup"><span data-stu-id="b2e34-121">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="b2e34-122">Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="b2e34-122">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="b2e34-123">Di seguito sono riportate le funzioni principali di Mediation Server:</span><span class="sxs-lookup"><span data-stu-id="b2e34-123">The main functions of the Mediation Server are as follows:</span></span>

  - <span data-ttu-id="b2e34-124">Crittografia e decrittografia di SRTP sul lato server Lync</span><span class="sxs-lookup"><span data-stu-id="b2e34-124">Encrypting and decrypting SRTP on the Lync Server side</span></span>

  - <span data-ttu-id="b2e34-125">Traduzione di SIP su TCP (per i gateway che non supportano TLS) per il SIP tramite Mutual TLS</span><span class="sxs-lookup"><span data-stu-id="b2e34-125">Translating SIP over TCP (for gateways that do not support TLS) to SIP over mutual TLS</span></span>

  - <span data-ttu-id="b2e34-126">Traduzione di flussi multimediali tra Lync Server e il peer del gateway del Mediation Server</span><span class="sxs-lookup"><span data-stu-id="b2e34-126">Translating media streams between Lync Server and the gateway peer of the Mediation Server</span></span>

  - <span data-ttu-id="b2e34-127">Connettere i client esterni alla rete ai componenti ICE interni, che consentono l'attraversamento multimediale di NAT e firewall</span><span class="sxs-lookup"><span data-stu-id="b2e34-127">Connecting clients that are outside the network to internal ICE components, which enable media traversal of NAT and firewalls</span></span>

  - <span data-ttu-id="b2e34-128">Fungendo da intermediario per i flussi di chiamata non supportati da un gateway, ad esempio le chiamate di operatori remoti in un client VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="b2e34-128">Acting as an intermediary for call flows that a gateway does not support, such as calls from remote workers on an Enterprise Voice client</span></span>

  - <span data-ttu-id="b2e34-129">Nelle distribuzioni che includono il trunking SIP, che collabora con il provider di servizi di trunking SIP per ottenere il supporto PSTN, che elimina la necessità di un gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="b2e34-129">In deployments that include SIP trunking, working with the SIP trunking service provider to provide PSTN support, which eliminates the need for a PSTN gateway</span></span>

<span data-ttu-id="b2e34-130">Nella figura seguente vengono illustrati i protocolli di segnalazione e multimediali usati dal Mediation Server quando si comunica con un gateway PSTN di base e con l'infrastruttura VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="b2e34-130">The following figure shows the signaling and media protocols that are used by the Mediation Server when communicating with a basic PSTN gateway and the Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="b2e34-131">**Segnalazioni e protocolli multimediali usati dal Mediation Server**</span><span class="sxs-lookup"><span data-stu-id="b2e34-131">**Signaling and media protocols used by the Mediation Server**</span></span>

<span data-ttu-id="b2e34-132">(images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Diagramma") protocolli Mediation ![Server Protocols]</span><span class="sxs-lookup"><span data-stu-id="b2e34-132">![Mediation Server Protocols diagram](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Mediation Server Protocols diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b2e34-133">Se si usa TCP o RTP/RTCP (invece di SRTP o SRTCP) nella rete tra il gateway PSTN e il Mediation Server, è consigliabile adottare misure per garantire la sicurezza e la privacy della rete.</span><span class="sxs-lookup"><span data-stu-id="b2e34-133">If you are using TCP or RTP/RTCP (instead of SRTP or SRTCP) on the network between the PSTN gateway and the Mediation Server, we recommend that you take measures to help ensure the security and privacy of the network.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b2e34-134">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b2e34-134">In This Section</span></span>

  - [<span data-ttu-id="b2e34-135">Trunk M:N in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2e34-135">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="b2e34-136">Controllo di ammissione di chiamata e Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2e34-136">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [<span data-ttu-id="b2e34-137">Servizi di emergenza avanzati e Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2e34-137">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [<span data-ttu-id="b2e34-138">Bypass multimediale e Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2e34-138">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)

  - [<span data-ttu-id="b2e34-139">Componenti e topologie per Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2e34-139">Components and topologies for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [<span data-ttu-id="b2e34-140">Linee guida per la distribuzione di Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2e34-140">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

