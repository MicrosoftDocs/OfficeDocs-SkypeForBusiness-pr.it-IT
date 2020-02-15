---
title: 'Lync Server 2013: controllo di ammissione di chiamata su una rete MPLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on an MPLS network
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48183387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8da29eb8825154f3e149d56b6bd9e4c4e7452652
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-an-mpls-network-with-lync-server-2013"></a><span data-ttu-id="c70c7-102">Controllo di ammissione di chiamata su una rete MPLS con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c70c7-102">Call admission control on an MPLS network with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c70c7-103">_**Ultimo argomento modificato:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="c70c7-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="c70c7-p101">In una rete MPLS (Multiprotocol Label Switching) tutti i siti sono connessi tramite full mesh, ovvero tutti i siti sono connessi direttamente alla dorsale MPLS del provider di servizi Internet e a ogni sito viene assegnata una larghezza di banda da utilizzare nel cloud MPLS attraverso un collegamento WAN. Non è presente alcun hub di rete o sito centrale per controllare il routing IP. Nella figura seguente viene illustrata una rete semplice basata sulla tecnologia MPLS.</span><span class="sxs-lookup"><span data-stu-id="c70c7-p101">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="c70c7-108">**Rete MPLS di esempio**</span><span class="sxs-lookup"><span data-stu-id="c70c7-108">**Example MPLS network**</span></span>

<span data-ttu-id="c70c7-109">![CAC con MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC con MPLS")</span><span class="sxs-lookup"><span data-stu-id="c70c7-109">![CAC with MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC with MPLS")</span></span>

<span data-ttu-id="c70c7-p102">Per distribuire il controllo di ammissione di chiamata in una rete MPLS, è necessario creare un'area di rete che rappresenti il cloud MPLS e un sito di rete che rappresenti ogni sito satellite MPLS. Nella figura seguente viene illustrato come è consigliabile configurare l'area di rete e i siti di rete per rappresentare la rete MPLS di esempio della figura precedente. I limiti di larghezza di banda totali e quelli di sessione sono quindi basati sulla capacità del collegamento WAN che va da ogni sito di rete all'area di rete che rappresenta il cloud MPLS.</span><span class="sxs-lookup"><span data-stu-id="c70c7-p102">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="c70c7-113">**Area di rete e siti di rete per una rete MPLS**</span><span class="sxs-lookup"><span data-stu-id="c70c7-113">**Network region and network sites for an MPLS network**</span></span>

<span data-ttu-id="c70c7-114">![Controllo di ammissione di chiamata (CAC) con diagramma MPLS](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Controllo di ammissione di chiamata (CAC) con diagramma MPLS")</span><span class="sxs-lookup"><span data-stu-id="c70c7-114">![Call Admission Control (CAC) with MPLS diagram](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Call Admission Control (CAC) with MPLS diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

