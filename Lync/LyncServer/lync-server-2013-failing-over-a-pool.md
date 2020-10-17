---
title: 'Lync Server 2013: failover di un pool'
description: 'Lync Server 2013: failover di un pool.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 819137c1277c5058f4e5d36ef5dbe71e672e8641
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554982"
---
# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="c6a34-103">Failover di un pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6a34-103">Failing over a pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6a34-104">_**Ultimo argomento modificato:** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="c6a34-104">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="c6a34-p101">Se si verifica un errore in un singolo pool Front End ed è necessario eseguirne il failover, utilizzare la procedura indicata di seguito. In questa procedura, Datacenter1 contiene Pool1 e l'errore si è verificato in Pool1. Viene eseguito il failover su Pool2 situato in Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="c6a34-p101">If a single Front End pool has failed and needs to be failed over, use the following procedure. In this procedure, Datacenter1 contains Pool1, and Pool1 has failed. You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="c6a34-108">La maggior parte del lavoro per il failover del pool comporta l'failover dell'archivio di gestione centrale, se necessario.</span><span class="sxs-lookup"><span data-stu-id="c6a34-108">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="c6a34-109">Questo è importante perché l'archivio di gestione centrale deve essere funzionale quando gli utenti del pool non sono più in grado di eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="c6a34-109">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="c6a34-p103">Inoltre, se si verifica un errore in un pool Front End ma il pool di server perimetrali presso il sito è ancora in esecuzione, è necessario sapere se quest'ultimo pool utilizza quello in cui si è verificato l'errore come pool hop successivo. In caso affermativo, è necessario impostare il pool di server perimetrali in modo da utilizzare un pool Front End diverso prima del failover del pool Front End in errore. La modifica dell'impostazione relativa all'hop successivo varia a seconda che sia utilizzato un pool che si trova nello stesso sito o in un sito diverso.</span><span class="sxs-lookup"><span data-stu-id="c6a34-p103">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="c6a34-113">**Per impostare un pool di server perimetrali per l'utilizzo di un pool hop successivo nello stesso sito**</span><span class="sxs-lookup"><span data-stu-id="c6a34-113">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="c6a34-114">Aprire Generatore di topologie, fare clic con il pulsante destro del mouse sul pool di server perimetrali che deve essere modificato e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c6a34-114">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="c6a34-p104">Fare clic su **Hop successivo**. Nell'elenco **Pool hop successivo** selezionare il pool da utilizzare come pool hop successivo.</span><span class="sxs-lookup"><span data-stu-id="c6a34-p104">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="c6a34-117">Fare clic su **OK**, quindi pubblicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="c6a34-117">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="c6a34-118">**Per impostare un pool di server perimetrali per l'utilizzo di un pool hop successivo in un sito diverso**</span><span class="sxs-lookup"><span data-stu-id="c6a34-118">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="c6a34-119">Aprire una finestra di Lync Server Management Shell e digitare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="c6a34-119">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="c6a34-120">**Per eseguire il failover di un pool in caso di emergenza**</span><span class="sxs-lookup"><span data-stu-id="c6a34-120">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="c6a34-121">Individuare il pool che ospita il server di gestione centrale digitando il cmdlet seguente in un front end server in Pool2:</span><span class="sxs-lookup"><span data-stu-id="c6a34-121">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="c6a34-122">I risultati di questo cmdlet mostrano quale pool ospita attualmente il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="c6a34-122">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="c6a34-123">Nella parte restante di questa procedura, questo pool è noto come \_ pool CMS.</span><span class="sxs-lookup"><span data-stu-id="c6a34-123">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="c6a34-124">Utilizzare Generatore di topologie per individuare la versione di Lync Server in esecuzione nel \_ pool CMS.</span><span class="sxs-lookup"><span data-stu-id="c6a34-124">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="c6a34-125">Se è in esecuzione Lync Server 2013, utilizzare il cmdlet seguente per individuare il pool di backup del pool 1.</span><span class="sxs-lookup"><span data-stu-id="c6a34-125">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="c6a34-126">Fare in modo che \_ il pool di backup sia il pool di backup.</span><span class="sxs-lookup"><span data-stu-id="c6a34-126">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="c6a34-127">Controllare lo stato dell'archivio di gestione centrale con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="c6a34-127">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="c6a34-128">Questo cmdlet deve mostrare che sia ActiveMasterFQDN che ActiveFileTransferAgents puntano al nome di dominio completo del \_ pool CMS.</span><span class="sxs-lookup"><span data-stu-id="c6a34-128">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="c6a34-129">Se sono vuoti, il server di gestione centrale non è disponibile ed è necessario eseguirne il failover.</span><span class="sxs-lookup"><span data-stu-id="c6a34-129">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="c6a34-130">Se l'archivio di gestione centrale non è disponibile o se l'archivio di gestione centrale è in esecuzione su Pool1, ovvero il pool che ha avuto esito negativo, è necessario eseguire il failover del server di gestione centrale prima che venga eseguito il failover del pool.</span><span class="sxs-lookup"><span data-stu-id="c6a34-130">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="c6a34-131">Se è necessario eseguire il failover del server di gestione centrale ospitato in un pool che esegue Lync Server 2013, utilizzare il cmdlet nel passaggio 5 di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="c6a34-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="c6a34-132">Se è necessario eseguire il failover del server di gestione centrale ospitato in un pool che esegue Lync Server 2010, utilizzare il cmdlet nel passaggio 6 di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="c6a34-132">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="c6a34-133">Se non è necessario eseguire il failover del server di gestione centrale, passare al passaggio 7 di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="c6a34-133">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="c6a34-134">Per eseguire il failover dell'archivio di gestione centrale in un pool che esegue Lync Server 2013, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c6a34-134">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="c6a34-135">Verificare innanzitutto quale server back-end \_ del pool di backup esegue l'istanza principale dell'archivio di gestione centrale digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c6a34-135">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="c6a34-136">Se il server back-end principale del \_ pool di backup è il principale, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c6a34-136">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="c6a34-137">Se il server back-end mirror del \_ pool di backup è il principale, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c6a34-137">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="c6a34-138">Verificare che il failover del server di gestione centrale sia stato completato.</span><span class="sxs-lookup"><span data-stu-id="c6a34-138">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="c6a34-139">Digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c6a34-139">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="c6a34-140">Verificare che sia ActiveMasterFQDN che ActiveFileTransferAgents puntino al nome di dominio completo del pool di backup \_ .</span><span class="sxs-lookup"><span data-stu-id="c6a34-140">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="c6a34-141">Infine, controllare lo stato della replica per tutti i Front End Server digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c6a34-141">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="c6a34-142">Verificare che il valore di tutte le repliche sia True.</span><span class="sxs-lookup"><span data-stu-id="c6a34-142">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="c6a34-143">Passare al passaggio 7 di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="c6a34-143">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="c6a34-144">Installare l'archivio di gestione centrale nel server back-end del \_ pool di backup.</span><span class="sxs-lookup"><span data-stu-id="c6a34-144">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="c6a34-145">Prima di tutto, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c6a34-145">First, run the following command:</span></span>
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="c6a34-146">\_Per forzare lo spostamento dell'archivio di gestione centrale, eseguire il comando successivo in uno dei front end server del pool di backup:</span><span class="sxs-lookup"><span data-stu-id="c6a34-146">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="c6a34-147">Verificare che lo spostamento sia stato completato:</span><span class="sxs-lookup"><span data-stu-id="c6a34-147">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="c6a34-148">Verificare che sia ActiveMasterFQDN che ActiveFileTransferAgents puntino al nome di dominio completo del pool di backup \_ .</span><span class="sxs-lookup"><span data-stu-id="c6a34-148">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="c6a34-149">Controllare lo stato della replica per tutti i Front End Server digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c6a34-149">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="c6a34-150">Verificare che il valore di tutte le repliche sia True.</span><span class="sxs-lookup"><span data-stu-id="c6a34-150">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="c6a34-151">Installare il servizio server di gestione centrale nel resto dei front end server nel pool di backup \_ .</span><span class="sxs-lookup"><span data-stu-id="c6a34-151">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="c6a34-152">A tale scopo, eseguire il comando riportato di seguito in tutti i Front End Server, tranne quello utilizzato per forzare lo spostamento dell'archivio di gestione centrale in precedenza in questa procedura:</span><span class="sxs-lookup"><span data-stu-id="c6a34-152">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="c6a34-153">Eseguire il failover degli utenti da pool1 a Pool2 eseguendo il cmdlet seguente in una finestra di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="c6a34-153">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="c6a34-154">Poiché le operazioni eseguite nelle parti precedenti di questa procedura per verificare lo stato dell'archivio di gestione centrale non sono universali, è comunque possibile che questo cmdlet non venga eseguito correttamente perché l'archivio di gestione centrale non è ancora completamente superato.</span><span class="sxs-lookup"><span data-stu-id="c6a34-154">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="c6a34-155">In questo caso, è necessario correggere l'archivio di gestione centrale in base ai messaggi di errore visualizzati e quindi eseguire di nuovo questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c6a34-155">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="c6a34-p112">Se viene visualizzato il seguente messaggio di errore, è necessario impostare il pool di server perimetrali di questo sito in modo che utilizzi un pool diverso come hop successivo prima di eseguire il failover del pool. Per informazioni dettagliate, vedere la procedura all'inizio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c6a34-p112">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

