---
title: Eseguire failover e failback di un pool
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: f2a1970df43aa2fb7becb03319ee6ff5934afe0a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991801"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="a9b38-103">Mancanza di un pool in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a9b38-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="a9b38-104">Usare le procedure seguenti se un singolo pool Front-end non è riuscito e deve essere fallito o il pool che ha sperimentato il disastro è tornato online ed è necessario ripristinare lo stato di lavoro normale.</span><span class="sxs-lookup"><span data-stu-id="a9b38-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="a9b38-105">Scopri anche come eseguire il failover e il failover del pool di Edge usato per la Federazione Skype for business o la Federazione XMPP oppure modificare il pool di bordi associato a un pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="a9b38-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="a9b38-106">Failover di un pool Front-End</span><span class="sxs-lookup"><span data-stu-id="a9b38-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="a9b38-107">Eseguire il failover di un pool</span><span class="sxs-lookup"><span data-stu-id="a9b38-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="a9b38-108">Failover del pool di Edge usato per la Federazione di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a9b38-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="a9b38-109">Failover del pool di Edge usato per la Federazione XMPP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a9b38-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="a9b38-110">Eseguire il failover del pool di Edge usato per la Federazione di Skype for Business Server o la Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="a9b38-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="a9b38-111">Cambiare il pool di bordi associato a un pool Front-End</span><span class="sxs-lookup"><span data-stu-id="a9b38-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="a9b38-112">Failover di un pool Front-End</span><span class="sxs-lookup"><span data-stu-id="a9b38-112">Fail over a Front End pool</span></span>

<span data-ttu-id="a9b38-113">In questa procedura, Datacenter1 contiene pool1 e pool1 non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="a9b38-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="a9b38-114">Non si riesce più a Pool2 situato in Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="a9b38-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="a9b38-115">La maggior parte del lavoro per il failover del pool comporta l'assenza di errori sopra l'Central Management store, se necessario.</span><span class="sxs-lookup"><span data-stu-id="a9b38-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="a9b38-116">Questo è importante perché l'archivio di gestione centrale deve essere funzionale quando gli utenti del pool non riescono più.</span><span class="sxs-lookup"><span data-stu-id="a9b38-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="a9b38-117">Inoltre, se un pool Front-end non riesce ma il pool di Edge in tale sito è ancora in corso, è necessario sapere se il pool di Edge usa il pool non riuscito come pool di hop successivo.</span><span class="sxs-lookup"><span data-stu-id="a9b38-117">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="a9b38-118">In caso affermativo, è necessario modificare il pool di bordi per usare un pool Front-end diverso prima di non superare il pool Front-end non riuscito.</span><span class="sxs-lookup"><span data-stu-id="a9b38-118">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="a9b38-119">La modalità di modifica dell'impostazione hop successiva varia a seconda che il bordo usi un pool nello stesso sito del pool di bordi o in un altro sito.</span><span class="sxs-lookup"><span data-stu-id="a9b38-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="a9b38-120">**Per impostare un pool di bordi per l'uso di un pool di hop successivo nello stesso sito**</span><span class="sxs-lookup"><span data-stu-id="a9b38-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="a9b38-121">Aprire Generatore di topologia, fare clic con il pulsante destro del mouse sul pool di bordi che deve essere modificato e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="a9b38-122">Fare clic su **hop successivo**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-122">Click **Next Hop**.</span></span> <span data-ttu-id="a9b38-123">Nell'elenco **hop successivo:** selezionare il pool che ora fungerà da pool hop successivo.</span><span class="sxs-lookup"><span data-stu-id="a9b38-123">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="a9b38-124">Fare clic su **OK**e quindi pubblicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="a9b38-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="a9b38-125">**Per impostare un pool di bordi per l'uso di un pool di hop successivo in un altro sito**</span><span class="sxs-lookup"><span data-stu-id="a9b38-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="a9b38-126">Aprire una finestra di Management Shell di Skype for Business Server e digitare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="a9b38-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="a9b38-127">**Per eseguire il failover di un pool in un caso di emergenza**</span><span class="sxs-lookup"><span data-stu-id="a9b38-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="a9b38-128">Individuare il pool che ospita il server di gestione centralizzato digitando il cmdlet seguente in un server front-end in Pool2:</span><span class="sxs-lookup"><span data-stu-id="a9b38-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="a9b38-129">I risultati di questo cmdlet mostrano quale pool ospita attualmente il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="a9b38-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="a9b38-130">Nel resto della procedura questo pool è noto come pool di CMS\_.</span><span class="sxs-lookup"><span data-stu-id="a9b38-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="a9b38-131">USA generatore di topologia per trovare la versione di Skype for Business Server in esecuzione\_nel pool di CMS.</span><span class="sxs-lookup"><span data-stu-id="a9b38-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="a9b38-132">Se è in uso Skype for Business Server, usare il cmdlet seguente per trovare il pool di backup del pool 1.</span><span class="sxs-lookup"><span data-stu-id="a9b38-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="a9b38-133">Consentire al\_pool di backup di essere il pool di backup.</span><span class="sxs-lookup"><span data-stu-id="a9b38-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="a9b38-134">Controllare lo stato di Central Management Store con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="a9b38-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="a9b38-135">Questo cmdlet deve indicare che sia ActiveMasterFQDN che ActiveFileTransferAgents puntano al nome FQDN del pool\_di CMS.</span><span class="sxs-lookup"><span data-stu-id="a9b38-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="a9b38-136">Se sono vuoti, il server di gestione centrale non è disponibile ed è necessario riuscire.</span><span class="sxs-lookup"><span data-stu-id="a9b38-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="a9b38-137">Se l'archivio di gestione centrale non è disponibile o se l'archivio di gestione centrale è in esecuzione in pool1, ovvero il pool non è riuscito, è necessario eseguire il failover del server di gestione centralizzato prima di non riuscire nel pool.</span><span class="sxs-lookup"><span data-stu-id="a9b38-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="a9b38-138">Se è necessario eseguire il failover del server di gestione centrale ospitato in un pool che usa Skype for Business Server, usare il cmdlet nel passaggio 5 di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="a9b38-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="a9b38-139">Se non è necessario eseguire il failover del server di gestione centrale, passare al passaggio 7 di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="a9b38-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="a9b38-140">Per non superare l'Central Management store in un pool che esegue Skype for Business Server, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9b38-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="a9b38-141">Prima di tutto, controlla che il server back\_-end nel pool di backup esegua l'istanza principale di Central Management Store digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a9b38-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="a9b38-142">Se il server di back-end principale\_nel pool di backup è l'entità, digitare:</span><span class="sxs-lookup"><span data-stu-id="a9b38-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="a9b38-143">Se il server mirror back-end nel\_pool di backup è l'entità, digitare:</span><span class="sxs-lookup"><span data-stu-id="a9b38-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="a9b38-144">Verificare che il failover di Central Management Server sia completo.</span><span class="sxs-lookup"><span data-stu-id="a9b38-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="a9b38-145">Digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a9b38-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="a9b38-146">Verificare che sia ActiveMasterFQDN che ActiveFileTransferAgents indichino il nome di dominio completo\_del pool di backup.</span><span class="sxs-lookup"><span data-stu-id="a9b38-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="a9b38-147">Infine, controlla lo stato della replica per tutti i server front-end digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a9b38-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="a9b38-148">Verificare che tutte le repliche abbiano il valore true.</span><span class="sxs-lookup"><span data-stu-id="a9b38-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="a9b38-149">Passare al passaggio 7 in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="a9b38-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="a9b38-150">Installare il Central Management store nel server back-end del pool\_di backup.</span><span class="sxs-lookup"><span data-stu-id="a9b38-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="a9b38-151">Eseguire prima di tutto il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a9b38-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="a9b38-152">Eseguire il comando successivo in uno dei server front-end del pool\_di backup per forzare lo stato di trasferimento di Central Management store:</span><span class="sxs-lookup"><span data-stu-id="a9b38-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="a9b38-153">Convalidare lo stato di trasferimento è completo:</span><span class="sxs-lookup"><span data-stu-id="a9b38-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="a9b38-154">Verificare che sia ActiveMasterFQDN che ActiveFileTransferAgents indichino il nome di dominio completo\_del pool di backup.</span><span class="sxs-lookup"><span data-stu-id="a9b38-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="a9b38-155">Controllare lo stato della replica per tutti i server front-end digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a9b38-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="a9b38-156">Verificare che tutte le repliche abbiano il valore true.</span><span class="sxs-lookup"><span data-stu-id="a9b38-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="a9b38-157">Installare il servizio Central Management Server nel resto dei server front-end nel pool di\_backup.</span><span class="sxs-lookup"><span data-stu-id="a9b38-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="a9b38-158">A tale scopo, eseguire il comando seguente in tutti i server front-end, ad eccezione di quello usato per forzare lo stato precedente della procedura:</span><span class="sxs-lookup"><span data-stu-id="a9b38-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="a9b38-159">Eseguire il failover degli utenti da pool1 a Pool2 eseguendo il cmdlet seguente in una finestra di Management Shell di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="a9b38-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="a9b38-160">Poiché la procedura adottata nelle parti precedenti di questa procedura per verificare lo stato dell'archivio di gestione centrale non è universale, è comunque possibile che il cmdlet non riesca perché l'archivio di gestione centrale non è ancora completamente riuscito.</span><span class="sxs-lookup"><span data-stu-id="a9b38-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="a9b38-161">In questo caso, è necessario correggere l'Central Management store in base ai messaggi di errore visualizzati e quindi eseguire di nuovo questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a9b38-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="a9b38-162">Se viene visualizzato il messaggio di errore seguente, è necessario modificare il pool di Edge in questo sito per usare un pool diverso come hop successivo prima di non superare il pool.</span><span class="sxs-lookup"><span data-stu-id="a9b38-162">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="a9b38-163">Per informazioni dettagliate, vedere le procedure all'inizio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a9b38-163">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="a9b38-164">Eseguire il failover di un pool</span><span class="sxs-lookup"><span data-stu-id="a9b38-164">Fail back a pool</span></span>

<span data-ttu-id="a9b38-165">Dopo che il pool che ha sperimentato il disastro è di nuovo online, ovvero pool1 in questo esempio, eseguire la procedura seguente per ripristinare lo stato di lavoro normale.</span><span class="sxs-lookup"><span data-stu-id="a9b38-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="a9b38-166">Tieni presente che il processo di failback richiede diversi minuti per il completamento.</span><span class="sxs-lookup"><span data-stu-id="a9b38-166">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="a9b38-167">Per riferimento, si prevede di richiedere fino a 60 minuti per un pool di utenti di 20.000.</span><span class="sxs-lookup"><span data-stu-id="a9b38-167">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="a9b38-168">Non è possibile eseguire il failover degli utenti che erano stati originariamente ospitati in pool1 e che non hanno eseguito il failover di Pool2 digitando il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="a9b38-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="a9b38-169">Nessun altro passaggio è necessario.</span><span class="sxs-lookup"><span data-stu-id="a9b38-169">No other steps are necessary.</span></span> <span data-ttu-id="a9b38-170">Se non è stato superato il server di gestione centrale, è possibile lasciarlo in Pool2.</span><span class="sxs-lookup"><span data-stu-id="a9b38-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="a9b38-171">Failover del pool di Edge usato per la Federazione di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a9b38-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="a9b38-172">Se il pool di Edge in cui è stata configurata la Federazione di Skype for Business Server si abbassa, è necessario cambiare la Federazione per usare un pool di bordi diverso per il lavoro della Federazione.</span><span class="sxs-lookup"><span data-stu-id="a9b38-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="a9b38-173">In un server front-end aprire Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="a9b38-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="a9b38-174">Espandere **pool di bordi**e quindi fare clic con il pulsante destro del mouse sul pool di Edge Server o Edge Server attualmente configurato per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="a9b38-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="a9b38-175">Selezionare **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="a9b38-176">In **modifica proprietà** in **generale**deselezionare **Abilita federazione per questo pool di bordi (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="a9b38-177">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-177">Click **OK**.</span></span>

3.  <span data-ttu-id="a9b38-178">Espandere **pool di bordi**e quindi fare clic con il pulsante destro del mouse sul pool di Edge Server o Edge Server che si desidera utilizzare per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="a9b38-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="a9b38-179">Selezionare **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="a9b38-180">In **modifica proprietà** in **generale**Selezionare **Abilita federazione per questo pool di bordi (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="a9b38-181">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-181">Click **OK**.</span></span>

5.  <span data-ttu-id="a9b38-182">Fare clic su **azione**, selezionare **topologia**, quindi **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-182">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="a9b38-183">Quando viene richiesto di **pubblicare la topologia**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-183">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="a9b38-184">Al termine della pubblicazione, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-184">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="a9b38-185">Nel server perimetrale aprire la distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a9b38-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="a9b38-186">Fare clic su **Installa o Aggiorna Skype for Business Server System**, quindi fare clic su **Imposta o Rimuovi componenti di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="a9b38-187">Fare di nuovo clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="a9b38-188">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-188">Click **Next**.</span></span> <span data-ttu-id="a9b38-189">La schermata di riepilogo mostrerà le azioni Man mano che vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="a9b38-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="a9b38-190">Dopo aver completato la distribuzione, fare clic su **Visualizza log** per visualizzare i file di log disponibili.</span><span class="sxs-lookup"><span data-stu-id="a9b38-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="a9b38-191">Fare clic su **fine** per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a9b38-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="a9b38-192">Se il sito che contiene il pool di Edge non riuscito contiene server front-end ancora in corso, è necessario aggiornare il servizio servizi di conferenza Web e il servizio di conferenza telefonica a/V in questi pool di front-end per usare un pool di Edge in un sito remoto ancora in corso.</span><span class="sxs-lookup"><span data-stu-id="a9b38-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="a9b38-193">Failover del pool di Edge usato per la Federazione XMPP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a9b38-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="a9b38-194">Nell'organizzazione esiste un pool di bordi designato come pool da usare per la Federazione XMPP.</span><span class="sxs-lookup"><span data-stu-id="a9b38-194">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="a9b38-195">Se il pool scende, è necessario eseguire il failover della Federazione XMPP per usare un pool di bordi diverso prima che la Federazione XMPP possa funzionare di nuovo.</span><span class="sxs-lookup"><span data-stu-id="a9b38-195">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="a9b38-196">La prima volta che si installano pool di bordi e si Abilita la Federazione XMPP, è possibile semplificare il processo di ripristino di emergenza impostando i record SRV DNS esterni per tutti i pool di Edge per la Federazione XMPP, anziché solo uno.</span><span class="sxs-lookup"><span data-stu-id="a9b38-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="a9b38-197">Ognuno di questi record SRV deve avere un set di priorità diverso.</span><span class="sxs-lookup"><span data-stu-id="a9b38-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="a9b38-198">Tutto il traffico federativo XMPP passa attraverso il pool con il record SRV con la massima priorità.</span><span class="sxs-lookup"><span data-stu-id="a9b38-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="a9b38-199">Nella procedura seguente, EdgePool1 è il pool che ospitava originariamente la Federazione XMPP e EdgePool2 è il pool che ora ospiterà la Federazione XMPP.</span><span class="sxs-lookup"><span data-stu-id="a9b38-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="a9b38-200">Per eseguire il failover del pool di Edge usato per la Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="a9b38-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="a9b38-201">Se non si dispone già di un altro pool di Edge distribuito, oltre a quello attualmente in calo, distribuire il pool.</span><span class="sxs-lookup"><span data-stu-id="a9b38-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="a9b38-202">In ogni Edge Server nel nuovo pool di Edge che ora ospiterà la Federazione XMPP (EdgePool2), eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="a9b38-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="a9b38-203">Eseguire il cmdlet seguente per reindirizzare la route federativo XMPP a EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="a9b38-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="a9b38-204">In questo esempio, sito2 è il sito che contiene il pool di bordi che ora ospiterà la route federativa XMPP e EdgeServer2.contoso.com è il nome di dominio completo di un server perimetrale in tale pool.</span><span class="sxs-lookup"><span data-stu-id="a9b38-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="a9b38-205">Nel server DNS esterno modificare il record DNS per la Federazione XMPP in punti a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a9b38-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="a9b38-206">Se non si ha già un record SRV DNS per la Federazione XMPP che si risolve nel pool di Edge che ora ospiterà la Federazione XMPP, è necessario aggiungerlo, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a9b38-206">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="a9b38-207">Questo record SRV deve avere un valore di porta 5269.</span><span class="sxs-lookup"><span data-stu-id="a9b38-207">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="a9b38-208">Verificare che il pool di Edge che ora ospita la Federazione XMPP contenga la porta 5269 aperta esternamente.</span><span class="sxs-lookup"><span data-stu-id="a9b38-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="a9b38-209">Avviare i servizi in tutti i server perimetrali nel pool di Edge, che ora ospiterà la Federazione XMPP:</span><span class="sxs-lookup"><span data-stu-id="a9b38-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="a9b38-210">Eseguire il failover del pool di Edge usato per la Federazione di Skype for Business Server o la Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="a9b38-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="a9b38-211">Dopo che un pool di Edge non riuscito usato per ospitare la Federazione è stato riportato online, usare questa procedura per non eseguire più la route federativa di Skype for Business Server e/o la route della Federazione XMPP per usare di nuovo questo pool di Edge ripristinato.</span><span class="sxs-lookup"><span data-stu-id="a9b38-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="a9b38-212">Nel pool di Edge ora disponibile di nuovo, avviare i servizi Edge.</span><span class="sxs-lookup"><span data-stu-id="a9b38-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="a9b38-213">Se si vuole ripristinare la route federativo di Skype for Business Server per l'uso del server perimetrale ripristinato, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9b38-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="a9b38-214">In un server front-end aprire Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="a9b38-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="a9b38-215">Espandere **pool di bordi**e quindi fare clic con il pulsante destro del mouse sull'Edge Server o sul pool di Edge Server attualmente configurato per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="a9b38-215">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="a9b38-216">Selezionare **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="a9b38-217">In **modifica proprietà** in **generale**deselezionare **Abilita federazione per questo pool di bordi (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="a9b38-218">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-218">Click **OK**.</span></span>
    
      - <span data-ttu-id="a9b38-219">Espandere **pool di bordi**e quindi fare clic con il pulsante destro del mouse sull'Edge Server o sul pool di Edge Server originale che si vuole usare per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="a9b38-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="a9b38-220">Selezionare **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="a9b38-221">In **modifica proprietà** in **generale**Selezionare **Abilita federazione per questo pool di bordi (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="a9b38-222">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-222">Click **OK**.</span></span>
    
      - <span data-ttu-id="a9b38-223">Fare clic su **azione**, selezionare **topologia**, quindi **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-223">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="a9b38-224">Quando viene richiesto di **pubblicare la topologia**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-224">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="a9b38-225">Al termine della pubblicazione, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-225">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="a9b38-226">Nel server perimetrale aprire la distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a9b38-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="a9b38-227">Fare clic su **Installa o Aggiorna Skype for Business Server System**, quindi fare clic su **Imposta o Rimuovi componenti di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="a9b38-228">Fare di nuovo clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="a9b38-229">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-229">Click **Next**.</span></span> <span data-ttu-id="a9b38-230">La schermata di riepilogo mostrerà le azioni Man mano che vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="a9b38-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="a9b38-231">Dopo aver completato la distribuzione, fare clic su **Visualizza log** per visualizzare i file di log disponibili.</span><span class="sxs-lookup"><span data-stu-id="a9b38-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="a9b38-232">Fare clic su **fine** per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a9b38-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="a9b38-233">Se si vuole eseguire il failover della route federativa XMPP per usare il server perimetrale ripristinato, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9b38-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="a9b38-234">Eseguire il cmdlet seguente per reindirizzare la route federativo XMPP al pool Edge che ora ospiterà la Federazione XMPP (in questo esempio, EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="a9b38-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="a9b38-235">In questo esempio, Microsoft1 è il sito che contiene il pool di bordi che ora ospiterà la route federativa XMPP e EdgeServer1.contoso.com è il nome di dominio completo di un server perimetrale in tale pool.</span><span class="sxs-lookup"><span data-stu-id="a9b38-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="a9b38-236">Se non si ha già un record SRV DNS per la Federazione XMPP che si risolve nel pool di Edge che ora ospiterà la Federazione XMPP, è necessario aggiungerlo, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a9b38-236">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="a9b38-237">Questo record SRV deve avere un valore di porta 5269.</span><span class="sxs-lookup"><span data-stu-id="a9b38-237">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="a9b38-238">Nel server DNS esterno modificare il record DNS per la Federazione XMPP in punti a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a9b38-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="a9b38-239">Verificare che il pool di Edge che ora ospita la Federazione XMPP contenga la porta 5269 aperta esternamente.</span><span class="sxs-lookup"><span data-stu-id="a9b38-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="a9b38-240">Se i pool Front-End sono rimasti in uso nel sito che contiene il pool di bordi non riuscito ed è stato ripristinato, è necessario aggiornare il servizio di Web Conferencing e il servizio di conferenza telefonica a/V in questi pool di front-end per usare di nuovo i pool di bordi nel sito locale.</span><span class="sxs-lookup"><span data-stu-id="a9b38-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="a9b38-241">Se il pool Front-end nello stesso sito del pool di Edge non è riuscito anche, è ora possibile usare Invoke-CsPoolFailback per non eseguire il backup del pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="a9b38-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="a9b38-242">Cambiare il pool di bordi associato a un pool Front-End</span><span class="sxs-lookup"><span data-stu-id="a9b38-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="a9b38-243">Se un pool di bordi scende ma il pool Front-end nello stesso sito è ancora in corso, è necessario impostare il pool Front-end in modo da usare un pool di Edge in un sito diverso fino a quando non viene ripristinato il pool di Edge non riuscito.</span><span class="sxs-lookup"><span data-stu-id="a9b38-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="a9b38-244">In Generatore di topologie passare al nome del pool Front-end che è necessario modificare.</span><span class="sxs-lookup"><span data-stu-id="a9b38-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="a9b38-245">Fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="a9b38-246">Nella sezione **associazioni** , in **associa Edge pool (per i componenti multimediali)**, usare la casella di controllo a discesa per selezionare il pool di bordi a cui si vuole associare questo pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="a9b38-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="a9b38-247">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9b38-247">Click **OK**.</span></span>
