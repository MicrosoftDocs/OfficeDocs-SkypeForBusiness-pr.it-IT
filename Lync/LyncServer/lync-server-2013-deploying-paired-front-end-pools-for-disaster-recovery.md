---
title: 'Lync Server 2013: distribuzione di pool Front End abbinati per il ripristino di emergenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a18b92dde9b6ca48ffe8912f216331c39ef9cc9d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="279a8-102">Distribuzione di pool Front End abbinati per il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="279a8-102">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="279a8-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="279a8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="279a8-104">È possibile distribuire facilmente la topologia di ripristino di emergenza dei pool Front End associati utilizzando Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="279a8-104">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span>

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="279a8-105">Per distribuire una coppia di pool Front End</span><span class="sxs-lookup"><span data-stu-id="279a8-105">To deploy a pair of Front End pools</span></span>

1.  <span data-ttu-id="279a8-106">Se i pool sono nuovi e non ancora definiti, utilizzare Generatore di topologie per creare i pool.</span><span class="sxs-lookup"><span data-stu-id="279a8-106">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>

2.  <span data-ttu-id="279a8-107">In Generatore di topologie fare clic con il pulsante destro del mouse su uno dei due pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="279a8-107">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="279a8-108">Fare clic su **Resilienza** nel riquadro a sinistra e selezionare **Pool di backup associato** nel riquadro a destra.</span><span class="sxs-lookup"><span data-stu-id="279a8-108">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>

4.  <span data-ttu-id="279a8-p101">Nella casella sotto **Pool di backup associato** selezionare il pool da accoppiare a questo pool. Sarà possibile selezionare solo pool esistenti che non sono già accoppiati con un altro pool.</span><span class="sxs-lookup"><span data-stu-id="279a8-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
    <span data-ttu-id="279a8-111">![36080581-db76-497D-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497D-bf9e-f02b39574d0e")</span><span class="sxs-lookup"><span data-stu-id="279a8-111">![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")</span></span>  

5.  <span data-ttu-id="279a8-112">Selezionare **Failover e failback automatico per VoIP** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="279a8-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="279a8-113">Quando vengono visualizzati i dettagli su questo pool, il pool associato apparirà nel riquadro a destra sotto **Resilienza**.</span><span class="sxs-lookup"><span data-stu-id="279a8-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>

6.  <span data-ttu-id="279a8-114">Utilizzare Generatore di topologie per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="279a8-114">Use Topology Builder to publish the topology.</span></span>

7.  <span data-ttu-id="279a8-p102">Se i due pool non sono stati ancora distribuiti, distribuirli ora in modo da completare la configurazione. È possibile ignorare i due passaggi finali di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="279a8-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="279a8-117">Tuttavia, se i pool erano già distribuiti prima che venisse definita la relazione accoppiata, è necessario completare i due passaggi finali che seguono.</span><span class="sxs-lookup"><span data-stu-id="279a8-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>

8.  <span data-ttu-id="279a8-118">Su ogni Front End Server in entrambi i pool eseguire:</span><span class="sxs-lookup"><span data-stu-id="279a8-118">On every Front End Server in both pools, run the following:</span></span>
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    <span data-ttu-id="279a8-119">Consente di configurare altri servizi necessari per il corretto funzionamento dell'accoppiamento di backup.</span><span class="sxs-lookup"><span data-stu-id="279a8-119">This configures other services required for backup pairing to work correctly.</span></span>

9.  <span data-ttu-id="279a8-120">Da un prompt dei comandi di Lync Server Management Shell, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="279a8-120">From a Lync Server Management Shell command prompt, run the following:</span></span>
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. <span data-ttu-id="279a8-121">Forzare la sincronizzazione dei dati utente e di conferenza di entrambi i pool specificando i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="279a8-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    <span data-ttu-id="279a8-122">La sincronizzazione dei dati potrebbe richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="279a8-122">Synchronizing the data may take some time.</span></span> <span data-ttu-id="279a8-123">Per controllare lo stato è possibile usare i cmdlet seguenti.</span><span class="sxs-lookup"><span data-stu-id="279a8-123">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="279a8-124">Assicurarsi che lo stato di entrambe le direzioni sia in stato stazionario.</span><span class="sxs-lookup"><span data-stu-id="279a8-124">Make sure that the status in both directions is in steady state.</span></span>
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> <span data-ttu-id="279a8-125">L'opzione <STRONG>failover automatico e failback per la voce</STRONG> e gli intervalli di tempo associati in Generatore di topologie si applicano solo alle funzionalità di resilienza vocale introdotte in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="279a8-125">The <STRONG>Automatic failover and failback for Voice</STRONG> option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server 2010.</span></span> <span data-ttu-id="279a8-126">La selezione di questa opzione non implica che il failover del pool descritto in questo documento sia automatico.</span><span class="sxs-lookup"><span data-stu-id="279a8-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="279a8-127">Il failover e il failback del pool richiedono sempre che un amministratore richiami manualmente i cmdlet di failover e di failback, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="279a8-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

