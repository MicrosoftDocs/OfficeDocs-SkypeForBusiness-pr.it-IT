---
title: 'Lync Server 2013: aggiornare o aggiornare Front End Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32a537dc701f7b3e613cc9364c786cb561cadb50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530323"
---
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="18a5d-102">Aggiornare o aggiornare Front End Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18a5d-102">Upgrade or update Front End Servers in Lync Server 2013</span></span>

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18a5d-103">_**Ultimo argomento modificato:** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="18a5d-103">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="18a5d-104">I Front End Server di un pool Enterprise Edition sono organizzati in *domini di aggiornamento*.</span><span class="sxs-lookup"><span data-stu-id="18a5d-104">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="18a5d-105">Si tratta di subset di Front End Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="18a5d-105">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="18a5d-106">I domini di aggiornamento vengono creati automaticamente dal generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="18a5d-106">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="18a5d-107">Quando si aggiornano i server, è necessario eseguire un dominio di aggiornamento alla volta.</span><span class="sxs-lookup"><span data-stu-id="18a5d-107">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="18a5d-108">Portare ogni server in un dominio di aggiornamento verso il basso, aggiornarlo e quindi riavviarlo prima di passare a un altro dominio di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="18a5d-108">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="18a5d-109">Tenere presente che i domini e i server dell'aggiornamento sono stati aggiornati fino a quel momento.</span><span class="sxs-lookup"><span data-stu-id="18a5d-109">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="18a5d-110">Quando si aggiorna ogni server, utilizzare il diagramma diagramma di flusso seguente.</span><span class="sxs-lookup"><span data-stu-id="18a5d-110">Use the following flowchart diagram when upgrading each server.</span></span>

![Eseguire l'aggiornamento dei Front End Server](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="18a5d-112">Per applicare un aggiornamento ai Front End Server in un pool</span><span class="sxs-lookup"><span data-stu-id="18a5d-112">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="18a5d-113">In un Front End Server del pool eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="18a5d-113">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="18a5d-114">**Get-CsPoolUpgradeReadinessState**</span><span class="sxs-lookup"><span data-stu-id="18a5d-114">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="18a5d-115">Se il valore di *PoolUpgradeState* è **occupato**, attendere 10 minuti, quindi tentare di nuovo **Get-CsPoolUpgradeReadinessState** .</span><span class="sxs-lookup"><span data-stu-id="18a5d-115">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="18a5d-116">Se si vede **occupato** per almeno tre volte consecutive, dopo aver atteso 10 minuti tra ogni tentativo o se viene visualizzato un risultato di **InsufficientActiveFrontEnds** per **PoolUpgradeState,** si verifica un problema con il pool.</span><span class="sxs-lookup"><span data-stu-id="18a5d-116">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="18a5d-117">Se questo pool è associato a un altro pool Front End in una topologia per il ripristino di emergenza, eseguire il failover del pool nel pool di backup e aggiornare i server di questo pool.</span><span class="sxs-lookup"><span data-stu-id="18a5d-117">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="18a5d-118">Per ulteriori informazioni, vedere [failover di un pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="18a5d-118">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="18a5d-119">Se il valore di *PoolUpgradeState* è **Pronto**, andare al passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="18a5d-119">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="18a5d-120">Il cmdlet **Get-CsPoolUpgradeReadinessState** restituisce inoltre informazioni su ogni dominio di aggiornamento nel pool e sui front end server in ogni dominio di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="18a5d-120">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="18a5d-121">Se il valore **ReadyforUpgrade** è impostato su **true** per il dominio di aggiornamento che contiene il server o i server che si desidera aggiornare, è possibile aggiornare i server in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="18a5d-121">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="18a5d-122">A tale scopo, effettuare quando segue:</span><span class="sxs-lookup"><span data-stu-id="18a5d-122">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="18a5d-123">Interrompere le nuove connessioni ai front end server che si desidera aggiornare utilizzando il `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18a5d-123">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="18a5d-124">Se si eseguono questi aggiornamenti del server durante i tempi di inattività dei server pianificati, è possibile eseguire questo cmdlet senza il parametro '-<STRONG>grazioso</STRONG>', come indicato di seguito: <STRONG>Stop-CsWindowsService</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="18a5d-124">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="18a5d-125">Questo consente di arrestare immediatamente i servizi, senza attendere che vengano soddisfatte tutte le richieste di servizio esistenti.</span><span class="sxs-lookup"><span data-stu-id="18a5d-125">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="18a5d-126">Aggiornare i server associati a questo dominio di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="18a5d-126">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="18a5d-127">Riavviare i server e verificare che accettino nuove connessioni.</span><span class="sxs-lookup"><span data-stu-id="18a5d-127">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="18a5d-128">Ripetere i passaggi 1 e 2 per ogni altro dominio di aggiornamento nel pool fino a quando non sono stati aggiornati tutti i Front End Server.</span><span class="sxs-lookup"><span data-stu-id="18a5d-128">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

