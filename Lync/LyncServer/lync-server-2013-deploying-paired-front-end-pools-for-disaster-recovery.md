---
title: 'Lync Server 2013: Distribuzione di pool Front End abbinati per il ripristino di emergenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c01549722fe04d0a4833a9d2c37fd5e85dc575a7
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40978542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="ea160-102">Distribuzione di pool Front End abbinati per il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea160-102">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea160-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ea160-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ea160-104">È possibile distribuire facilmente la topologia di ripristino di emergenza di pool Front-End associati usando generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="ea160-104">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span>

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="ea160-105">Per distribuire una coppia di pool Front-End</span><span class="sxs-lookup"><span data-stu-id="ea160-105">To deploy a pair of Front End pools</span></span>

1.  <span data-ttu-id="ea160-106">Se i pool sono nuovi e non ancora definiti, usare generatore di topologie per creare i pool.</span><span class="sxs-lookup"><span data-stu-id="ea160-106">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>

2.  <span data-ttu-id="ea160-107">In Generatore di topologie fare clic con il pulsante destro del mouse su uno dei due pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="ea160-107">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="ea160-108">Fare clic su **resilienza** nel riquadro sinistro e quindi selezionare **pool di backup associato** nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="ea160-108">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>

4.  <span data-ttu-id="ea160-109">Nella casella sotto il **pool di backup associato**selezionare il pool che si vuole associare al pool.</span><span class="sxs-lookup"><span data-stu-id="ea160-109">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool.</span></span> <span data-ttu-id="ea160-110">Solo i pool esistenti che non sono già associati a un altro pool saranno disponibili per la selezione.</span><span class="sxs-lookup"><span data-stu-id="ea160-110">Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
    <span data-ttu-id="ea160-111">![36080581-db76-497D-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497D-bf9e-f02b39574d0e")</span><span class="sxs-lookup"><span data-stu-id="ea160-111">![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")</span></span>  

5.  <span data-ttu-id="ea160-112">Selezionare **failover automatico e failback per la voce**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea160-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="ea160-113">Quando si visualizzano i dettagli su questo pool, il pool associato ora viene visualizzato nel riquadro destro in **resilienza**.</span><span class="sxs-lookup"><span data-stu-id="ea160-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>

6.  <span data-ttu-id="ea160-114">USA generatore di topologia per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="ea160-114">Use Topology Builder to publish the topology.</span></span>

7.  <span data-ttu-id="ea160-115">Se i due pool non sono stati ancora distribuiti, distribuirli ora e la configurazione verrà completata.</span><span class="sxs-lookup"><span data-stu-id="ea160-115">If the two pools were not yet deployed, deploy them now and the configuration will be complete.</span></span> <span data-ttu-id="ea160-116">È possibile ignorare i due passaggi finali descritti in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="ea160-116">You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="ea160-117">Se tuttavia i pool sono già stati distribuiti prima di definire la relazione associata, è necessario completare i due passaggi finali seguenti.</span><span class="sxs-lookup"><span data-stu-id="ea160-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>

8.  <span data-ttu-id="ea160-118">In tutti i server front-end in entrambi i pool eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea160-118">On every Front End Server in both pools, run the following:</span></span>
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    <span data-ttu-id="ea160-119">In questo modo vengono configurati altri servizi necessari per il corretto funzionamento delle associazioni di backup.</span><span class="sxs-lookup"><span data-stu-id="ea160-119">This configures other services required for backup pairing to work correctly.</span></span>

9.  <span data-ttu-id="ea160-120">Da un prompt dei comandi di Lync Server Management Shell eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea160-120">From a Lync Server Management Shell command prompt, run the following:</span></span>
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. <span data-ttu-id="ea160-121">Costringere i dati dell'utente e della conferenza di entrambi i pool a essere sincronizzati tra loro, con i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea160-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    <span data-ttu-id="ea160-122">La sincronizzazione dei dati può richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="ea160-122">Synchronizing the data may take some time.</span></span> <span data-ttu-id="ea160-123">Puoi usare i cmdlet seguenti per verificare lo stato.</span><span class="sxs-lookup"><span data-stu-id="ea160-123">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="ea160-124">Verificare che lo stato in entrambe le direzioni sia in stato stabile.</span><span class="sxs-lookup"><span data-stu-id="ea160-124">Make sure that the status in both directions is in steady state.</span></span>
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> <span data-ttu-id="ea160-125">L'opzione <STRONG>failover automatico e il failback per la voce</STRONG> e gli intervalli di tempo associati in Generatore di topologia si applicano solo alle caratteristiche di resilienza vocale introdotte in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ea160-125">The <STRONG>Automatic failover and failback for Voice</STRONG> option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server 2010.</span></span> <span data-ttu-id="ea160-126">La selezione di questa opzione non implica che il failover del pool illustrato in questo documento sia automatico.</span><span class="sxs-lookup"><span data-stu-id="ea160-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="ea160-127">Il failover del pool e il failback richiedono sempre che un amministratore richiami manualmente rispettivamente i cmdlet failover e failback.</span><span class="sxs-lookup"><span data-stu-id="ea160-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

