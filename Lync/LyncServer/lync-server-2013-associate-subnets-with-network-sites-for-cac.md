---
title: 'Lync Server 2013: associare subnet a siti di rete per CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for CAC
ms:assetid: a749c9b3-15f3-4e74-9f43-1507d3c2c940
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412786(v=OCS.15)
ms:contentKeyID: 48185017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf447b2e34ff4f274ebcab9d36e40b65bedab7dd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="e2321-102">Associare subnet a siti di rete per CAC in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2321-102">Associate subnets with network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2321-103">_**Argomento Ultima modifica:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="e2321-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="e2321-104">Ogni subnet della rete deve essere associata a un sito di rete specifico.</span><span class="sxs-lookup"><span data-stu-id="e2321-104">Every subnet in your network must be associated with a specific network site.</span></span> <span data-ttu-id="e2321-105">Il motivo è che le informazioni sulla subnet vengono usate per determinare il sito di rete in cui si trova un endpoint.</span><span class="sxs-lookup"><span data-stu-id="e2321-105">This is because subnet information is used to determine the network site on which an endpoint is located.</span></span> <span data-ttu-id="e2321-106">Quando sono note le posizioni di entrambe le parti di una sessione, il controllo di ammissione di chiamata (CAC) può determinare se è disponibile una larghezza di banda sufficiente per stabilire una chiamata.</span><span class="sxs-lookup"><span data-stu-id="e2321-106">When the locations of both parties in a session are known, call admission control (CAC) can determine if there is sufficient bandwidth to establish a call.</span></span>

<span data-ttu-id="e2321-107">Il controllo di ammissione alle chiamate non ha particolari requisiti per l'associazione delle subnet con i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="e2321-107">Call admission control does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="e2321-108">Per creare un'associazione tra le subnet e i siti di rete della topologia, seguire le procedure descritte in [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="e2321-108">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span> <span data-ttu-id="e2321-109">Per visualizzare i siti di rete (e le rispettive subnet) nella topologia di rete di esempio per il controllo dell'ammissione alle chiamate, vedere [esempio: raccolta dei requisiti per il controllo di ammissione delle chiamate in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="e2321-109">To view the network sites (and their respective subnets) in the example network topology for call admission control, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

