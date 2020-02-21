---
title: Opzioni di abbinamento e procedure consigliate per il pool di Lync Server 2013 supportate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d33bc5e9622728fb4ee9c2a6a566e6010466d577
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="4e697-102">Opzioni di abbinamento del pool supportate e procedure consigliate per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e697-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e697-103">_**Ultimo argomento modificato:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="4e697-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="4e697-p101">La distanza tra due data center che devono contenere pool Front End abbinati tra loro può essere illimitata. Si consiglia di utilizzare due data center situati nella stessa area internazionale con collegamenti ad alta velocità. La situazione ottimale prevede che i due data center siano sufficientemente distanti per evitare che un'emergenza interessi entrambi contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="4e697-p101">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other. We recommend that you use two data centers in the same world region, with high-speed links between them. It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="4e697-107">L'implementazione di due data center in aree internazionali diverse è possibile, ma può causare una perdita di dati più elevata a causa della latenza nella replica dei dati.</span><span class="sxs-lookup"><span data-stu-id="4e697-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="4e697-108">Quando si pianificano i pool da associare, è necessario tenere presente che sono supportate solo le associazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e697-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="4e697-p102">I pool Enterprise Edition possono essere abbinati solo ad altri pool Enterprise Edition. Analogamente, i pool Standard Edition sono abbinabili solo ad altri pool Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4e697-p102">Enterprise Edition pools can be paired only with other Enterprise Edition pools. Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="4e697-p103">I pool fisici possono essere abbinati solo ad altri pool fisici. Analogamente, i pool virtuali sono abbinabili solo ad altri pool virtuali.</span><span class="sxs-lookup"><span data-stu-id="4e697-p103">Physical pools can be paired only with other physical pools. Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="4e697-113">I pool associati insieme devono eseguire lo stesso sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4e697-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="4e697-114">È possibile abbinare due pool in un modo diverso da quanto consigliato sia nel Generatore di topologie sia durante la convalida della topologia.</span><span class="sxs-lookup"><span data-stu-id="4e697-114">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations.</span></span> <span data-ttu-id="4e697-115">Il Generatore di topologie, ad esempio, consente di abbinare un pool Enterprise Edition a un pool Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4e697-115">For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool.</span></span> <span data-ttu-id="4e697-116">Tuttavia, questi tipi di abbinamenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="4e697-116">However, these types of pairings are not supported.</span></span>

<span data-ttu-id="4e697-117">Ogni pool di una coppia deve essere in grado di servire tutti gli utenti di entrambi i pool in caso di emergenza.</span><span class="sxs-lookup"><span data-stu-id="4e697-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="4e697-118">Se si abbinano pool Enterprise Edition, è anche possibile implementare la disponibilità elevata nei server Back End, ma per coppie di pool Standard Edition sono disponibili solo le misure per il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="4e697-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

