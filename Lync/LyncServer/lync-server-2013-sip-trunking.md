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
ms.openlocfilehash: d76907c1868e9fccb1a31e705c73807a8cbe501b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a><span data-ttu-id="77b18-102">Trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77b18-102">SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77b18-103">_**Argomento Ultima modifica:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="77b18-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="77b18-104">SIP (Session Initiation Protocol) viene usato per avviare e gestire sessioni di comunicazioni VoIP (Voice over IP) per il servizio telefonico di base e per servizi di comunicazione in tempo reale aggiuntivi, ad esempio messaggistica istantanea, conferenza, rilevamento presenza e multimediali.</span><span class="sxs-lookup"><span data-stu-id="77b18-104">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia.</span></span> <span data-ttu-id="77b18-105">Questa sezione fornisce informazioni sulla pianificazione per l'implementazione di *trunk SIP*, un tipo di connessione SIP che si estende oltre il limite della rete locale.</span><span class="sxs-lookup"><span data-stu-id="77b18-105">This section provides planning information for implementing *SIP trunks*, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

<div>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="77b18-106">Che cos'è il trunking SIP?</span><span class="sxs-lookup"><span data-stu-id="77b18-106">What is SIP Trunking?</span></span>

<span data-ttu-id="77b18-107">Un trunk SIP è una connessione IP che stabilisce un collegamento di comunicazioni SIP tra l'organizzazione e un provider di servizi di telefonia Internet (ITSP) oltre il firewall.</span><span class="sxs-lookup"><span data-stu-id="77b18-107">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall.</span></span> <span data-ttu-id="77b18-108">In genere, viene usato un trunk SIP per connettere il sito centrale dell'organizzazione a un ITSP.</span><span class="sxs-lookup"><span data-stu-id="77b18-108">Typically, a SIP trunk is used to connect your organization’s central site to an ITSP.</span></span> <span data-ttu-id="77b18-109">In alcuni casi, è anche possibile scegliere di usare il trunking SIP per connettere il sito di succursale a un ITSP.</span><span class="sxs-lookup"><span data-stu-id="77b18-109">In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="77b18-110">Trunk SIP e connessioni SIP dirette</span><span class="sxs-lookup"><span data-stu-id="77b18-110">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="77b18-111">Il termine *trunk* è derivato dalla tecnologia Circuit-Switched.</span><span class="sxs-lookup"><span data-stu-id="77b18-111">The term *trunk* is derived from circuit-switched technology.</span></span> <span data-ttu-id="77b18-112">Si riferisce a una linea fisica dedicata che connette il dispositivo di commutazione telefonica.</span><span class="sxs-lookup"><span data-stu-id="77b18-112">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="77b18-113">Come il predecessore, i trunk di Time Division Multiplexing (TDM), trunk SIP sono connessioni tra due reti SIP separate: Lync Server 2013 Enterprise e ITSP.</span><span class="sxs-lookup"><span data-stu-id="77b18-113">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Lync Server 2013 enterprise and the ITSP.</span></span> <span data-ttu-id="77b18-114">Diversamente dai trunk a scambio di circuiti, i trunk SIP sono connessioni virtuali che possono essere stabilite su uno dei tipi di connessione di trunking SIP supportati.</span><span class="sxs-lookup"><span data-stu-id="77b18-114">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span> <span data-ttu-id="77b18-115">Per informazioni dettagliate sui tipi di connessione supportati, vedere [come implementare il trunking SIP in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="77b18-115">For details about the supported connection types, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="77b18-116">Le connessioni SIP dirette, invece, sono connessioni SIP che non superano il limite di rete locale, ovvero si connettono a un gateway PSTN (Public Switched Telephone Network) o PBX (Private Branch Exchange) all'interno della rete interna.</span><span class="sxs-lookup"><span data-stu-id="77b18-116">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="77b18-117">Per informazioni dettagliate su come usare le connessioni SIP dirette con Lync Server 2013, vedere [connessioni SIP dirette in Lync server 2013](lync-server-2013-direct-sip-connections.md).</span><span class="sxs-lookup"><span data-stu-id="77b18-117">For details about how you can use direct SIP connections with Lync Server 2013, see [Direct SIP connections in Lync Server 2013](lync-server-2013-direct-sip-connections.md).</span></span>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="77b18-118">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="77b18-118">In This Section</span></span>

  - [<span data-ttu-id="77b18-119">Panoramica del trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77b18-119">Overview of SIP trunking in Lync Server 2013</span></span>](lync-server-2013-overview-of-sip-trunking.md)

  - [<span data-ttu-id="77b18-120">Come implementare il trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77b18-120">How do I implement SIP trunking in Lync Server 2013?</span></span>](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [<span data-ttu-id="77b18-121">Componenti e topologie per il trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77b18-121">Components and topologies for SIP trunking in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [<span data-ttu-id="77b18-122">Trunking SIP del sito della filiale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77b18-122">Branch site SIP trunking in Lync Server 2013</span></span>](lync-server-2013-branch-site-sip-trunking.md)

  - [<span data-ttu-id="77b18-123">Elenco di controllo di distribuzione per i trunk SIP per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77b18-123">SIP trunk deployment checklist for Lync Server 2013</span></span>](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

