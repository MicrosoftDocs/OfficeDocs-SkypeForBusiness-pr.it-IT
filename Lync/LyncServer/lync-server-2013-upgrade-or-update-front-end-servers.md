---
title: 'Lync Server 2013: aggiornare o aggiornare i server front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af1680da68299881fe94244969d44fce1900532b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="23e96-102">Aggiornare o aggiornare i server front-end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23e96-102">Upgrade or update Front End Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23e96-103">_**Argomento Ultima modifica:** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="23e96-103">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="23e96-104">I server front-end in un pool di Enterprise Edition sono organizzati in *domini di aggiornamento*.</span><span class="sxs-lookup"><span data-stu-id="23e96-104">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="23e96-105">Si tratta di sottoinsiemi di server front-end nel pool.</span><span class="sxs-lookup"><span data-stu-id="23e96-105">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="23e96-106">I domini di aggiornamento vengono creati automaticamente da generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="23e96-106">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="23e96-107">Quando si aggiornano i server, è necessario farlo un dominio di aggiornamento alla volta.</span><span class="sxs-lookup"><span data-stu-id="23e96-107">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="23e96-108">Trasferire ogni server in un dominio di aggiornamento, aggiornarlo e quindi riavviarlo prima di passare a un altro dominio di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="23e96-108">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="23e96-109">Assicurati di tenere traccia dei domini e server di aggiornamento aggiornati fino a questo momento.</span><span class="sxs-lookup"><span data-stu-id="23e96-109">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="23e96-110">Usare il diagramma di flusso seguente durante l'aggiornamento di ogni server.</span><span class="sxs-lookup"><span data-stu-id="23e96-110">Use the following flowchart diagram when upgrading each server.</span></span>

:::image type="content" source="images/UpgradeUpdateFrontEndServerslync2013.png" alt-text="Aggiornare o aggiornare i server front-end":::

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="23e96-112">Per applicare un aggiornamento ai server front-end in un pool</span><span class="sxs-lookup"><span data-stu-id="23e96-112">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="23e96-113">In un server front-end nel pool eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="23e96-113">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="23e96-114">**Get-CsPoolUpgradeReadinessState**</span><span class="sxs-lookup"><span data-stu-id="23e96-114">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="23e96-115">Se il valore di *PoolUpgradeState* è **occupato**, attendere 10 minuti e quindi provare di nuovo **Get-CsPoolUpgradeReadinessState** .</span><span class="sxs-lookup"><span data-stu-id="23e96-115">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="23e96-116">Se si vede **occupato** per almeno tre volte consecutive, dopo aver aspettato 10 minuti tra ogni tentativo o se viene visualizzato qualsiasi risultato di **InsufficientActiveFrontEnds** per **PoolUpgradeState,** si verifica un problema con il pool.</span><span class="sxs-lookup"><span data-stu-id="23e96-116">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="23e96-117">Se questo pool è associato a un altro pool Front-end in una topologia di ripristino di emergenza, il pool deve essere superato nel pool di backup e quindi aggiornare i server in questo pool.</span><span class="sxs-lookup"><span data-stu-id="23e96-117">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="23e96-118">Per informazioni dettagliate, vedere [mancanza di un pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="23e96-118">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="23e96-119">Se il valore di *PoolUpgradeState* è **pronto**, passare al passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="23e96-119">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="23e96-120">Il cmdlet **Get-CsPoolUpgradeReadinessState** restituisce anche informazioni su ogni dominio di aggiornamento nel pool e su quali server front-end si trovano in ogni dominio di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="23e96-120">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="23e96-121">Se il valore **ReadyforUpgrade** è **true** per il dominio di aggiornamento che contiene il server o i server che si desidera aggiornare, è possibile aggiornare i server in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="23e96-121">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="23e96-122">Per eseguire questa operazione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="23e96-122">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="23e96-123">Arrestare le nuove connessioni ai server front-end che si vuole aggiornare usando il `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="23e96-123">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="23e96-124">Se si eseguono questi aggiornamenti del server durante un periodo di inattività pianificato del server, è possibile eseguire questo cmdlet senza il parametro "-<STRONG>grazioso</STRONG>", come indicato di seguito: <STRONG>Stop-CsWindowsService</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="23e96-124">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="23e96-125">In questo modo si chiuderanno immediatamente i servizi, senza attendere la compilazione di tutte le richieste di servizio esistenti.</span><span class="sxs-lookup"><span data-stu-id="23e96-125">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="23e96-126">Aggiornare i server associati al dominio di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="23e96-126">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="23e96-127">Riavviare i server e verificare che accettino nuove connessioni.</span><span class="sxs-lookup"><span data-stu-id="23e96-127">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="23e96-128">Ripetere i passaggi 1 e 2 per ogni altro dominio di aggiornamento nel pool, finché non sono stati aggiornati tutti i server front-end.</span><span class="sxs-lookup"><span data-stu-id="23e96-128">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

