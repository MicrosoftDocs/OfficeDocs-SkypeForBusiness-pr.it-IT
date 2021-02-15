---
title: Distribuire pool Front End abbinati per il ripristino di emergenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: È possibile decidere di utilizzare pool Front End abbinati per fornire protezione da ripristino di emergenza, ma non è un requisito.
ms.openlocfilehash: 7d066de60bf3ab98d73d8aeee08044803fad983c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830606"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="01e30-103">Distribuire pool Front End abbinati per il ripristino di emergenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="01e30-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="01e30-104">È possibile decidere di utilizzare pool Front End abbinati per fornire protezione da ripristino di emergenza, ma non è un requisito.</span><span class="sxs-lookup"><span data-stu-id="01e30-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="01e30-105">È possibile distribuire facilmente la topologia di ripristino di emergenza di pool Front End abbinati utilizzando Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="01e30-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="01e30-106">Per distribuire una coppia di pool Front End</span><span class="sxs-lookup"><span data-stu-id="01e30-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="01e30-107">Se i pool sono nuovi e non ancora definiti, utilizzare Generatore di topologie per creare i pool.</span><span class="sxs-lookup"><span data-stu-id="01e30-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="01e30-108">In Generatore di topologie fare clic con il pulsante destro del mouse su uno dei due pool e quindi **scegliere Modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="01e30-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="01e30-109">Fare clic su **Resilienza** nel riquadro a sinistra e selezionare **Pool di backup associato** nel riquadro a destra.</span><span class="sxs-lookup"><span data-stu-id="01e30-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="01e30-p101">Nella casella sotto **Pool di backup associato** selezionare il pool da accoppiare a questo pool. Sarà possibile selezionare solo pool esistenti che non sono già accoppiati con un altro pool.</span><span class="sxs-lookup"><span data-stu-id="01e30-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="01e30-112">Selezionare **Failover e failback automatico per VoIP** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="01e30-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="01e30-113">Quando vengono visualizzati i dettagli su questo pool, il pool associato apparirà nel riquadro a destra sotto **Resilienza**.</span><span class="sxs-lookup"><span data-stu-id="01e30-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="01e30-114">Utilizzare Generatore di topologie per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="01e30-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="01e30-115">Se i due pool non sono stati ancora distribuiti, distribuirli ora in modo da completare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="01e30-115">If the two pools were not yet deployed, deploy them now and the configuration will be complete.</span></span> <span data-ttu-id="01e30-116">È possibile ignorare i passaggi finali di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="01e30-116">You can skip the final steps in this procedure.</span></span>
    
    <span data-ttu-id="01e30-117">Tuttavia, se i pool sono già stati distribuiti prima di definire la relazione associata, è necessario completare i passaggi finali seguenti.</span><span class="sxs-lookup"><span data-stu-id="01e30-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following final steps.</span></span>
    
8. <span data-ttu-id="01e30-118">Su ogni Front End Server in entrambi i pool eseguire:</span><span class="sxs-lookup"><span data-stu-id="01e30-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="01e30-119">Consente di configurare altri servizi necessari per il corretto funzionamento dell'accoppiamento di backup.</span><span class="sxs-lookup"><span data-stu-id="01e30-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="01e30-120">Al termine dell'installazione dei componenti necessari per l'associazione di backup in ogni Front End Server in entrambi i pool, assicurarsi di ri applicare nuovamente qualsiasi aggiornamento cumulativo esistente applicato in precedenza in questi Front End Server in entrambi i pool e quindi continuare con il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="01e30-120">Once Bootstrapper finishes installing the required components for backup pairing on every Front end Server in both pools, please be sure to re-apply any existing Cumulative Update that was previously applied on these Front End Servers in both pools and then continue with the next step.</span></span>

10. <span data-ttu-id="01e30-121">Da un prompt dei comandi di Skype for Business Server Management Shell, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="01e30-121">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. <span data-ttu-id="01e30-122">Forzare la sincronizzazione tra l'utente e i dati delle conferenze di entrambi i pool con i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="01e30-122">Force the user and conference data of both pools to be synchronized with each other with the following cmdlets:</span></span>
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="01e30-123">La sincronizzazione dei dati potrebbe richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="01e30-123">Synchronizing the data may take some time.</span></span> <span data-ttu-id="01e30-124">Per controllare lo stato è possibile usare i cmdlet seguenti.</span><span class="sxs-lookup"><span data-stu-id="01e30-124">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="01e30-125">Assicurati che lo stato in entrambe le direzioni sia stabile.</span><span class="sxs-lookup"><span data-stu-id="01e30-125">Make sure that the status in both directions is in steady state.</span></span>
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="01e30-126">L'opzione failover e **failback** automatici per VoIP e gli intervalli di tempo associati in Generatore di topologie si applicano solo alle funzionalità di resilienza vocale introdotte in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01e30-126">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="01e30-127">La selezione di questa opzione non implica che il failover del pool descritto in questo documento sia automatico.</span><span class="sxs-lookup"><span data-stu-id="01e30-127">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="01e30-128">Il failover e il failback del pool richiedono sempre che un amministratore richiami manualmente i cmdlet di failover e di failback, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="01e30-128">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="01e30-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01e30-129">See also</span></span>

[<span data-ttu-id="01e30-130">Ripristino di emergenza del pool Front End in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="01e30-130">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
