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
ms.openlocfilehash: 1ebd4e8110b8783c869530d95eda0646a895b88e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826566"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="7f119-103">Failover e failover di un pool in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7f119-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="7f119-104">Utilizzare le procedure seguenti se un singolo pool Front End ha avuto esito negativo e non è più possibile eseguire il failover oppure il pool in cui è stata eseguita la catastrofe è tornato online ed è necessario ripristinare lo stato di funzionamento normale della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7f119-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="7f119-105">Informazioni su come eseguire il failover e il failback del pool di server perimetrali utilizzato per la Federazione di Skype for business o per la Federazione XMPP oppure per modificare il pool di server perimetrali associato a un pool Front end.</span><span class="sxs-lookup"><span data-stu-id="7f119-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="7f119-106">Failover di un pool Front End</span><span class="sxs-lookup"><span data-stu-id="7f119-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="7f119-107">Eseguire il failover di un pool</span><span class="sxs-lookup"><span data-stu-id="7f119-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="7f119-108">Failover del pool di server perimetrali utilizzato per la Federazione di Skype for business</span><span class="sxs-lookup"><span data-stu-id="7f119-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="7f119-109">Failover del pool di server perimetrali utilizzato per la Federazione XMPP in Skype for business</span><span class="sxs-lookup"><span data-stu-id="7f119-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="7f119-110">Eseguire il failover del pool di server perimetrali utilizzato per la Federazione di Skype for business o per la Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="7f119-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="7f119-111">Modificare il pool di server perimetrali associato a un pool Front End</span><span class="sxs-lookup"><span data-stu-id="7f119-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="7f119-112">Failover di un pool Front End</span><span class="sxs-lookup"><span data-stu-id="7f119-112">Fail over a Front End pool</span></span>

<span data-ttu-id="7f119-113">In questa procedura, Datacenter1 contiene Pool1 e l'errore si è verificato in Pool1.</span><span class="sxs-lookup"><span data-stu-id="7f119-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="7f119-114">Viene eseguito il failover su Pool2 situato in Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="7f119-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="7f119-115">La maggior parte del lavoro per il failover del pool comporta l'failover dell'archivio di gestione centrale, se necessario.</span><span class="sxs-lookup"><span data-stu-id="7f119-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="7f119-116">Questo è importante perché l'archivio di gestione centrale deve essere funzionale quando gli utenti del pool non sono più in grado di eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="7f119-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="7f119-p104">Inoltre, se si verifica un errore in un pool Front End ma il pool di server perimetrali presso il sito è ancora in esecuzione, è necessario sapere se quest'ultimo pool utilizza quello in cui si è verificato l'errore come pool hop successivo. In caso affermativo, è necessario impostare il pool di server perimetrali in modo da utilizzare un pool Front End diverso prima del failover del pool Front End in errore. La modifica dell'impostazione relativa all'hop successivo varia a seconda che sia utilizzato un pool che si trova nello stesso sito o in un sito diverso.</span><span class="sxs-lookup"><span data-stu-id="7f119-p104">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="7f119-120">**Per impostare un pool di server perimetrali per l'utilizzo di un pool di hop successivo nello stesso sito**</span><span class="sxs-lookup"><span data-stu-id="7f119-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="7f119-121">Aprire Generatore di topologie, fare clic con il pulsante destro del mouse sul pool di server perimetrali che deve essere modificato e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7f119-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="7f119-p105">Fare clic su **Hop successivo**. Nell'elenco **Pool hop successivo** selezionare il pool da utilizzare come pool hop successivo.</span><span class="sxs-lookup"><span data-stu-id="7f119-p105">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="7f119-124">Fare clic su **OK**, quindi pubblicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="7f119-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="7f119-125">**Per impostare un pool di server perimetrali per l'utilizzo di un pool hop successivo in un sito diverso**</span><span class="sxs-lookup"><span data-stu-id="7f119-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="7f119-126">Aprire una finestra di Skype for Business Server Management Shell e digitare il seguente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7f119-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="7f119-127">**Per eseguire il failover di un pool in un evento di emergenza**</span><span class="sxs-lookup"><span data-stu-id="7f119-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="7f119-128">Individuare il pool che ospita il server di gestione centrale digitando il cmdlet seguente in un front end server in Pool2:</span><span class="sxs-lookup"><span data-stu-id="7f119-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="7f119-129">I risultati di questo cmdlet mostrano quale pool ospita attualmente il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="7f119-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="7f119-130">Nella parte restante di questa procedura, questo pool è noto come \_ pool CMS.</span><span class="sxs-lookup"><span data-stu-id="7f119-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="7f119-131">Utilizzare Generatore di topologie per trovare la versione di Skype for Business Server in esecuzione nel \_ pool CMS.</span><span class="sxs-lookup"><span data-stu-id="7f119-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="7f119-132">Se è in esecuzione Skype for Business Server, utilizzare il cmdlet seguente per trovare il pool di backup del pool 1.</span><span class="sxs-lookup"><span data-stu-id="7f119-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="7f119-133">Fare in modo che \_ il pool di backup sia il pool di backup.</span><span class="sxs-lookup"><span data-stu-id="7f119-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="7f119-134">Controllare lo stato dell'archivio di gestione centrale con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="7f119-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="7f119-135">Questo cmdlet deve mostrare che sia ActiveMasterFQDN che ActiveFileTransferAgents puntano al nome di dominio completo del \_ pool CMS.</span><span class="sxs-lookup"><span data-stu-id="7f119-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="7f119-136">Se sono vuoti, il server di gestione centrale non è disponibile ed è necessario eseguirne il failover.</span><span class="sxs-lookup"><span data-stu-id="7f119-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="7f119-137">Se l'archivio di gestione centrale non è disponibile o se l'archivio di gestione centrale è in esecuzione su Pool1, ovvero il pool che ha avuto esito negativo, è necessario eseguire il failover del server di gestione centrale prima che venga eseguito il failover del pool.</span><span class="sxs-lookup"><span data-stu-id="7f119-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="7f119-138">Se è necessario eseguire il failover del server di gestione centrale ospitato in un pool che esegue Skype for Business Server, utilizzare il cmdlet nel passaggio 5 di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="7f119-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="7f119-139">Se non è necessario eseguire il failover del server di gestione centrale, passare al passaggio 7 di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="7f119-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="7f119-140">Per eseguire il failover dell'archivio di gestione centrale in un pool che esegue Skype for Business Server, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f119-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="7f119-141">Verificare innanzitutto quale server back-end \_ del pool di backup esegue l'istanza principale dell'archivio di gestione centrale digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7f119-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="7f119-142">Se il server back-end principale del \_ pool di backup è il principale, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7f119-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="7f119-143">Se il server back-end mirror del \_ pool di backup è il principale, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7f119-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="7f119-144">Verificare che il failover del server di gestione centrale sia stato completato.</span><span class="sxs-lookup"><span data-stu-id="7f119-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="7f119-145">Digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7f119-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="7f119-146">Verificare che sia ActiveMasterFQDN che ActiveFileTransferAgents puntino al nome di dominio completo del pool di backup \_ .</span><span class="sxs-lookup"><span data-stu-id="7f119-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="7f119-147">Infine, controllare lo stato della replica per tutti i Front End Server digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7f119-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="7f119-148">Verificare che il valore di tutte le repliche sia True.</span><span class="sxs-lookup"><span data-stu-id="7f119-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="7f119-149">Passare al passaggio 7 di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="7f119-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="7f119-150">Installare l'archivio di gestione centrale nel server back-end del \_ pool di backup.</span><span class="sxs-lookup"><span data-stu-id="7f119-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="7f119-151">Prima di tutto, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7f119-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="7f119-152">\_Per forzare lo spostamento dell'archivio di gestione centrale, eseguire il comando successivo in uno dei front end server del pool di backup:</span><span class="sxs-lookup"><span data-stu-id="7f119-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="7f119-153">Verificare che lo spostamento sia stato completato:</span><span class="sxs-lookup"><span data-stu-id="7f119-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="7f119-154">Verificare che sia ActiveMasterFQDN che ActiveFileTransferAgents puntino al nome di dominio completo del pool di backup \_ .</span><span class="sxs-lookup"><span data-stu-id="7f119-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="7f119-155">Controllare lo stato della replica per tutti i Front End Server digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7f119-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="7f119-156">Verificare che il valore di tutte le repliche sia True.</span><span class="sxs-lookup"><span data-stu-id="7f119-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="7f119-157">Installare il servizio server di gestione centrale nel resto dei front end server nel pool di backup \_ .</span><span class="sxs-lookup"><span data-stu-id="7f119-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="7f119-158">A tale scopo, eseguire il comando riportato di seguito in tutti i Front End Server, tranne quello utilizzato per forzare lo spostamento dell'archivio di gestione centrale in precedenza in questa procedura:</span><span class="sxs-lookup"><span data-stu-id="7f119-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="7f119-159">Eseguire il failover degli utenti da pool1 a Pool2 eseguendo il cmdlet seguente in una finestra della shell di gestione di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="7f119-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="7f119-160">Poiché le operazioni eseguite nelle parti precedenti di questa procedura per verificare lo stato dell'archivio di gestione centrale non sono universali, è comunque possibile che questo cmdlet non venga eseguito correttamente perché l'archivio di gestione centrale non è ancora completamente superato.</span><span class="sxs-lookup"><span data-stu-id="7f119-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="7f119-161">In questo caso, è necessario correggere l'archivio di gestione centrale in base ai messaggi di errore visualizzati e quindi eseguire di nuovo questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f119-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="7f119-p113">Se viene visualizzato il seguente messaggio di errore, è necessario impostare il pool di server perimetrali di questo sito in modo che utilizzi un pool diverso come hop successivo prima di eseguire il failover del pool. Per informazioni dettagliate, vedere la procedura all'inizio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7f119-p113">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="7f119-164">Eseguire il failover di un pool</span><span class="sxs-lookup"><span data-stu-id="7f119-164">Fail back a pool</span></span>

<span data-ttu-id="7f119-165">Dopo aver riportato online il pool in cui si è verificata la situazione di emergenza (ovvero Pool1 in questo esempio), eseguire le operazioni seguenti per ripristinare uno stato di funzionamento regolare per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7f119-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="7f119-166">Si noti che per il completamento del processo di failback sono richiesti vari minuti.</span><span class="sxs-lookup"><span data-stu-id="7f119-166">Note that the failback process takes several minute to complete.</span></span>  <span data-ttu-id="7f119-167">A titolo di riferimento, sono previsti fino a 60 minuti per un pool di 20.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="7f119-167">For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="7f119-168">Eseguire il failback degli utenti ospitati in origine in Pool1 e di cui è stato eseguito il failover in Pool2 digitando il comando di cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="7f119-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="7f119-169">Non sono necessari altri passaggi.</span><span class="sxs-lookup"><span data-stu-id="7f119-169">No other steps are necessary.</span></span> <span data-ttu-id="7f119-170">Se si è verificato un errore nel server di gestione centrale, è possibile lasciarlo in Pool2.</span><span class="sxs-lookup"><span data-stu-id="7f119-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="7f119-171">Failover del pool di server perimetrali utilizzato per la Federazione di Skype for business</span><span class="sxs-lookup"><span data-stu-id="7f119-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="7f119-172">Se il pool di server perimetrali in cui è configurata la Federazione di Skype for business è configurato, è necessario modificare la Federazione per utilizzare un pool di Edge diverso per il funzionamento della Federazione.</span><span class="sxs-lookup"><span data-stu-id="7f119-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="7f119-173">In un server Front End aprire il Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="7f119-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="7f119-174">Espandere **pool di server perimetrali** e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di computer perimetrali attualmente configurato per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="7f119-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="7f119-175">Scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7f119-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="7f119-176">In **Modifica proprietà** in **Generale** deselezionare **Abilita federazione per pool di server perimetrali (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="7f119-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="7f119-177">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f119-177">Click **OK**.</span></span>

3.  <span data-ttu-id="7f119-178">Espandere **pool di server perimetrali** e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di perimetro che si desidera utilizzare per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="7f119-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="7f119-179">Scegliere **Modifica proprietà**</span><span class="sxs-lookup"><span data-stu-id="7f119-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="7f119-p119">In **Modifica proprietà** in **Generale** selezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f119-p119">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="7f119-p120">Fare clic su **Azione**, selezionare **Topologia** e **Pubblica**. Quando viene richiesto in **Pubblicare la topologia** fare clic su **Avanti**. Dopo il completamento della pubblicazione fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="7f119-p120">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="7f119-185">Nel server perimetrale, aprire la distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7f119-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="7f119-186">Fare clic su **Installa o aggiorna il sistema di Skype for Business Server**, quindi fare clic su **installazione o rimozione componenti di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="7f119-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="7f119-187">Fare clic su **Riesegui**.</span><span class="sxs-lookup"><span data-stu-id="7f119-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="7f119-188">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7f119-188">Click **Next**.</span></span> <span data-ttu-id="7f119-189">Nella schermata di riepilogo verranno visualizzate le azioni in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7f119-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="7f119-190">Al termine della distribuzione, fare clic su **Visualizza log** per visualizzare i file di log disponibili.</span><span class="sxs-lookup"><span data-stu-id="7f119-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="7f119-191">Fare clic su **Fine** per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7f119-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="7f119-192">Se il sito che contiene il pool di server perimetrali in errore contiene Front End Server ancora in esecuzione, è necessario aggiornare il servizio Web Conferencing e il servizio A/V Conferencing in questi pool Front End per l'utilizzo di un pool di server perimetrali in un sito remoto ancora funzionante.</span><span class="sxs-lookup"><span data-stu-id="7f119-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="7f119-193">Failover del pool di server perimetrali utilizzato per la Federazione XMPP in Skype for business</span><span class="sxs-lookup"><span data-stu-id="7f119-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="7f119-p123">All'interno dell'organizzazione un solo pool di server perimetrali è designato come pool da usare per la federazione XMPP. Se questo pool non è disponibile, per consentire il funzionamento della federazione XMPP è necessario eseguire il failover di questa a un altro pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="7f119-p123">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="7f119-196">Quando si installano i pool di server perimetrali e si abilita la federazione XMPP per la prima volta, per semplificare il processo di ripristino di emergenza della federazione XMPP è possibile impostare record DNS SRV esterni per tutti i pool di server perimetrali, invece che per uno solo.</span><span class="sxs-lookup"><span data-stu-id="7f119-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="7f119-197">Per ciascuno di questi record SRV deve essere impostata una priorità diversa.</span><span class="sxs-lookup"><span data-stu-id="7f119-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="7f119-198">Tutto il traffico di federazione XMPP passa per il pool con il record SRV con la priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="7f119-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="7f119-199">Nella procedura seguente EdgePool1 è il pool di server perimetrali che ospita la federazione XMPP originariamente ed EdgePool2 è il pool che la ospiterà.</span><span class="sxs-lookup"><span data-stu-id="7f119-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="7f119-200">Per eseguire il failover del pool di server perimetrali utilizzato per la Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="7f119-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="7f119-201">Se oltre al pool di server perimetrali non disponibile non ne sono stati distribuiti altri, distribuirne uno.</span><span class="sxs-lookup"><span data-stu-id="7f119-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="7f119-202">In ogni server perimetrale del nuovo pool di server perimetrali che ora ospita la federazione XMPP (EdgePool2) eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="7f119-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="7f119-203">Eseguire il cmdlet seguente per puntare la route della federazione XMPP a EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="7f119-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="7f119-204">In questo esempio, Site2 è il sito che contiene il pool di server perimetrali che ospiterà la route della federazione XMPP ed EdgeServer2.contoso.com è l'FQDN di un server perimetrale del pool.</span><span class="sxs-lookup"><span data-stu-id="7f119-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="7f119-205">Nel server DNS esterno modificare il record DNS A in modo che la federazione XMPP punti a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7f119-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="7f119-p125">Se per la federazione XMPP non è disponibile un record DNS SRV corrispondente al pool di server perimetrali che ospiterà la federazione XMPP, è necessario aggiungerlo così com'è illustrato nell'esempio seguente. Il valore della porta del record SRV deve essere 5269.</span><span class="sxs-lookup"><span data-stu-id="7f119-p125">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="7f119-208">Verificare che il pool di server perimetrali che ospiterà la federazione XMPP abbia la porta 5269 aperta verso l'esterno.</span><span class="sxs-lookup"><span data-stu-id="7f119-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="7f119-209">Avviare i servizi in tutti i server perimetrali del pool che ospiterà la federazione XMPP:</span><span class="sxs-lookup"><span data-stu-id="7f119-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="7f119-210">Eseguire il failover del pool di server perimetrali utilizzato per la Federazione di Skype for business o per la Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="7f119-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="7f119-211">Dopo che un pool di server perimetrali non riusciti utilizzato per ospitare la Federazione è stato riportato online, utilizzare questa procedura per eseguire il failback della route di Federazione di Skype for business e/o della route di federazione XMPP per utilizzare di nuovo questo pool perimetrale ripristinato.</span><span class="sxs-lookup"><span data-stu-id="7f119-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="7f119-212">Avviare i servizi Edge nel pool di server perimetrali che è nuovamente disponibile.</span><span class="sxs-lookup"><span data-stu-id="7f119-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="7f119-213">Se si desidera eseguire il failback della route di Federazione di Skype for Business Server per l'utilizzo del server perimetrale ripristinato, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f119-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="7f119-p126">In un Front End Server aprire Generatore di topologie. Espandere **Pool di server perimetrali** e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali attualmente configurato per la federazione. Scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7f119-p126">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="7f119-p127">In **Generale** in **Modifica proprietà** deselezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f119-p127">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="7f119-p128">Espandere **Pool di server perimetrali** e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali originale che si desidera utilizzare di nuovo per la federazione. Scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7f119-p128">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="7f119-p129">In **Generale** in **Modifica proprietà** selezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f119-p129">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="7f119-p130">Fare clic su **Azione**, selezionare **Topologia** e **Pubblica**. Quando viene richiesto in **Pubblicare la topologia** fare clic su **Avanti**. Dopo il completamento della pubblicazione fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="7f119-p130">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="7f119-226">Nel server perimetrale, aprire la distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7f119-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="7f119-227">Fare clic su **Installa o aggiorna il sistema di Skype for Business Server**, quindi fare clic su **Imposta o Rimuovi componenti di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="7f119-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="7f119-228">Fare clic su **Riesegui**.</span><span class="sxs-lookup"><span data-stu-id="7f119-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="7f119-229">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7f119-229">Click **Next**.</span></span> <span data-ttu-id="7f119-230">Nella schermata di riepilogo verranno visualizzate le azioni in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7f119-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="7f119-231">Al termine della distribuzione, fare clic su **Visualizza log** per visualizzare i file di log disponibili.</span><span class="sxs-lookup"><span data-stu-id="7f119-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="7f119-232">Fare clic su **Fine** per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7f119-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="7f119-233">Se si desidera eseguire il failback della route di federazione XMPP per l'utilizzo del server perimetrale ripristinato, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f119-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="7f119-234">Eseguire il cmdlet seguente in modo che la route di federazione XMPP punti di nuovo al pool di server perimetrali che ospiterà la federazione XMPP, in questo esempio EdgeServer1:</span><span class="sxs-lookup"><span data-stu-id="7f119-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="7f119-235">In questo esempio Site1 indica il sito contenente il pool di server perimetrali che ospiterà ora la route di federazione XMPP, mentre EdgeServer1.contoso.com indica l'FQDN di un server perimetrale del pool.</span><span class="sxs-lookup"><span data-stu-id="7f119-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="7f119-p133">Se non si dispone già di un record SRV DNS per la federazione XMPP che viene risolto nel pool di server perimetrali che ospiterà ora la federazione XMPP, aggiungerlo come indicato nell'esempio seguente. Il valore di porta del record SRV deve essere 5269.</span><span class="sxs-lookup"><span data-stu-id="7f119-p133">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="7f119-238">Nel server DNS esterno modificare il record A DNS della federazione XMPP in modo che punti a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7f119-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="7f119-239">Verificare che la porta 5269 del pool di server perimetrali che ora ospita la federazione XMPP sia aperta esternamente.</span><span class="sxs-lookup"><span data-stu-id="7f119-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="7f119-240">Se i pool Front End sono rimasti in esecuzione nel sito contenente il pool di server perimetrali in cui si è verificato l'errore e che è stato ripristinato, aggiornare il servizio Web Conferencing e il servizio A/V Conferencing in questi pool Front End in modo che riutilizzino i pool di server perimetrali nel sito locale.</span><span class="sxs-lookup"><span data-stu-id="7f119-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="7f119-241">Se si era verificato un errore anche nel pool Front End nello stesso sito del pool di server perimetrali con errore, è ora possibile utilizzare Invoke–CsPoolFailback per eseguire il failback del pool Front End.</span><span class="sxs-lookup"><span data-stu-id="7f119-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="7f119-242">Modificare il pool di server perimetrali associato a un pool Front End</span><span class="sxs-lookup"><span data-stu-id="7f119-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="7f119-243">Se si verifica un'interruzione di un pool di server perimetrali di un sito, ma il pool Front End dello stesso sito è ancora in esecuzione, sarà necessario impostare il pool Front End in modo che venga utilizzato un pool di server perimetrali di un altro sito fino a quando il pool di server perimetrali non viene ripristinato.</span><span class="sxs-lookup"><span data-stu-id="7f119-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="7f119-244">Nel Generatore di topologie individuare il nome del pool Front End che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="7f119-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="7f119-245">Fare clic con il pulsante destro del mouse sul pool e scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7f119-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="7f119-246">Nella sezione **Associazioni**, in **Associa pool di server perimetrali (per componenti multimediali)**, usare la casella di riepilogo a discesa per selezionare il pool di server perimetrali a cui si vuole associare il pool Front End.</span><span class="sxs-lookup"><span data-stu-id="7f119-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="7f119-247">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f119-247">Click **OK**.</span></span>
