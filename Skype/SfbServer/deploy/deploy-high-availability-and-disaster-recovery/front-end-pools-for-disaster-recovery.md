---
title: Distribuire pool Front End associati per il ripristino di emergenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Si può decidere di usare i pool Front-End associati per ottenere protezione dal ripristino di emergenza, ma non è un requisito.
ms.openlocfilehash: 73f7d7619efbfc82124507234ebea8ebbcf4a7e8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002906"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="2023a-103">Distribuire pool Front End associati per il ripristino di emergenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2023a-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="2023a-104">Si può decidere di usare i pool Front-End associati per ottenere protezione dal ripristino di emergenza, ma non è un requisito.</span><span class="sxs-lookup"><span data-stu-id="2023a-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="2023a-105">È possibile distribuire facilmente la topologia di ripristino di emergenza di pool Front-End associati usando generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="2023a-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="2023a-106">Per distribuire una coppia di pool Front-End</span><span class="sxs-lookup"><span data-stu-id="2023a-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="2023a-107">Se i pool sono nuovi e non ancora definiti, usare generatore di topologie per creare i pool.</span><span class="sxs-lookup"><span data-stu-id="2023a-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="2023a-108">In Generatore di topologie fare clic con il pulsante destro del mouse su uno dei due pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="2023a-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="2023a-109">Fare clic su **resilienza** nel riquadro sinistro e quindi selezionare **pool di backup associato** nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="2023a-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="2023a-110">Nella casella sotto il **pool di backup associato**selezionare il pool che si vuole associare al pool.</span><span class="sxs-lookup"><span data-stu-id="2023a-110">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool.</span></span> <span data-ttu-id="2023a-111">Solo i pool esistenti che non sono già associati a un altro pool saranno disponibili per la selezione.</span><span class="sxs-lookup"><span data-stu-id="2023a-111">Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="2023a-112">Selezionare **failover automatico e failback per la voce**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2023a-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="2023a-113">Quando si visualizzano i dettagli su questo pool, il pool associato ora viene visualizzato nel riquadro destro in **resilienza**.</span><span class="sxs-lookup"><span data-stu-id="2023a-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="2023a-114">USA generatore di topologia per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="2023a-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="2023a-115">Se i due pool non sono stati ancora distribuiti, distribuirli ora e la configurazione verrà completata.</span><span class="sxs-lookup"><span data-stu-id="2023a-115">If the two pools were not yet deployed, deploy them now and the configuration will be complete.</span></span> <span data-ttu-id="2023a-116">È possibile ignorare i passaggi finali di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="2023a-116">You can skip the final steps in this procedure.</span></span>
    
    <span data-ttu-id="2023a-117">Tuttavia, se i pool sono già stati distribuiti prima di definire la relazione associata, è necessario completare la procedura finale seguente.</span><span class="sxs-lookup"><span data-stu-id="2023a-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following final steps.</span></span>
    
8. <span data-ttu-id="2023a-118">In tutti i server front-end in entrambi i pool eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2023a-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="2023a-119">In questo modo vengono configurati altri servizi necessari per il corretto funzionamento delle associazioni di backup.</span><span class="sxs-lookup"><span data-stu-id="2023a-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="2023a-120">Una volta completata l'installazione dei componenti necessari per l'associazione di backup in tutti i server front-end in entrambi i pool, assicurati di riapplicare tutti gli aggiornamenti cumulativi esistenti applicati in precedenza in questi server front-end in entrambi i pool e quindi continuare con il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="2023a-120">Once Bootstrapper finishes installing the required components for backup pairing on every Front end Server in both pools, please be sure to re-apply any existing Cumulative Update that was previously applied on these Front End Servers in both pools and then continue with the next step.</span></span>

10. <span data-ttu-id="2023a-121">Da un prompt dei comandi di Skype for Business Server Management Shell eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2023a-121">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. <span data-ttu-id="2023a-122">Costringere i dati dell'utente e della conferenza di entrambi i pool a essere sincronizzati tra loro con i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="2023a-122">Force the user and conference data of both pools to be synchronized with each other with the following cmdlets:</span></span>
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="2023a-123">La sincronizzazione dei dati può richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="2023a-123">Synchronizing the data may take some time.</span></span> <span data-ttu-id="2023a-124">Puoi usare i cmdlet seguenti per verificare lo stato.</span><span class="sxs-lookup"><span data-stu-id="2023a-124">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="2023a-125">Verificare che lo stato in entrambe le direzioni sia in stato stabile.</span><span class="sxs-lookup"><span data-stu-id="2023a-125">Make sure that the status in both directions is in steady state.</span></span>
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="2023a-126">L'opzione **failover automatico e il failback per la voce** e gli intervalli di tempo associati in Generatore di topologia si applicano solo alle caratteristiche di resilienza vocale introdotte in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2023a-126">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="2023a-127">La selezione di questa opzione non implica che il failover del pool illustrato in questo documento sia automatico.</span><span class="sxs-lookup"><span data-stu-id="2023a-127">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="2023a-128">Il failover del pool e il failback richiedono sempre che un amministratore richiami manualmente rispettivamente i cmdlet failover e failback.</span><span class="sxs-lookup"><span data-stu-id="2023a-128">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2023a-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2023a-129">See also</span></span>

[<span data-ttu-id="2023a-130">Ripristino di emergenza del pool di front-end in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2023a-130">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
