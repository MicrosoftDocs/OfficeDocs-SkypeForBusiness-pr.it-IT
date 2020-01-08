---
title: Opzioni di associazione e procedure consigliate per il raggruppamento supportate in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00202aeb4db74ec81671e557a0679a9f41046b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="f1881-102">Opzioni di associazione e procedure consigliate per la combinazione di pool supportate per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1881-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1881-103">_**Argomento Ultima modifica:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="f1881-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="f1881-104">Non esiste alcuna restrizione sulla distanza tra due centri dati che includono i pool Front-End associati tra loro.</span><span class="sxs-lookup"><span data-stu-id="f1881-104">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other.</span></span> <span data-ttu-id="f1881-105">Ti consigliamo di usare due centri dati nella stessa area geografica mondiale, con collegamenti ad alta velocità tra di essi.</span><span class="sxs-lookup"><span data-stu-id="f1881-105">We recommend that you use two data centers in the same world region, with high-speed links between them.</span></span> <span data-ttu-id="f1881-106">È preferibile che i due centri dati siano abbastanza separati per evitare che un singolo disastro colpisca contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="f1881-106">It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="f1881-107">È possibile avere due centri dati in tutte le aree del mondo, ma potrebbe causare una perdita di dati più elevata a causa della latenza nella replicazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="f1881-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="f1881-108">Quando si pianificano i pool da associare, è necessario ricordare che sono supportate solo le associazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1881-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="f1881-109">I pool Enterprise Edition possono essere accoppiati solo con altri pool di Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f1881-109">Enterprise Edition pools can be paired only with other Enterprise Edition pools.</span></span> <span data-ttu-id="f1881-110">Allo stesso modo, i pool Standard Edition possono essere abbinati solo agli altri pool di Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f1881-110">Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="f1881-111">I pool fisici possono essere accoppiati solo con altri pool fisici.</span><span class="sxs-lookup"><span data-stu-id="f1881-111">Physical pools can be paired only with other physical pools.</span></span> <span data-ttu-id="f1881-112">Allo stesso modo, i pool virtuali possono essere abbinati solo ad altri pool virtuali.</span><span class="sxs-lookup"><span data-stu-id="f1881-112">Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="f1881-113">I pool combinati devono eseguire lo stesso sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f1881-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="f1881-114">Né il generatore di topologie né la convalida della topologia impediscono l'associazione di due pool in modo da non seguire questi suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="f1881-114">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations.</span></span> <span data-ttu-id="f1881-115">Ad esempio, generatore di topologie consente di associare un pool Enterprise Edition a un pool di Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f1881-115">For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool.</span></span> <span data-ttu-id="f1881-116">Tuttavia, questi tipi di associazione non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="f1881-116">However, these types of pairings are not supported.</span></span>

<span data-ttu-id="f1881-117">Ogni pool in una coppia deve avere la capacità di servire tutti gli utenti da entrambi i pool in caso di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f1881-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="f1881-118">Se si abbinano pool Enterprise Edition, è anche possibile implementare una disponibilità elevata nei server back-end, ma per le coppie di pool standard solo le misure di ripristino di emergenza sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="f1881-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

