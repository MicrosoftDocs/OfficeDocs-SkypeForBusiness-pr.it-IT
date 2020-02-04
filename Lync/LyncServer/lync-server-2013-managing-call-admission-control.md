---
title: 'Lync Server 2013: gestione del controllo di ammissione alle chiamate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing call admission control
ms:assetid: b0bd4783-6f47-408d-b010-2e30f9bc1770
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721851(v=OCS.15)
ms:contentKeyID: 49733784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11cd9e2bb894f5fcb2230d08939d29852fba3fcd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="a964d-102">Gestione del controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a964d-102">Managing call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a964d-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a964d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a964d-104">Il controllo di ammissione di chiamata (CAC) determina, in base alla larghezza di banda della rete disponibile, se consentire la creazione di sessioni di comunicazioni in tempo reale, ad esempio chiamate vocali o videochiamate.</span><span class="sxs-lookup"><span data-stu-id="a964d-104">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="a964d-105">Usare le procedure seguenti per gestire le diverse funzionalità di CAC per l'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a964d-105">Use the following procedures to manage different CAC features for your Lync Server 2013 environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a964d-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a964d-106">In This Section</span></span>

  - [<span data-ttu-id="a964d-107">Abilitazione del controllo di ammissione alle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a964d-107">Enabling call admission control in Lync Server 2013</span></span>](lync-server-2013-enabling-call-admission-control.md)

  - [<span data-ttu-id="a964d-108">Gestire i profili dei criteri di larghezza di banda di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a964d-108">Managing network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-managing-network-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="a964d-109">Aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a964d-109">Network regions in Lync Server 2013</span></span>](lync-server-2013-network-regions.md)

  - [<span data-ttu-id="a964d-110">Route dell'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a964d-110">Network region routes in Lync Server 2013</span></span>](lync-server-2013-network-region-routes.md)

  - [<span data-ttu-id="a964d-111">Controllo ammissione chiamata per i siti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a964d-111">Call admission control for sites in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-for-sites.md)

  - [<span data-ttu-id="a964d-112">Attivazione e disattivazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a964d-112">Enabling and disabling media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-media-bypass.md)

  - [<span data-ttu-id="a964d-113">Collegamento tra aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a964d-113">Linking network regions in Lync Server 2013</span></span>](lync-server-2013-linking-network-regions.md)

  - [<span data-ttu-id="a964d-114">Gestione delle subnet di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a964d-114">Managing network subnets in Lync Server 2013</span></span>](lync-server-2013-managing-network-subnets.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a964d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a964d-115">See Also</span></span>


[<span data-ttu-id="a964d-116">Panoramica del controllo di ammissione alle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a964d-116">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

