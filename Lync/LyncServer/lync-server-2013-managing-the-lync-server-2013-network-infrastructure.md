---
title: "Lync Server 2013: gestione dell'infrastruttura di rete di Lync Server 2013"
description: "Lync Server 2013: gestione dell'infrastruttura di rete di Lync Server 2013."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Lync Server 2013 network infrastructure
ms:assetid: cb13456a-8f66-4595-be21-8887f30ad4eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182585(v=OCS.15)
ms:contentKeyID: 48185638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab1b5c6fe52374b012063ac26640e9bb25496ad7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564102"
---
# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="fd0e3-103">Gestione dell'infrastruttura di rete di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd0e3-103">Managing the Lync Server 2013 network infrastructure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd0e3-104">_**Ultimo argomento modificato:** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="fd0e3-104">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="fd0e3-105">Microsoft Lync Server 2013 include il supporto per il controllo di ammissione di chiamata (CAC) e il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-105">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="fd0e3-106">Per implementare queste funzionalità, è necessario configurare una rete di aree, siti, subnet e così via che consentirà di gestire la larghezza di banda in situazioni in cui le trasmissioni audio e video devono essere limitate.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-106">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="fd0e3-107">È inoltre possibile utilizzare la tecnologia di rete Qualità del servizio (QoS) per fornire un'esperienza utente finale ottimale per le comunicazioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-107">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="fd0e3-108">È possibile utilizzare il pannello di controllo di Lync Server per configurare e gestire CAC, bypass multimediale e QoS.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-108">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="fd0e3-109">Negli argomenti elencati di seguito vengono descritte le procedure correlate.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-109">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fd0e3-110">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="fd0e3-110">In This Section</span></span>

  - [<span data-ttu-id="fd0e3-111">Gestione della qualità del servizio (QoS) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd0e3-111">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="fd0e3-112">Gestione del controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd0e3-112">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="fd0e3-113">Interfacce di rete di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd0e3-113">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="fd0e3-114">Impedire nuove connessioni a Lync Server 2013 per la manutenzione del server</span><span class="sxs-lookup"><span data-stu-id="fd0e3-114">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="fd0e3-115">Metodologia della qualità delle chiamate di Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd0e3-115">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="fd0e3-116">Indicatori di integrità chiave in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd0e3-116">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

