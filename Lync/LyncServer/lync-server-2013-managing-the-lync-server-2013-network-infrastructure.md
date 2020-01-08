---
title: "Lync Server 2013: Gestione dell'infrastruttura di rete di Lync Server 2013"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Lync Server 2013 network infrastructure
ms:assetid: cb13456a-8f66-4595-be21-8887f30ad4eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182585(v=OCS.15)
ms:contentKeyID: 48185638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bd95ac0259e86f3ac8fd39a09276bffa88cfc75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="c9ba4-102">Gestione dell'infrastruttura di rete di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9ba4-102">Managing the Lync Server 2013 network infrastructure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9ba4-103">_**Argomento Ultima modifica:** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="c9ba4-103">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="c9ba4-104">Microsoft Lync Server 2013 include il supporto per il controllo di ammissione alle chiamate (CAC) e il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="c9ba4-104">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="c9ba4-105">Per implementare queste funzionalità, è necessario configurare una rete di aree geografiche, siti, subnet e così via che consentano di gestire la larghezza di banda in situazioni in cui le trasmissioni audio e video devono essere limitate.</span><span class="sxs-lookup"><span data-stu-id="c9ba4-105">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="c9ba4-106">È anche possibile usare la tecnologia di rete QoS (Quality of Service) per fornire un'esperienza ottimale per l'utente finale per le comunicazioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="c9ba4-106">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="c9ba4-107">È possibile usare il pannello di controllo di Lync Server per configurare e gestire CAC, bypass multimediale e QoS.</span><span class="sxs-lookup"><span data-stu-id="c9ba4-107">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="c9ba4-108">Gli argomenti seguenti includono la procedura per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="c9ba4-108">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c9ba4-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c9ba4-109">In This Section</span></span>

  - [<span data-ttu-id="c9ba4-110">Gestione della qualità del servizio (QoS) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9ba4-110">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="c9ba4-111">Gestione del controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9ba4-111">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="c9ba4-112">Interfacce di rete di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9ba4-112">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="c9ba4-113">Impedire le nuove connessioni a Lync Server 2013 per la manutenzione del server</span><span class="sxs-lookup"><span data-stu-id="c9ba4-113">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="c9ba4-114">Metodologia di qualità delle chiamate di Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9ba4-114">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="c9ba4-115">Indicatori di integrità chiave in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9ba4-115">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

