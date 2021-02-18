---
title: Eseguire failover e failback di un pool
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: 547a71f44fa81f9ba12a1c661465c7b8604b3fa1
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278676"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="3b6e4-103">Failover e failback di un pool in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3b6e4-103">Failing over and failing back a pool in Skype for Business Server</span></span>

<span data-ttu-id="3b6e4-104">Utilizzare le procedure seguenti se un singolo pool di Front-End ha avuto esito negativo ed è necessario eseguire il backup oppure se il pool in cui si è verificata l'emergenza è di nuovo online ed è necessario ripristinare lo stato di lavoro normale della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-104">Use the following procedures if a single Front-End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="3b6e4-105">Informazioni su come eseguire il failover e il fail back del pool di server perimetrali utilizzato per la federazione di Skype for Business o la federazione XMPP oppure modificare il pool di server perimetrali associato a un pool Front-End server.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-105">Learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front-End pool.</span></span>

- [<span data-ttu-id="3b6e4-106">Eseguire il failover di un pool Front End</span><span class="sxs-lookup"><span data-stu-id="3b6e4-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="3b6e4-107">Fail back di un pool</span><span class="sxs-lookup"><span data-stu-id="3b6e4-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="3b6e4-108">Eseguire il failover del pool di server perimetrali utilizzato per la federazione di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3b6e4-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="3b6e4-109">Eseguire il failover del pool di server perimetrali utilizzato per la federazione XMPP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3b6e4-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="3b6e4-110">Fail back del pool di server perimetrali utilizzato per la federazione di Skype for Business Server o la federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="3b6e4-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="3b6e4-111">Modificare il pool di server perimetrali associato a un pool Front End</span><span class="sxs-lookup"><span data-stu-id="3b6e4-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="3b6e4-112">Eseguire il failover di Front-End pool</span><span class="sxs-lookup"><span data-stu-id="3b6e4-112">Fail over a Front-End pool</span></span>

<span data-ttu-id="3b6e4-113">Datacenter1 contiene Pool1 e Pool1 non riuscito.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-113">Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="3b6e4-114">Si sta per eseguire il failover a Pool2 che si trova in Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-114">You're failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="3b6e4-115">La maggior parte del lavoro per il failover del pool implica il failover dell'archivio di gestione centrale, se necessario.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-115">Most of the work for the pool failover involves failing over the Central Management store, if it's required.</span></span> <span data-ttu-id="3b6e4-116">L'archivio di gestione centrale deve essere funzionante quando si esegue il failed over degli utenti del pool.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-116">The Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="3b6e4-117">Se un pool di Front-End ha esito negativo, ma il pool di server perimetrali in tale sito è ancora in esecuzione, è necessario sapere se il pool di server perimetrali utilizza il pool con errori come pool hop successivo.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-117">If a Front-End pool fails, but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="3b6e4-118">In caso contrario, è necessario modificare il pool di server perimetrali in modo che utilizzi un pool di Front-End diverso prima di eseguire il failover del pool di Front-End non riuscito.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-118">If it does, you must change the Edge pool to use a different Front-End pool before failing over the failed Front-End pool.</span></span> <span data-ttu-id="3b6e4-119">La modifica dell'impostazione relativa all'hop successivo varia a seconda che sia utilizzato un pool che si trova nello stesso sito o in un sito diverso.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="3b6e4-120">**Per impostare un pool di server perimetrali per l'utilizzo di un pool di hop successivo nello stesso sito**</span><span class="sxs-lookup"><span data-stu-id="3b6e4-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1. <span data-ttu-id="3b6e4-121">Aprire Generatore di topologie, fare clic con il pulsante destro del mouse sul pool di server perimetrali da modificare e scegliere **Modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="3b6e4-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and select **Edit Properties**.</span></span>

2. <span data-ttu-id="3b6e4-122">Selezionare **Hop successivo.**</span><span class="sxs-lookup"><span data-stu-id="3b6e4-122">Select **Next Hop**.</span></span> <span data-ttu-id="3b6e4-123">**Nell'elenco Pool hop successivo selezionare** il pool che verrà ora utilizzato come pool hop successivo.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-123">From the **Next hop pool:** list, select the pool that will now serve as the next hop pool.</span></span>

3. <span data-ttu-id="3b6e4-124">Selezionare **OK** e quindi pubblicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-124">Select **OK**, and then publish the changes.</span></span>

<span data-ttu-id="3b6e4-125">**Per impostare un pool di server perimetrali per l'utilizzo di un pool di hop successivo in un sito diverso**</span><span class="sxs-lookup"><span data-stu-id="3b6e4-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1. <span data-ttu-id="3b6e4-126">Aprire una finestra di Skype for Business Server Management Shell e digitare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>

        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="3b6e4-127">**Per eseguire il failover di un pool in caso di emergenza**</span><span class="sxs-lookup"><span data-stu-id="3b6e4-127">**To fail over a pool in a disaster**</span></span>

1. <span data-ttu-id="3b6e4-128">Trovare il pool di host per il server di gestione centrale digitando il cmdlet seguente in un server Front-End in Pool2:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-128">Find the host pool for the Central Management Server by typing the following cmdlet on a Front-End server in Pool2:</span></span>

        Invoke-CsManagementServerFailover -Whatif

    <span data-ttu-id="3b6e4-129">I risultati di questo cmdlet mostrano quale pool ospita attualmente il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="3b6e4-130">Nella parte restante di questa procedura, questo pool è noto come \_ pool CMS.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2. <span data-ttu-id="3b6e4-131">Utilizzare Generatore di topologie per trovare la versione di Skype for Business Server in esecuzione nel \_ pool CMS.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="3b6e4-132">Se è in esecuzione Skype for Business Server, utilizzare il cmdlet seguente per trovare il pool di backup del pool 1.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-132">If it's running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>

        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>

    <span data-ttu-id="3b6e4-133">Consentire al \_ pool di backup di essere il pool di backup.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-133">Let Backup\_Pool be the backup pool.</span></span>

3. <span data-ttu-id="3b6e4-134">Controllare lo stato dell'archivio di gestione centrale con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-134">Check the status of the Central Management store with the following cmdlet:</span></span>

        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 

    <span data-ttu-id="3b6e4-135">Questo cmdlet dovrebbe mostrare che sia ActiveMasterFQDN che ActiveFileTransferAgents puntano al nome di dominio completo del \_ pool CMS.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="3b6e4-136">Se sono vuoti, il server di gestione centrale non è disponibile ed è necessario eseguire il failover.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="3b6e4-137">Se l'archivio di gestione centrale non è disponibile o se l'archivio di gestione centrale era in esecuzione in Pool1, ovvero il pool che ha avuto esito negativo, è necessario eseguire il failover del server di gestione centrale prima di eseguire il failover del pool.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="3b6e4-138">Se è necessario eseguire il failover del server di gestione centrale ospitato in un pool che esegue Skype for Business Server, utilizzare il cmdlet nel passaggio 5 di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="3b6e4-139">Se non è necessario eseguire il failover del server di gestione centrale, andare al passaggio 7 di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="3b6e4-140">Per eseguire il failover dell'archivio di gestione centrale in un pool che esegue Skype for Business Server, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>

      - <span data-ttu-id="3b6e4-141">Verificare innanzitutto quale Back-End server nel pool di backup esegue l'istanza principale dell'archivio di gestione \_ centrale digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-141">First, check which Back-End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>

            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="3b6e4-142">Se il server Back-End principale nel pool di backup \_ è l'entità, digitare:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-142">If the primary Back-End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="3b6e4-143">Se il server Back-End mirror nel pool di backup \_ è l'entità, digitare:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-143">If the mirror Back-End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="3b6e4-144">Verificare che il failover del server di gestione centrale sia stato completato.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="3b6e4-145">Digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-145">Type the following command:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="3b6e4-146">Verificare che ActiveMasterFQDN e ActiveFileTransferAgents puntino al nome di dominio completo del pool di \_ backup.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="3b6e4-147">Infine, controllare lo stato della replica per Front-End server digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-147">Finally, check the replica status for all Front-End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="3b6e4-148">Verificare che il valore di tutte le repliche sia True.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="3b6e4-149">Passare al passaggio 7 di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="3b6e4-150">Installare l'archivio di gestione centrale nel server back-end del pool di \_ backup.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="3b6e4-151">Prima di tutto, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="3b6e4-152">Eseguire il comando successivo in uno dei Front End Server del pool di backup per forzare lo \_ spostamento dell'archivio di gestione centrale:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="3b6e4-153">Verificare che lo spostamento sia stato completato:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="3b6e4-154">Verificare che ActiveMasterFQDN e ActiveFileTransferAgents puntino al nome di dominio completo del pool di \_ backup.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="3b6e4-155">Controllare lo stato della replica per tutti i Front End Server digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="3b6e4-156">Verificare che il valore di tutte le repliche sia True.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="3b6e4-157">Installare il servizio Server di gestione centrale nel resto dei Front End Server nel pool di \_ backup.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="3b6e4-158">A tale scopo, eseguire il comando seguente in tutti i Front End Server, ad eccezione di quello utilizzato per forzare lo spostamento dell'archivio di gestione centrale in precedenza in questa procedura:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="3b6e4-159">Eseguire il failover degli utenti da Pool1 a Pool2 eseguendo il cmdlet seguente in una finestra di Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="3b6e4-160">Poiché i passaggi evasi nelle parti precedenti di questa procedura per verificare lo stato dell'archivio di gestione centrale non sono universali, è comunque possibile che il cmdlet non riesca perché non è ancora stato eseguito il failover completo dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="3b6e4-161">In questo caso, è necessario correggere l'archivio di gestione centrale in base ai messaggi di errore visualizzati e quindi eseguire di nuovo questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="3b6e4-p113">Se viene visualizzato il seguente messaggio di errore, è necessario impostare il pool di server perimetrali di questo sito in modo che utilizzi un pool diverso come hop successivo prima di eseguire il failover del pool. Per informazioni dettagliate, vedere la procedura all'inizio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-p113">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="3b6e4-164">Fail back di un pool</span><span class="sxs-lookup"><span data-stu-id="3b6e4-164">Fail back a pool</span></span>

<span data-ttu-id="3b6e4-165">Dopo aver riportato online il pool in cui si è verificata la situazione di emergenza (ovvero Pool1 in questo esempio), eseguire le operazioni seguenti per ripristinare uno stato di funzionamento regolare per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="3b6e4-166">Il completamento del processo di failback richiede alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-166">The failback process takes several minute to complete.</span></span> <span data-ttu-id="3b6e4-167">Per riferimento, sono previsti fino a 60 minuti per un pool di 20.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-167">For reference, it's expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="3b6e4-168">Eseguire il failback degli utenti ospitati in origine in Pool1 e di cui è stato eseguito il failover in Pool2 digitando il comando di cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="3b6e4-169">Non sono necessari altri passaggi.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-169">No other steps are necessary.</span></span> <span data-ttu-id="3b6e4-170">Se è stato superato il server di gestione centrale, è possibile lasciarlo in Pool2.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="3b6e4-171">Eseguire il failover del pool di server perimetrali utilizzato per la federazione di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3b6e4-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="3b6e4-172">Se il pool di server perimetrali in cui è configurata la federazione di Skype for Business Server non funziona, è necessario modificare la federazione per utilizzare un pool di server perimetrali diverso per il funzionamento della federazione.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="3b6e4-173">In un server Front End aprire il Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="3b6e4-174">Espandere **Pool di server** perimetrali e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali attualmente configurato per la federazione.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="3b6e4-175">Scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="3b6e4-176">In **Modifica proprietà** in **Generale** deselezionare **Abilita federazione per pool di server perimetrali (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="3b6e4-177">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-177">Select **OK**.</span></span>

3.  <span data-ttu-id="3b6e4-178">Espandere **Pool di server** perimetrali e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali che si desidera utilizzare per la federazione.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="3b6e4-179">Scegliere **Modifica proprietà**</span><span class="sxs-lookup"><span data-stu-id="3b6e4-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="3b6e4-180">In **Modifica proprietà** in **Generale** selezionare **Abilita federazione per pool di server perimetrali (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="3b6e4-181">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-181">Select **OK**.</span></span>

5.  <span data-ttu-id="3b6e4-182">Selezionare **Azione**, **Topologia e** Pubblica. </span><span class="sxs-lookup"><span data-stu-id="3b6e4-182">Select **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="3b6e4-183">Quando viene richiesto di **pubblicare la topologia,** selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="3b6e4-183">When prompted on **Publish the topology**, select **Next**.</span></span> <span data-ttu-id="3b6e4-184">Al termine della pubblicazione, selezionare **Fine.**</span><span class="sxs-lookup"><span data-stu-id="3b6e4-184">When the Publish is finished, select **Finish**.</span></span>

6.  <span data-ttu-id="3b6e4-185">Nel server perimetrale, aprire la distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="3b6e4-186">Selezionare **Installa o aggiorna il sistema Skype for Business Server** e quindi selezionare Installazione o Rimozione componenti di Skype for Business **Server.**</span><span class="sxs-lookup"><span data-stu-id="3b6e4-186">Select **Install or Update Skype for Business Server System**, and then select **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="3b6e4-187">Selezionare **Esegui di nuovo.**</span><span class="sxs-lookup"><span data-stu-id="3b6e4-187">Select **Run Again**.</span></span>

7.  <span data-ttu-id="3b6e4-188">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-188">Select **Next**.</span></span> <span data-ttu-id="3b6e4-189">Nella schermata di riepilogo sono mostrate le azioni che vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="3b6e4-190">Al termine della distribuzione, selezionare **Visualizza registro per** visualizzare i file di registro disponibili.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-190">Once the deployment is done, select **View Log** to view available log files.</span></span> <span data-ttu-id="3b6e4-191">Selezionare **Fine** per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-191">Select **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="3b6e4-192">Se il sito contenente il pool di server perimetrali con problemi contiene Front End Server ancora in esecuzione, è necessario aggiornare il servizio Web Conferencing e il servizio A/V Conferencing in questi pool di Front-End per utilizzare un pool di server perimetrali in un sito remoto ancora in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front-End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="3b6e4-193">Eseguire il failover del pool di server perimetrali utilizzato per la federazione XMPP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3b6e4-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="3b6e4-p123">All'interno dell'organizzazione un solo pool di server perimetrali è designato come pool da usare per la federazione XMPP. Se questo pool non è disponibile, per consentire il funzionamento della federazione XMPP è necessario eseguire il failover di questa a un altro pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-p123">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="3b6e4-196">Quando si installano i pool di server perimetrali e si abilita la federazione XMPP per la prima volta, per semplificare il processo di ripristino di emergenza della federazione XMPP è possibile impostare record DNS SRV esterni per tutti i pool di server perimetrali, invece che per uno solo.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="3b6e4-197">Per ciascuno di questi record SRV deve essere impostata una priorità diversa.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="3b6e4-198">Tutto il traffico di federazione XMPP passa per il pool con il record SRV con la priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="3b6e4-199">Nella procedura seguente EdgePool1 è il pool, che originariamente ospitava la federazione XMPP, e EdgePool2 è il pool che ospiterà la federazione XMPP.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-199">In the following procedure, EdgePool1 is the pool, which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="3b6e4-200">Per eseguire il failover del pool di server perimetrali utilizzato per la federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="3b6e4-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="3b6e4-201">Se non è già stato distribuito un altro pool di server perimetrali (oltre a quello attualmente in esecuzione), distribuire tale pool.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-201">If you don’t already have another Edge pool deployed (besides the one that is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="3b6e4-202">In ogni server perimetrale del nuovo pool di server perimetrali che ora ospita la federazione XMPP (EdgePool2) eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="3b6e4-203">Eseguire il cmdlet seguente per puntare la route della federazione XMPP a EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="3b6e4-204">In questo esempio, Site2 è il sito che contiene il pool di server perimetrali che ospiterà la route della federazione XMPP ed EdgeServer2.contoso.com è l'FQDN di un server perimetrale del pool.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="3b6e4-205">Nel server DNS esterno modificare il record DNS A in modo che la federazione XMPP punti a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="3b6e4-p125">Se per la federazione XMPP non è disponibile un record DNS SRV corrispondente al pool di server perimetrali che ospiterà la federazione XMPP, è necessario aggiungerlo così com'è illustrato nell'esempio seguente. Il valore della porta del record SRV deve essere 5269.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-p125">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="3b6e4-208">Verificare che il pool di server perimetrali che ospiterà la federazione XMPP abbia la porta 5269 aperta verso l'esterno.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="3b6e4-209">Avviare i servizi in tutti i server perimetrali del pool che ospiterà la federazione XMPP:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="3b6e4-210">Fail back del pool di server perimetrali utilizzato per la federazione di Skype for Business Server o la federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="3b6e4-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="3b6e4-211">Dopo che un pool di server perimetrali non riuscito utilizzato per ospitare la federazione è stato riportato online, utilizzare questa procedura per eseguire il fail back della route di federazione di Skype for Business Server e/o la route di federazione XMPP per utilizzare di nuovo questo pool di server perimetrali ripristinato.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="3b6e4-212">Avviare i servizi Edge nel pool di server perimetrali che è nuovamente disponibile.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="3b6e4-213">Se si desidera eseguire il fail back della route di federazione di Skype for Business Server per utilizzare il server perimetrale ripristinato, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="3b6e4-214">In un server Front End aprire il Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="3b6e4-215">Espandere **Pool di server** perimetrali, quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali attualmente configurato per la federazione.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-215">Expand **Edge pools**, then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="3b6e4-216">Scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="3b6e4-217">In **Modifica proprietà** in **Generale** deselezionare **Abilita federazione per pool di server perimetrali (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="3b6e4-218">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-218">Select **OK**.</span></span>
    
      - <span data-ttu-id="3b6e4-219">Espandere **Pool di server** perimetrali, quindi fare clic con il pulsante destro del mouse sul server perimetrale originale o sul pool di server perimetrali che si desidera utilizzare di nuovo per la federazione.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-219">Expand **Edge pools**, then right-click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="3b6e4-220">Scegliere **Modifica proprietà**</span><span class="sxs-lookup"><span data-stu-id="3b6e4-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="3b6e4-221">In **Modifica proprietà** in **Generale** selezionare **Abilita federazione per pool di server perimetrali (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="3b6e4-222">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-222">Select **OK**.</span></span>
    
      - <span data-ttu-id="3b6e4-223">Selezionare **Azione**, **Topologia e** Pubblica. </span><span class="sxs-lookup"><span data-stu-id="3b6e4-223">Select **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="3b6e4-224">Quando viene richiesto di **pubblicare la topologia,** selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="3b6e4-224">When prompted on **Publish the topology**, select **Next**.</span></span> <span data-ttu-id="3b6e4-225">Al termine della pubblicazione, selezionare **Fine.**</span><span class="sxs-lookup"><span data-stu-id="3b6e4-225">When the Publish is finished, select **Finish**.</span></span>
    
      - <span data-ttu-id="3b6e4-226">Nel server perimetrale, aprire la distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="3b6e4-227">Seleziona **Installa o aggiorna il sistema Skype for Business Server,** quindi seleziona Installazione o Rimuovi componenti di Skype for Business **Server.**</span><span class="sxs-lookup"><span data-stu-id="3b6e4-227">Select **Install or Update Skype for Business Server System**, then select **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="3b6e4-228">Selezionare **Esegui di nuovo.**</span><span class="sxs-lookup"><span data-stu-id="3b6e4-228">Select **Run Again**.</span></span>
    
      - <span data-ttu-id="3b6e4-229">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-229">Select **Next**.</span></span> <span data-ttu-id="3b6e4-230">Nella schermata di riepilogo sono mostrate le azioni che vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="3b6e4-231">Al termine della distribuzione, selezionare **Visualizza registro per** visualizzare i file di registro disponibili.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-231">Once the deployment is done, select **View Log** to view available log files.</span></span> <span data-ttu-id="3b6e4-232">Selezionare **Fine** per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-232">Select **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="3b6e4-233">Se si desidera eseguire il failback della route di federazione XMPP per l'utilizzo del server perimetrale ripristinato, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="3b6e4-234">Eseguire il cmdlet seguente in modo che la route di federazione XMPP punti di nuovo al pool di server perimetrali che ospiterà la federazione XMPP, in questo esempio EdgeServer1:</span><span class="sxs-lookup"><span data-stu-id="3b6e4-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="3b6e4-235">In questo esempio Site1 indica il sito contenente il pool di server perimetrali che ospiterà ora la route di federazione XMPP, mentre EdgeServer1.contoso.com indica l'FQDN di un server perimetrale del pool.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="3b6e4-p133">Se non si dispone già di un record SRV DNS per la federazione XMPP che viene risolto nel pool di server perimetrali che ospiterà ora la federazione XMPP, aggiungerlo come indicato nell'esempio seguente. Il valore di porta del record SRV deve essere 5269.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-p133">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="3b6e4-238">Nel server DNS esterno modificare il record A DNS della federazione XMPP in modo che punti a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="3b6e4-239">Verificare che la porta 5269 del pool di server perimetrali che ora ospita la federazione XMPP sia aperta esternamente.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="3b6e4-240">Se i pool Front End sono rimasti in esecuzione nel sito contenente il pool di server perimetrali in cui si è verificato l'errore e che è stato ripristinato, aggiornare il servizio Web Conferencing e il servizio A/V Conferencing in questi pool Front End in modo che riutilizzino i pool di server perimetrali nel sito locale.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="3b6e4-241">Se si era verificato un errore anche nel pool Front End nello stesso sito del pool di server perimetrali con errore, è ora possibile utilizzare Invoke–CsPoolFailback per eseguire il failback del pool Front End.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="3b6e4-242">Modificare il pool di server perimetrali associato a un pool Front End</span><span class="sxs-lookup"><span data-stu-id="3b6e4-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="3b6e4-243">Se si verifica un'interruzione di un pool di server perimetrali di un sito, ma il pool Front End dello stesso sito è ancora in esecuzione, sarà necessario impostare il pool Front End in modo che venga utilizzato un pool di server perimetrali di un altro sito fino a quando il pool di server perimetrali non viene ripristinato.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="3b6e4-244">Nel Generatore di topologie individuare il nome del pool Front End che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="3b6e4-245">Fare clic con il pulsante destro del mouse sul pool e **quindi scegliere Modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="3b6e4-245">Right-click the pool, and then select **Edit Properties**.</span></span>

3.  <span data-ttu-id="3b6e4-246">Nella sezione **Associazioni**, in **Associa pool di server perimetrali (per componenti multimediali)**, usare la casella di riepilogo a discesa per selezionare il pool di server perimetrali a cui si vuole associare il pool Front End.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="3b6e4-247">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-247">Select **OK**.</span></span>
