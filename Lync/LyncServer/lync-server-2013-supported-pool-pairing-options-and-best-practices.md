---
title: Opzioni di associazione e procedure consigliate per il raggruppamento supportate in Lync Server 2013
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
ms.openlocfilehash: 9090fefba4b80f14382b9b43b5e9ced7cb36b2e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="738fc-102">Opzioni di associazione e procedure consigliate per la combinazione di pool supportate per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="738fc-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="738fc-103">_**Argomento Ultima modifica:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="738fc-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="738fc-104">Non esiste alcuna restrizione sulla distanza tra due centri dati che includono i pool Front-End associati tra loro.</span><span class="sxs-lookup"><span data-stu-id="738fc-104">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other.</span></span> <span data-ttu-id="738fc-105">Ti consigliamo di usare due centri dati nella stessa area geografica mondiale, con collegamenti ad alta velocità tra di essi.</span><span class="sxs-lookup"><span data-stu-id="738fc-105">We recommend that you use two data centers in the same world region, with high-speed links between them.</span></span> <span data-ttu-id="738fc-106">È preferibile che i due centri dati siano abbastanza separati per evitare che un singolo disastro colpisca contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="738fc-106">It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="738fc-107">È possibile avere due centri dati in tutte le aree del mondo, ma potrebbe causare una perdita di dati più elevata a causa della latenza nella replicazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="738fc-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="738fc-108">Quando si pianificano i pool da associare, è necessario ricordare che sono supportate solo le associazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="738fc-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="738fc-109">I pool Enterprise Edition possono essere accoppiati solo con altri pool di Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="738fc-109">Enterprise Edition pools can be paired only with other Enterprise Edition pools.</span></span> <span data-ttu-id="738fc-110">Allo stesso modo, i pool Standard Edition possono essere abbinati solo agli altri pool di Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="738fc-110">Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="738fc-111">I pool fisici possono essere accoppiati solo con altri pool fisici.</span><span class="sxs-lookup"><span data-stu-id="738fc-111">Physical pools can be paired only with other physical pools.</span></span> <span data-ttu-id="738fc-112">Allo stesso modo, i pool virtuali possono essere abbinati solo ad altri pool virtuali.</span><span class="sxs-lookup"><span data-stu-id="738fc-112">Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="738fc-113">I pool combinati devono eseguire lo stesso sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="738fc-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="738fc-114">Né il generatore di topologie né la convalida della topologia impediscono l'associazione di due pool in modo da non seguire questi suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="738fc-114">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations.</span></span> <span data-ttu-id="738fc-115">Ad esempio, generatore di topologie consente di associare un pool Enterprise Edition a un pool di Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="738fc-115">For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool.</span></span> <span data-ttu-id="738fc-116">Tuttavia, questi tipi di associazione non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="738fc-116">However, these types of pairings are not supported.</span></span>

<span data-ttu-id="738fc-117">Ogni pool in una coppia deve avere la capacità di servire tutti gli utenti da entrambi i pool in caso di emergenza.</span><span class="sxs-lookup"><span data-stu-id="738fc-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="738fc-118">Se si abbinano pool Enterprise Edition, è anche possibile implementare una disponibilità elevata nei server back-end, ma per le coppie di pool standard solo le misure di ripristino di emergenza sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="738fc-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

