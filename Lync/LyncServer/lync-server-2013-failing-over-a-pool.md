---
title: 'Lync Server 2013: Failover di un pool'
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
ms.openlocfilehash: ea66ae4a224d78e40a9fdb9de867d4738a5e3714
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="0cfc9-102">Failover di un pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0cfc9-102">Failing over a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cfc9-103">_**Argomento Ultima modifica:** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="0cfc9-103">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="0cfc9-104">Se un singolo pool Front-end non è riuscito e non è più necessario, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-104">If a single Front End pool has failed and needs to be failed over, use the following procedure.</span></span> <span data-ttu-id="0cfc9-105">In questa procedura, Datacenter1 contiene pool1 e pool1 non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-105">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="0cfc9-106">Non si riesce più a Pool2 situato in Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-106">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="0cfc9-107">La maggior parte del lavoro per il failover del pool comporta l'assenza di errori sopra l'Central Management store, se necessario.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-107">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="0cfc9-108">Questo è importante perché l'archivio di gestione centrale deve essere funzionale quando gli utenti del pool non riescono più.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-108">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="0cfc9-109">Inoltre, se un pool Front-end non riesce ma il pool di Edge in tale sito è ancora in corso, è necessario sapere se il pool di Edge usa il pool non riuscito come pool di hop successivo.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-109">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="0cfc9-110">In caso affermativo, è necessario modificare il pool di bordi per usare un pool Front-end diverso prima di non superare il pool Front-end non riuscito.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-110">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="0cfc9-111">La modalità di modifica dell'impostazione hop successiva varia a seconda che il bordo usi un pool nello stesso sito del pool di bordi o in un altro sito.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-111">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="0cfc9-112">**Per impostare un pool di bordi per l'uso di un pool di hop successivo nello stesso sito**</span><span class="sxs-lookup"><span data-stu-id="0cfc9-112">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="0cfc9-113">Aprire Generatore di topologia, fare clic con il pulsante destro del mouse sul pool di bordi che deve essere modificato e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-113">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="0cfc9-114">Fare clic su **hop successivo**.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-114">Click **Next Hop**.</span></span> <span data-ttu-id="0cfc9-115">Nell'elenco **hop successivo:** selezionare il pool che ora fungerà da pool hop successivo.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-115">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="0cfc9-116">Fare clic su **OK**e quindi pubblicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-116">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="0cfc9-117">**Per impostare un pool di bordi per l'uso di un pool di hop successivo in un altro sito**</span><span class="sxs-lookup"><span data-stu-id="0cfc9-117">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="0cfc9-118">Aprire una finestra di Lync Server Management Shell e digitare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="0cfc9-118">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="0cfc9-119">**Per eseguire il failover di un pool in un caso di emergenza**</span><span class="sxs-lookup"><span data-stu-id="0cfc9-119">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="0cfc9-120">Individuare il pool che ospita il server di gestione centralizzato digitando il cmdlet seguente in un server front-end in Pool2:</span><span class="sxs-lookup"><span data-stu-id="0cfc9-120">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="0cfc9-121">I risultati di questo cmdlet mostrano quale pool ospita attualmente il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-121">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="0cfc9-122">Nel resto della procedura questo pool è noto come pool di CMS\_.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-122">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="0cfc9-123">Usare generatore di topologie per trovare la versione di Lync Server in esecuzione\_nel pool di CMS.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-123">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="0cfc9-124">Se è in uso Lync Server 2013, usare il cmdlet seguente per trovare il pool di backup del pool 1.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-124">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="0cfc9-125">Consentire al\_pool di backup di essere il pool di backup.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-125">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="0cfc9-126">Controllare lo stato di Central Management Store con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="0cfc9-126">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="0cfc9-127">Questo cmdlet deve indicare che sia ActiveMasterFQDN che ActiveFileTransferAgents puntano al nome FQDN del pool\_di CMS.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-127">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="0cfc9-128">Se sono vuoti, il server di gestione centrale non è disponibile ed è necessario riuscire.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-128">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="0cfc9-129">Se l'archivio di gestione centrale non è disponibile o se l'archivio di gestione centrale è in esecuzione in pool1, ovvero il pool non è riuscito, è necessario eseguire il failover del server di gestione centralizzato prima di non riuscire nel pool.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-129">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="0cfc9-130">Se è necessario eseguire il failover del server di gestione centrale ospitato in un pool in cui è in esecuzione Lync Server 2013, usare il cmdlet nel passaggio 5 di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-130">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="0cfc9-131">Se è necessario eseguire il failover del server di gestione centrale ospitato in un pool in cui è in esecuzione Lync Server 2010, usare il cmdlet nel passaggio 6 di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="0cfc9-132">Se non è necessario eseguire il failover del server di gestione centrale, passare al passaggio 7 di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-132">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="0cfc9-133">Per eseguire il failover dell'Central Management store in un pool in cui è in esecuzione Lync Server 2013, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="0cfc9-133">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="0cfc9-134">Prima di tutto, controlla che il server back\_-end nel pool di backup esegua l'istanza principale di Central Management Store digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0cfc9-134">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="0cfc9-135">Se il server di back-end principale\_nel pool di backup è l'entità, digitare:</span><span class="sxs-lookup"><span data-stu-id="0cfc9-135">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="0cfc9-136">Se il server mirror back-end nel\_pool di backup è l'entità, digitare:</span><span class="sxs-lookup"><span data-stu-id="0cfc9-136">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="0cfc9-137">Verificare che il failover di Central Management Server sia completo.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-137">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="0cfc9-138">Digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0cfc9-138">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="0cfc9-139">Verificare che sia ActiveMasterFQDN che ActiveFileTransferAgents indichino il nome di dominio completo\_del pool di backup.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-139">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="0cfc9-140">Infine, controlla lo stato della replica per tutti i server front-end digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0cfc9-140">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="0cfc9-141">Verificare che tutte le repliche abbiano il valore true.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-141">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="0cfc9-142">Passare al passaggio 7 in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-142">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="0cfc9-143">Installare il Central Management store nel server back-end del pool\_di backup.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-143">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="0cfc9-144">Eseguire prima di tutto il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0cfc9-144">First, run the following command:</span></span>
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="0cfc9-145">Eseguire il comando successivo in uno dei server front-end del pool\_di backup per forzare lo stato di trasferimento di Central Management store:</span><span class="sxs-lookup"><span data-stu-id="0cfc9-145">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="0cfc9-146">Convalidare lo stato di trasferimento è completo:</span><span class="sxs-lookup"><span data-stu-id="0cfc9-146">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="0cfc9-147">Verificare che sia ActiveMasterFQDN che ActiveFileTransferAgents indichino il nome di dominio completo\_del pool di backup.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-147">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="0cfc9-148">Controllare lo stato della replica per tutti i server front-end digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0cfc9-148">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="0cfc9-149">Verificare che tutte le repliche abbiano il valore true.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-149">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="0cfc9-150">Installare il servizio Central Management Server nel resto dei server front-end nel pool di\_backup.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-150">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="0cfc9-151">A tale scopo, eseguire il comando seguente in tutti i server front-end, ad eccezione di quello usato per forzare lo stato precedente della procedura:</span><span class="sxs-lookup"><span data-stu-id="0cfc9-151">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="0cfc9-152">Eseguire il failover degli utenti da pool1 a Pool2 eseguendo il cmdlet seguente in una finestra di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="0cfc9-152">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="0cfc9-153">Poiché la procedura adottata nelle parti precedenti di questa procedura per verificare lo stato dell'archivio di gestione centrale non è universale, è comunque possibile che il cmdlet non riesca perché l'archivio di gestione centrale non è ancora completamente riuscito.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-153">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="0cfc9-154">In questo caso, è necessario correggere l'Central Management store in base ai messaggi di errore visualizzati e quindi eseguire di nuovo questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-154">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="0cfc9-155">Se viene visualizzato il messaggio di errore seguente, è necessario modificare il pool di Edge in questo sito per usare un pool diverso come hop successivo prima di non superare il pool.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-155">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="0cfc9-156">Per informazioni dettagliate, vedere le procedure all'inizio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0cfc9-156">For details, see the procedures at the beginning of this topic.</span></span>
    
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

