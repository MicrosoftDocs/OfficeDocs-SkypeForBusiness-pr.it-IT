---
title: 'Lync Server 2013: trunking SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0709bb6e837f536a2c034c239ee08c83f2b36e8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a><span data-ttu-id="2467e-102">Trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2467e-102">SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2467e-103">_**Ultimo argomento modificato:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="2467e-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="2467e-p101">Il protocollo SIP (Session Initiation Protocol) viene utilizzato per avviare e gestire sessioni di comunicazioni Voice over IP (VoIP) per servizi telefonici di base e per altri servizi di comunicazione in tempo reale, ad esempio messaggistica istantanea, conferenze, informazioni sulla presenza e sessioni multimediali. In questa sezione vengono fornite informazioni sulla pianificazione per l'implementazione di *trunk SIP*, un tipo di connessione SIP che si estende oltre i confini della rete locale.</span><span class="sxs-lookup"><span data-stu-id="2467e-p101">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia. This section provides planning information for implementing *SIP trunks*, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

<div>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="2467e-106">Cos'è il trunking SIP?</span><span class="sxs-lookup"><span data-stu-id="2467e-106">What is SIP Trunking?</span></span>

<span data-ttu-id="2467e-p102">Un trunk SIP è una connessione IP che consente di stabilire un collegamento di comunicazione SIP tra l'organizzazione e un provider di servizi di telefonia Internet (ITSP) oltre il firewall. In genere, un trunk SIP viene utilizzato per connettere il sito centrale dell'organizzazione a un ITSP. In alcuni casi, è anche possibile scegliere di utilizzare il trunking SIP per connettere un sito derivato a un ITSP.</span><span class="sxs-lookup"><span data-stu-id="2467e-p102">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall. Typically, a SIP trunk is used to connect your organization’s central site to an ITSP. In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="2467e-110">Confronto tra trunk SIP e connessioni SIP dirette</span><span class="sxs-lookup"><span data-stu-id="2467e-110">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="2467e-111">Il termine *trunk* deriva dalla tecnologia a commutazione di circuito.</span><span class="sxs-lookup"><span data-stu-id="2467e-111">The term *trunk* is derived from circuit-switched technology.</span></span> <span data-ttu-id="2467e-112">Si riferisce a una linea fisica dedicata che collega il dispositivo di commutazione telefonica.</span><span class="sxs-lookup"><span data-stu-id="2467e-112">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="2467e-113">Analogamente al predecessore, ai trunk TDM (Time Division Multiplexing), i trunk SIP sono connessioni tra due reti SIP separate, ovvero Lync Server 2013 Enterprise e ITSP.</span><span class="sxs-lookup"><span data-stu-id="2467e-113">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Lync Server 2013 enterprise and the ITSP.</span></span> <span data-ttu-id="2467e-114">A differenza dei trunk a commutazione di circuito, i trunk SIP sono connessioni virtuali che possono essere stabilite su qualsiasi tipo di connessione di trunking SIP supportato.</span><span class="sxs-lookup"><span data-stu-id="2467e-114">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span> <span data-ttu-id="2467e-115">Per informazioni dettagliate sui tipi di connessione supportati, vedere [come implementare il trunking SIP in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="2467e-115">For details about the supported connection types, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="2467e-116">Le connessioni SIP dirette sono invece connessioni SIP che non oltrepassano il confine di rete locale, ovvero si connettono a un gateway PSTN o un PBX nella rete interna.</span><span class="sxs-lookup"><span data-stu-id="2467e-116">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="2467e-117">Per informazioni dettagliate su come utilizzare le connessioni SIP dirette con Lync Server 2013, vedere [Direct SIP Connections in Lync server 2013](lync-server-2013-direct-sip-connections.md).</span><span class="sxs-lookup"><span data-stu-id="2467e-117">For details about how you can use direct SIP connections with Lync Server 2013, see [Direct SIP connections in Lync Server 2013](lync-server-2013-direct-sip-connections.md).</span></span>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2467e-118">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="2467e-118">In This Section</span></span>

  - [<span data-ttu-id="2467e-119">Panoramica del trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2467e-119">Overview of SIP trunking in Lync Server 2013</span></span>](lync-server-2013-overview-of-sip-trunking.md)

  - [<span data-ttu-id="2467e-120">Come implementare il trunking SIP in Lync Server 2013?</span><span class="sxs-lookup"><span data-stu-id="2467e-120">How do I implement SIP trunking in Lync Server 2013?</span></span>](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [<span data-ttu-id="2467e-121">Componenti e topologie per il trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2467e-121">Components and topologies for SIP trunking in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [<span data-ttu-id="2467e-122">Trunking SIP del sito di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2467e-122">Branch site SIP trunking in Lync Server 2013</span></span>](lync-server-2013-branch-site-sip-trunking.md)

  - [<span data-ttu-id="2467e-123">Elenco di controllo per la distribuzione del trunk SIP per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2467e-123">SIP trunk deployment checklist for Lync Server 2013</span></span>](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

