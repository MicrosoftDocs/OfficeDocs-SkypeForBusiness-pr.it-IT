---
title: 'Lync Server 2013: controllo di ammissione di chiamata in una rete MPLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control on an MPLS network
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48183387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee138a0f61bace067db12c9df4f06338aa13ac8b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-an-mpls-network-with-lync-server-2013"></a><span data-ttu-id="6b08a-102">Controllo di ammissione alle chiamate in una rete MPLS con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b08a-102">Call admission control on an MPLS network with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b08a-103">_**Argomento Ultima modifica:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="6b08a-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="6b08a-104">In una rete di commutazione di etichette Multiprotocol (MPLS), tutti i siti sono connessi da una mesh completa.</span><span class="sxs-lookup"><span data-stu-id="6b08a-104">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh.</span></span> <span data-ttu-id="6b08a-105">Ossia, tutti i siti sono connessi direttamente alla backbone MPLS del provider di servizi Internet e ogni sito è il provisioning della larghezza di banda da usare in un collegamento WAN al cloud MPLS.</span><span class="sxs-lookup"><span data-stu-id="6b08a-105">That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud.</span></span> <span data-ttu-id="6b08a-106">Non esiste un hub di rete o un sito centrale per controllare il routing IP.</span><span class="sxs-lookup"><span data-stu-id="6b08a-106">There is no network hub or central site to control IP routing.</span></span> <span data-ttu-id="6b08a-107">La figura seguente mostra una rete semplice basata sulla tecnologia MPLS.</span><span class="sxs-lookup"><span data-stu-id="6b08a-107">The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="6b08a-108">**Esempio di rete MPLS**</span><span class="sxs-lookup"><span data-stu-id="6b08a-108">**Example MPLS network**</span></span>

<span data-ttu-id="6b08a-109">![CAC con MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC con MPLS")</span><span class="sxs-lookup"><span data-stu-id="6b08a-109">![CAC with MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC with MPLS")</span></span>

<span data-ttu-id="6b08a-110">Per distribuire il controllo di ammissione di chiamata (CAC) in una rete MPLS, è possibile creare un'area di rete per rappresentare il cloud MPLS e creare un sito di rete per rappresentare ogni sito satellite MPLS.</span><span class="sxs-lookup"><span data-stu-id="6b08a-110">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site.</span></span> <span data-ttu-id="6b08a-111">Nella figura seguente viene illustrato il modo in cui i siti della rete e della rete devono essere configurati per rappresentare la rete MPLS di esempio nella figura precedente.</span><span class="sxs-lookup"><span data-stu-id="6b08a-111">The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure.</span></span> <span data-ttu-id="6b08a-112">I limiti generali della larghezza di banda e i limiti della sessione di larghezza di banda si basano sulla capacità del collegamento WAN da ogni sito di rete all'area di rete che rappresenta il cloud MPLS.</span><span class="sxs-lookup"><span data-stu-id="6b08a-112">The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="6b08a-113">**Area geografica e siti di rete per una rete MPLS**</span><span class="sxs-lookup"><span data-stu-id="6b08a-113">**Network region and network sites for an MPLS network**</span></span>

<span data-ttu-id="6b08a-114">![Controllo di ammissione alle chiamate (CAC) con]il controllo di ammissione al diagramma MPLS(images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "(CAC) con il diagramma MPLS")</span><span class="sxs-lookup"><span data-stu-id="6b08a-114">![Call Admission Control (CAC) with MPLS diagram](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Call Admission Control (CAC) with MPLS diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

