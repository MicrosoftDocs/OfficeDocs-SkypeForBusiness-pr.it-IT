---
title: Distribuire un gruppo di disponibilità Always On in un server back-end in Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Distribuire (installare) un gruppo di disponibilità Always On nella distribuzione di Skype for Business Server.
ms.openlocfilehash: 83565efe850570ac5ab9a0695757e708f3eae566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830656"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="82f81-103">Distribuire un gruppo di disponibilità Always On in un server back-end in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="82f81-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="82f81-104">Distribuire (installare) un gruppo di disponibilità Always On nella distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="82f81-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="82f81-105">La modalità di distribuzione di un gruppo di disponibilità varia a seconda che si distribuisca in un nuovo pool, in un pool esistente che utilizza il mirroring o in un pool esistente che attualmente non dispone di disponibilità elevata per il database back-end.</span><span class="sxs-lookup"><span data-stu-id="82f81-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="82f81-106">L'utilizzo di un gruppo di disponibilità con un ruolo del server Chat persistente non è supportato.</span><span class="sxs-lookup"><span data-stu-id="82f81-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="82f81-107">Distribuire un gruppo di disponibilità Always On in un nuovo pool Front End</span><span class="sxs-lookup"><span data-stu-id="82f81-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="82f81-108">Distribuire un gruppo di disponibilità Always On in un pool esistente che utilizza il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="82f81-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="82f81-109">Distribuire un gruppo di disponibilità Always On in un pool esistente che non utilizza il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="82f81-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="82f81-110">Distribuire un gruppo di disponibilità Always On in un nuovo pool Front End</span><span class="sxs-lookup"><span data-stu-id="82f81-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="82f81-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="82f81-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span></span>

1. <span data-ttu-id="82f81-112">Abilitare la funzionalità Clustering di failover in tutti i server di database che fanno parte del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="82f81-113">In ogni server eseguire le operazioni seguenti</span><span class="sxs-lookup"><span data-stu-id="82f81-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="82f81-114">Aprire Server Manager e fare clic **su Aggiungi ruoli e funzionalità.**</span><span class="sxs-lookup"><span data-stu-id="82f81-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="82f81-115">Fare **clic su** Avanti fino a raggiungere la casella **Seleziona** funzionalità.</span><span class="sxs-lookup"><span data-stu-id="82f81-115">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="82f81-116">In questo caso, selezionare la **casella di controllo Clustering** di failover.</span><span class="sxs-lookup"><span data-stu-id="82f81-116">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="82f81-117">Nella casella **Add features that are required for Failover Clustering?** fare clic su Add **Features.**</span><span class="sxs-lookup"><span data-stu-id="82f81-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="82f81-118">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="82f81-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="82f81-119">Convalidare la configurazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="82f81-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="82f81-120">In Server Manager scegliere Gestione **cluster** di failover dal menu **Strumenti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="82f81-121">In **Azioni sul** lato destro dello schermo fare clic su Convalida **configurazione.**</span><span class="sxs-lookup"><span data-stu-id="82f81-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="82f81-122">Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-123">Selezionare i server da aggiungere al cluster e quindi fare clic **su Esegui tutti i test.**</span><span class="sxs-lookup"><span data-stu-id="82f81-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="82f81-124">Nella casella **Riepilogo** controllare gli eventuali errori rilevati dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="82f81-124">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="82f81-125">Fare quindi **clic su Fine** per completare la convalida.</span><span class="sxs-lookup"><span data-stu-id="82f81-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="82f81-126">La procedura guidata probabilmente segnala diversi avvisi, soprattutto se non si utilizza l'archiviazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="82f81-126">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="82f81-127">Non è necessario utilizzare l'archiviazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="82f81-127">You are not required to use shared storage.</span></span> <span data-ttu-id="82f81-128">Tuttavia, se vengono visualizzati messaggi **di** errore, è necessario risolvere tali problemi prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="82f81-128">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="82f81-129">Creare il cluster di failover di Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="82f81-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="82f81-130">Nella procedura **guidata Gestione cluster di failover** fare clic con il pulsante destro del mouse su Gestione cluster di **failover** e quindi scegliere **Crea cluster.**</span><span class="sxs-lookup"><span data-stu-id="82f81-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="82f81-131">Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-132">Aggiungere il nome del cluster e l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="82f81-132">Add the cluster name and IP address.</span></span> <span data-ttu-id="82f81-133">Dopo la convalida delle impostazioni, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-133">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-134">Nella pagina Conferma, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-135">Dopo aver creato il cluster, fare clic su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="82f81-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="82f81-136">È consigliabile configurare le impostazioni del quorum del cluster per l'utilizzo di un controllo della condivisione file.</span><span class="sxs-lookup"><span data-stu-id="82f81-136">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="82f81-137">A tale scopo, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="82f81-137">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="82f81-138">Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **Altre azioni** e fare clic su Configura impostazioni **quorum cluster.**</span><span class="sxs-lookup"><span data-stu-id="82f81-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="82f81-139">Nella pagina **Selezione opzione di configurazione quorum** fare clic su Seleziona il controllo del **quorum.**</span><span class="sxs-lookup"><span data-stu-id="82f81-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="82f81-140">Nella pagina **Selezione quorum di controllo** fare clic su Configura un controllo della condivisione **file.**</span><span class="sxs-lookup"><span data-stu-id="82f81-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="82f81-141">Nella pagina **Configura condivisione file di controllo** digitare il percorso della condivisione file che si desidera utilizzare e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-142">Nella pagina **Conferma**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="82f81-143">In ogni server del cluster abilitare la funzionalità Di gruppo di disponibilità in SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="82f81-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="82f81-144">Aprire Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="82f81-144">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="82f81-145">Nell'albero sul lato sinistro dello schermo fare clic su **SQL Server Servizi** e quindi fare doppio clic sul SQL Server servizio.</span><span class="sxs-lookup"><span data-stu-id="82f81-145">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="82f81-146">Nella casella **Proprietà** selezionare la **scheda Disponibilità elevata AlwaysOn.** Selezionare la **casella di controllo Abilita gruppi di disponibilità AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="82f81-146">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="82f81-147">Riavviare SQL Server servizio quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="82f81-147">Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="82f81-148">Utilizzare Generatore di topologie per creare il pool Front End, come illustrato in Creare e pubblicare una nuova topologia [in Skype for Business Server.](../../deploy/install/create-and-publish-new-topology.md)</span><span class="sxs-lookup"><span data-stu-id="82f81-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="82f81-149">In questo caso, specificare il gruppo di disponibilità come SQL per il pool.</span><span class="sxs-lookup"><span data-stu-id="82f81-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="82f81-150">Creare il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="82f81-151">Apri SQL Server Management Studio e connettiti all'SQL Server istanza.</span><span class="sxs-lookup"><span data-stu-id="82f81-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="82f81-152">In Esplora oggetti espandere la **cartella Disponibilità elevata Always On.**</span><span class="sxs-lookup"><span data-stu-id="82f81-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="82f81-153">Fare clic con il pulsante destro **del** mouse sulla cartella Gruppi di disponibilità e scegliere **Creazione guidata nuovo gruppo di disponibilità.**</span><span class="sxs-lookup"><span data-stu-id="82f81-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="82f81-154">Se viene **visualizzata la** pagina Introduzione, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-155">Nella pagina **Specifica nome gruppo di** disponibilità digitare il nome del gruppo di disponibilità e fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-156">Nella pagina Selezione database selezionare i database che si desidera includere nel gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="82f81-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="82f81-157">Scegliere il pulsante **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="82f81-158">Non includere i **database ReportServer,** **ReportServerTempDB** o Persistent Chat nel gruppo di disponibilità AlwaysOn, in quanto non sono supportati in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="82f81-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="82f81-159">È possibile includere tutti gli altri database di Skype for Business Server nel gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="82f81-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="82f81-160">Nella pagina **Specifica repliche** fare clic sulla **scheda** Repliche. Fare quindi clic **sul pulsante Aggiungi** repliche e connettersi alle altre istanze SQL unite come nodi del cluster di failover di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="82f81-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="82f81-161">Per ogni istanza, selezionare le **opzioni Failover automatico** e **Commit** sincrono.</span><span class="sxs-lookup"><span data-stu-id="82f81-161">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="82f81-162">Non selezionare **l'opzione Secondaria leggibile.**</span><span class="sxs-lookup"><span data-stu-id="82f81-162">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="82f81-163">Fare clic **sulla scheda Endpoint** e verificare che il numero di **porta** sia impostato su 5022.</span><span class="sxs-lookup"><span data-stu-id="82f81-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="82f81-164">Fare clic **sulla scheda Listener** e selezionare l'opzione Crea listener del gruppo **di** disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-164">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="82f81-165">In tale opzione digitare un nome per il listener e impostare **la** porta su 1433 (altre porte non sono supportate per questa opzione).</span><span class="sxs-lookup"><span data-stu-id="82f81-165">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="82f81-166">Fare **clic su** Aggiungi e quindi nella casella Indirizzo **IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="82f81-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="82f81-167">Nella **pagina** Selezione sincronizzazione dati iniziale selezionare Completo e specificare una cartella accessibile alle repliche e per cui l'account di servizio SQL Server utilizzato da entrambe le repliche dispone delle autorizzazioni di scrittura.</span><span class="sxs-lookup"><span data-stu-id="82f81-167">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="82f81-168">Scegliere il pulsante **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-168">Then click **Next**.</span></span>
    
     <span data-ttu-id="82f81-169">Questa condivisione file verrà utilizzata temporaneamente quando si inizializzano i database.</span><span class="sxs-lookup"><span data-stu-id="82f81-169">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="82f81-170">Se si gestiscono database di grandi dimensioni, è consigliabile inizializzarli manualmente nel caso in cui la larghezza di banda di rete non possa contenere le dimensioni dei backup dei database.</span><span class="sxs-lookup"><span data-stu-id="82f81-170">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="82f81-171">Nella pagina Convalida verificare che tutti i controlli di convalida siano stati eseguiti correttamente e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-172">Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su Fine.</span><span class="sxs-lookup"><span data-stu-id="82f81-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="82f81-173">Dopo aver distribuito il pool e il gruppo di disponibilità del gruppo di disponibilità, eseguire alcuni passaggi finali per assicurarsi che gli account di accesso SQL siano presenti in ognuna delle repliche nel gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="82f81-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="82f81-174">Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente** e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="82f81-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="82f81-175">Espandere Skype for Business Server, espandere la topologia ed espandere SQL Server **store.**</span><span class="sxs-lookup"><span data-stu-id="82f81-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="82f81-176">Fare clic con il pulsante destro SQL'archivio del nuovo gruppo di disponibilità AlwaysOn e scegliere **Modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="82f81-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="82f81-177">Nella parte inferiore della pagina, nella casella **SQL Server FQDN,** modificare il valore in FQDN del listener del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="82f81-178">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="82f81-178">Publish the topology.</span></span> <span data-ttu-id="82f81-179">Scegliere **Topologia** dal menu Azione **e** quindi **Pubblica.**</span><span class="sxs-lookup"><span data-stu-id="82f81-179">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="82f81-180">Nella pagina di conferma fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-180">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="82f81-181">Attendere quindi alcuni minuti per la replica della nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="82f81-181">Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="82f81-182">Apri SQL Server Management Studio e passa al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="82f81-183">Eseguire il failover su una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="82f81-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="82f81-184">Aprire Skype for Business Server Management Shell e digitare il cmdlet seguente per creare SQL account di accesso in questa replica:</span><span class="sxs-lookup"><span data-stu-id="82f81-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="82f81-185">Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria, quindi utilizzare ) per  `Install-CsDatabase -Update` ogni replica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="82f81-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="82f81-186">Distribuire un gruppo di disponibilità Always On in un pool esistente che utilizza il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="82f81-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="82f81-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="82f81-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="82f81-188">Se il pool che si sta aggiornando a un gruppo di disponibilità ospita l'archivio di gestione centrale per l'organizzazione, è necessario spostare il Servizio di gestione catalogo in un altro pool prima di aggiornare il pool.</span><span class="sxs-lookup"><span data-stu-id="82f81-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="82f81-189">Utilizzare il cmdlet Move-CsManagementServer per spostare il pool.</span><span class="sxs-lookup"><span data-stu-id="82f81-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="82f81-190">Se nell'organizzazione non è presente un altro pool, è possibile distribuire temporaneamente un server Standard Edition e spostare il server CMS in questo server prima di aggiornare il pool al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="82f81-191">Eseguire il failover di tutti i dati dal mirror al nodo principale aprendo Skype for Business Server Management Shell e digitando il cmdlet seguente.</span><span class="sxs-lookup"><span data-stu-id="82f81-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="82f81-192">Ripetere questo cmdlet per ogni tipo di database nel pool.</span><span class="sxs-lookup"><span data-stu-id="82f81-192">Repeat this cmdlet for each database type in the pool.</span></span> <span data-ttu-id="82f81-193">È possibile utilizzare il cmdlet seguente per trovare tutti i tipi di database archiviati nel pool.</span><span class="sxs-lookup"><span data-stu-id="82f81-193">You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="82f81-194">Utilizzare Generatore di topologie per rimuovere il mirroring del database dal pool.</span><span class="sxs-lookup"><span data-stu-id="82f81-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="82f81-195">Apre lo strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="82f81-195">Open Topology Builder.</span></span> <span data-ttu-id="82f81-196">Nella topologia espandere Pool **Enterprise Edition Front End,** fare clic con il pulsante destro del mouse sul nome del pool e scegliere **Modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="82f81-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="82f81-197">Per ogni tipo di SQL di archiviazione nel pool, deselezionare la casella di controllo **SQL mirroring dello Store.**</span><span class="sxs-lookup"><span data-stu-id="82f81-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="82f81-198">Pubblicare la topologia modificata.</span><span class="sxs-lookup"><span data-stu-id="82f81-198">Publish the changed topology.</span></span> <span data-ttu-id="82f81-199">Scegliere **Topologia** dal menu Azione **e** quindi **Pubblica.**</span><span class="sxs-lookup"><span data-stu-id="82f81-199">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="82f81-200">Nella pagina di conferma fare clic su **Avanti**</span><span class="sxs-lookup"><span data-stu-id="82f81-200">Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="82f81-201">Usa SQL Server Management Studio per interrompere il mirroring.</span><span class="sxs-lookup"><span data-stu-id="82f81-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="82f81-202">Aprire SQL Server Management Studio, accedere ai database, fare clic con il pulsante destro del mouse su **Attività** e scegliere **Mirror.**</span><span class="sxs-lookup"><span data-stu-id="82f81-202">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**.</span></span> <span data-ttu-id="82f81-203">Fare clic **su Rimuovi mirroring** e quindi su **OK.**</span><span class="sxs-lookup"><span data-stu-id="82f81-203">Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="82f81-204">Ripetere questa operazione per tutti i database del pool che verranno convertiti in un gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="82f81-205">Configurare la funzionalità Clustering di failover in tutti i server di database che fanno parte del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="82f81-206">In ogni server eseguire le operazioni seguenti</span><span class="sxs-lookup"><span data-stu-id="82f81-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="82f81-207">Aprire Server Manager e fare clic **su Aggiungi ruoli e funzionalità.**</span><span class="sxs-lookup"><span data-stu-id="82f81-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="82f81-208">Fare **clic su** Avanti fino a raggiungere la casella **Seleziona** funzionalità.</span><span class="sxs-lookup"><span data-stu-id="82f81-208">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="82f81-209">In questo caso, selezionare la **casella di controllo Clustering** di failover.</span><span class="sxs-lookup"><span data-stu-id="82f81-209">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="82f81-210">Nella casella **Add features that are required for Failover Clustering?** fare clic su Add **Features.**</span><span class="sxs-lookup"><span data-stu-id="82f81-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="82f81-211">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="82f81-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="82f81-212">Convalidare la configurazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="82f81-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="82f81-213">In Server Manager scegliere Gestione **cluster** di failover dal menu **Strumenti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="82f81-214">In **Azioni sul** lato destro dello schermo fare clic su Convalida **configurazione.**</span><span class="sxs-lookup"><span data-stu-id="82f81-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="82f81-215">Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-216">Selezionare i server da aggiungere al cluster e quindi fare clic **su Esegui tutti i test.**</span><span class="sxs-lookup"><span data-stu-id="82f81-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="82f81-217">Nella casella **Riepilogo** controllare gli eventuali errori rilevati dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="82f81-217">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="82f81-218">Fare quindi **clic su Fine** per completare la convalida.</span><span class="sxs-lookup"><span data-stu-id="82f81-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="82f81-219">La procedura guidata probabilmente segnala diversi avvisi, soprattutto se non si utilizza l'archiviazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="82f81-219">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="82f81-220">Non è necessario utilizzare l'archiviazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="82f81-220">You are not required to use shared storage.</span></span> <span data-ttu-id="82f81-221">Tuttavia, se vengono visualizzati messaggi **di** errore, è necessario risolvere tali problemi prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="82f81-221">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="82f81-222">Creare il cluster di failover di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="82f81-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="82f81-223">Nella procedura **guidata Gestione cluster di failover** fare clic con il pulsante destro del mouse su Gestione cluster di **failover** e quindi scegliere **Crea cluster.**</span><span class="sxs-lookup"><span data-stu-id="82f81-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="82f81-224">Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-225">Aggiungere il nome del cluster e l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="82f81-225">Add the cluster name and IP address.</span></span> <span data-ttu-id="82f81-226">Dopo la convalida delle impostazioni, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-226">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-227">Nella pagina Conferma, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-228">Dopo aver creato il cluster, fare clic su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="82f81-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="82f81-229">È consigliabile configurare le impostazioni del quorum del cluster per l'utilizzo di un controllo della condivisione file.</span><span class="sxs-lookup"><span data-stu-id="82f81-229">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="82f81-230">A tale scopo, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="82f81-230">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="82f81-231">Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **Altre azioni** e fare clic su Configura impostazioni **quorum cluster.**</span><span class="sxs-lookup"><span data-stu-id="82f81-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="82f81-232">Nella pagina **Selezione opzione di configurazione quorum** fare clic su Seleziona il controllo del **quorum.**</span><span class="sxs-lookup"><span data-stu-id="82f81-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="82f81-233">Nella pagina **Selezione quorum di controllo** fare clic su Configura un controllo della condivisione **file.**</span><span class="sxs-lookup"><span data-stu-id="82f81-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="82f81-234">Nella pagina **Configura condivisione file di controllo** digitare il percorso della condivisione file che si desidera utilizzare e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-235">Nella pagina **Conferma**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="82f81-236">In ogni server del cluster abilitare la funzionalità Di gruppo di disponibilità in SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="82f81-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="82f81-237">Aprire Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="82f81-237">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="82f81-238">Nell'albero sul lato sinistro dello schermo fare clic su **SQL Server Servizi** e quindi fare doppio clic sul SQL Server servizio.</span><span class="sxs-lookup"><span data-stu-id="82f81-238">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="82f81-239">Nella casella **Proprietà** selezionare la **scheda Disponibilità elevata AlwaysOn.** Selezionare la **casella di controllo Abilita gruppi di disponibilità AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="82f81-239">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="82f81-240">Riavviare SQL Server servizio quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="82f81-240">Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="82f81-241">Creare il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="82f81-242">Apri SQL Server Management Studio e connettiti all'SQL Server istanza.</span><span class="sxs-lookup"><span data-stu-id="82f81-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="82f81-243">In Esplora oggetti espandere la **cartella Disponibilità elevata Always On.**</span><span class="sxs-lookup"><span data-stu-id="82f81-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="82f81-244">Fare clic con il pulsante destro **del** mouse sulla cartella Gruppi di disponibilità e scegliere **Creazione guidata nuovo gruppo di disponibilità.**</span><span class="sxs-lookup"><span data-stu-id="82f81-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="82f81-245">Se viene **visualizzata la** pagina Introduzione, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="82f81-246">Nella pagina **Specifica nome gruppo di** disponibilità digitare il nome del gruppo di disponibilità e fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="82f81-247">Nella pagina Selezione database selezionare i database che si desidera includere nel gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="82f81-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="82f81-248">Scegliere il pulsante **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="82f81-249">Non includere i **database ReportServer,** **ReportServerTempDB** o Persistent Chat nel gruppo di disponibilità AlwaysOn, in quanto non sono supportati in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="82f81-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="82f81-250">È possibile includere tutti gli altri database di Skype for Business Server nel gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="82f81-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="82f81-251">Nella pagina **Specifica repliche** fare clic sulla **scheda** Repliche. Fare quindi clic **sul pulsante Aggiungi** repliche e connettersi alle altre istanze SQL unite come nodi del cluster di failover di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="82f81-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="82f81-252">Per ogni istanza, selezionare le **opzioni Failover automatico** e **Commit** sincrono.</span><span class="sxs-lookup"><span data-stu-id="82f81-252">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="82f81-253">Non selezionare **l'opzione Secondaria leggibile.**</span><span class="sxs-lookup"><span data-stu-id="82f81-253">Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="82f81-254">Fare clic **sulla scheda Endpoint** e verificare che il numero di **porta** sia impostato su 5022.</span><span class="sxs-lookup"><span data-stu-id="82f81-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="82f81-255">Fare clic **sulla scheda Listener** e selezionare l'opzione Crea listener del gruppo **di** disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-255">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="82f81-256">In tale opzione digitare un nome per il listener e impostare **la** porta su 1433 (altre porte non sono supportate per questa opzione).</span><span class="sxs-lookup"><span data-stu-id="82f81-256">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="82f81-257">Fare **clic su** Aggiungi e quindi nella casella Indirizzo **IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="82f81-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="82f81-258">Nella **pagina** Selezione sincronizzazione dati iniziale selezionare Completo e specificare una cartella accessibile alle repliche e per cui l'account di servizio SQL Server utilizzato da entrambe le repliche dispone delle autorizzazioni di scrittura.</span><span class="sxs-lookup"><span data-stu-id="82f81-258">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="82f81-259">Scegliere il pulsante **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-259">Then click **Next**.</span></span>
    
    <span data-ttu-id="82f81-260">Questa condivisione file verrà utilizzata temporaneamente quando si inizializzano i database.</span><span class="sxs-lookup"><span data-stu-id="82f81-260">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="82f81-261">Se si gestiscono database di grandi dimensioni, è consigliabile inizializzarli manualmente nel caso in cui la larghezza di banda di rete non possa contenere le dimensioni dei backup dei database.</span><span class="sxs-lookup"><span data-stu-id="82f81-261">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="82f81-262">Nella pagina Convalida verificare che tutti i controlli di convalida siano stati eseguiti correttamente e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="82f81-263">Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su Fine.</span><span class="sxs-lookup"><span data-stu-id="82f81-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="82f81-264">Creare un nuovo archivio specificando il listener del gruppo di disponibilità del gruppo e specificare l'entità del mirror precedente come nodo primario del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="82f81-265">Apre lo strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="82f81-265">Open Topology Builder.</span></span> <span data-ttu-id="82f81-266">Nella topologia espandere Componenti **condivisi,** fare clic con il pulsante destro **del mouse** su SQL Server archivi e scegliere Nuovo **SQL Server Store.**</span><span class="sxs-lookup"><span data-stu-id="82f81-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="82f81-267">Nella pagina Definisci nuovo **SQL Store** selezionare  innanzitutto la casella di controllo Impostazioni disponibilità elevata e quindi verificare che i gruppi di disponibilità AlwaysOn SQL siano visualizzati nella casella di riepilogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="82f81-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="82f81-268">Nella casella **SQL Server FQDN listener** disponibilità digitare il nome di dominio completo del listener creato al momento della creazione del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="82f81-269">Nella casella **SQL Server FQDN** digitare l'FQDN del nodo primario del gruppo di disponibilità e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="82f81-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="82f81-270">Deve essere l'entità del mirror precedente per questo archivio.</span><span class="sxs-lookup"><span data-stu-id="82f81-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="82f81-271">Associare il nuovo gruppo di disponibilità al pool Front End.</span><span class="sxs-lookup"><span data-stu-id="82f81-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="82f81-272">In Generatore di topologie fare clic con il pulsante destro del mouse sul pool da associare al gruppo di disponibilità e scegliere **Modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="82f81-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="82f81-273">In **Associazioni,** nella casella SQL Server **Store,** selezionare il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="82f81-274">Selezionare lo stesso gruppo per tutti gli altri database del pool che si desidera spostare nel gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="82f81-275">Quando si è certi che tutti i database necessari siano impostati sul gruppo di disponibilità, fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="82f81-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="82f81-276">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="82f81-276">Publish the topology.</span></span> <span data-ttu-id="82f81-277">Scegliere **Topologia** dal menu Azione **e** quindi **Pubblica.**</span><span class="sxs-lookup"><span data-stu-id="82f81-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="82f81-278">Nella pagina di conferma fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="82f81-279">Eseguire alcuni passaggi finali per verificare che gli account SQL account di accesso siano presenti in ognuna delle repliche nel gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="82f81-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="82f81-280">Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente** e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="82f81-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="82f81-281">Espandere Skype for Business Server, espandere la topologia ed espandere SQL Server **store.**</span><span class="sxs-lookup"><span data-stu-id="82f81-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="82f81-282">Fare clic con il pulsante SQL'archivio del nuovo gruppo di disponibilità e scegliere **Modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="82f81-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="82f81-283">Nella parte inferiore della pagina, nella casella **SQL Server FQDN,** modificare il valore in FQDN del listener del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="82f81-284">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="82f81-284">Publish the topology.</span></span> <span data-ttu-id="82f81-285">Scegliere **Topologia** dal menu Azione **e** quindi **Pubblica.**</span><span class="sxs-lookup"><span data-stu-id="82f81-285">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="82f81-286">Nella pagina di conferma fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-286">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="82f81-287">Attendere quindi alcuni minuti per la replica della nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="82f81-287">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="82f81-288">Apri SQL Server Management Studio e passa al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="82f81-289">Eseguire il failover su una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="82f81-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="82f81-290">Aprire Skype for Business Server Management Shell e digitare il cmdlet seguente per creare SQL account di accesso in questa replica:</span><span class="sxs-lookup"><span data-stu-id="82f81-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="82f81-291">Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria, quindi utilizzare ) per  `Install-CsDatabase -Update` ogni replica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="82f81-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="82f81-292">Distribuire un gruppo di disponibilità Always On in un pool esistente che non utilizza il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="82f81-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="82f81-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="82f81-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="82f81-294">Se il pool che si sta aggiornando a un gruppo di disponibilità ospita l'archivio di gestione centrale per l'organizzazione, è necessario spostare il Servizio di gestione catalogo in un altro pool prima di aggiornare il pool.</span><span class="sxs-lookup"><span data-stu-id="82f81-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="82f81-295">Utilizzare il cmdlet Move-CsManagementServer per spostare il pool.</span><span class="sxs-lookup"><span data-stu-id="82f81-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="82f81-296">Se nell'organizzazione non è presente un altro pool, è possibile distribuire temporaneamente un server Standard Edition e spostare il server CMS in questo server prima di aggiornare il pool al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="82f81-297">Configurare la funzionalità Clustering di failover in tutti i server di database che fanno parte del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="82f81-298">In ogni server eseguire le operazioni seguenti</span><span class="sxs-lookup"><span data-stu-id="82f81-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="82f81-299">Aprire Server Manager e fare clic **su Aggiungi ruoli e funzionalità.**</span><span class="sxs-lookup"><span data-stu-id="82f81-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="82f81-300">Fare **clic su** Avanti fino a raggiungere la casella **Seleziona** funzionalità.</span><span class="sxs-lookup"><span data-stu-id="82f81-300">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="82f81-301">In questo caso, selezionare la **casella di controllo Clustering** di failover.</span><span class="sxs-lookup"><span data-stu-id="82f81-301">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="82f81-302">Nella casella **Add features that are required for Failover Clustering?** fare clic su Add **Features.**</span><span class="sxs-lookup"><span data-stu-id="82f81-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="82f81-303">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="82f81-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="82f81-304">Convalidare la configurazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="82f81-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="82f81-305">In Server Manager scegliere Gestione **cluster** di failover dal menu **Strumenti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="82f81-306">In **Azioni sul** lato destro dello schermo fare clic su Convalida **configurazione.**</span><span class="sxs-lookup"><span data-stu-id="82f81-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="82f81-307">Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-308">Selezionare i server da aggiungere al cluster e quindi fare clic **su Esegui tutti i test.**</span><span class="sxs-lookup"><span data-stu-id="82f81-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="82f81-309">Nella casella **Riepilogo** controllare gli eventuali errori rilevati dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="82f81-309">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="82f81-310">Fare quindi **clic su Fine** per completare la convalida.</span><span class="sxs-lookup"><span data-stu-id="82f81-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="82f81-311">La procedura guidata probabilmente segnala diversi avvisi, soprattutto se non si utilizza l'archiviazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="82f81-311">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="82f81-312">Non è necessario utilizzare l'archiviazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="82f81-312">You are not required to use shared storage.</span></span> <span data-ttu-id="82f81-313">Tuttavia, se vengono visualizzati messaggi **di** errore, è necessario risolvere tali problemi prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="82f81-313">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="82f81-314">Creare il cluster di failover di Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="82f81-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="82f81-315">Nella procedura **guidata Gestione cluster di failover** fare clic con il pulsante destro del mouse su Gestione cluster di **failover** e quindi scegliere **Crea cluster.**</span><span class="sxs-lookup"><span data-stu-id="82f81-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="82f81-316">Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-317">Aggiungere il nome del cluster e l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="82f81-317">Add the cluster name and IP address.</span></span> <span data-ttu-id="82f81-318">Dopo la convalida delle impostazioni, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-318">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-319">Nella pagina Conferma, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-320">Dopo aver creato il cluster, fare clic su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="82f81-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="82f81-321">È consigliabile configurare le impostazioni del quorum del cluster per l'utilizzo di un controllo della condivisione file.</span><span class="sxs-lookup"><span data-stu-id="82f81-321">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="82f81-322">A tale scopo, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="82f81-322">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="82f81-323">Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **Altre azioni** e fare clic su Configura impostazioni **quorum cluster.**</span><span class="sxs-lookup"><span data-stu-id="82f81-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="82f81-324">Nella pagina **Selezione opzione di configurazione quorum** fare clic su Seleziona il controllo del **quorum.**</span><span class="sxs-lookup"><span data-stu-id="82f81-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="82f81-325">Nella pagina **Selezione quorum di controllo** fare clic su Configura un controllo della condivisione **file.**</span><span class="sxs-lookup"><span data-stu-id="82f81-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="82f81-326">Nella pagina **Configura condivisione file di controllo** digitare il percorso della condivisione file che si desidera utilizzare e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-327">Nella pagina **Conferma**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="82f81-328">In ogni server del cluster, abilitare Il gruppo di disponibilità in SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="82f81-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="82f81-329">Aprire Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="82f81-329">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="82f81-330">Nell'albero sul lato sinistro dello schermo fare clic su **SQL Server Servizi** e quindi fare doppio clic sul SQL Server servizio.</span><span class="sxs-lookup"><span data-stu-id="82f81-330">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="82f81-331">Nella casella **Proprietà** selezionare la **scheda Disponibilità elevata AlwaysOn.** Selezionare la **casella di controllo Abilita gruppi di disponibilità AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="82f81-331">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="82f81-332">Riavviare SQL Server servizio quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="82f81-332">Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="82f81-333">Creare il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="82f81-334">Apri SQL Server Management Studio e connettiti all'SQL Server istanza.</span><span class="sxs-lookup"><span data-stu-id="82f81-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="82f81-335">In Esplora oggetti espandere la **cartella Disponibilità elevata Always On.**</span><span class="sxs-lookup"><span data-stu-id="82f81-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="82f81-336">Fare clic con il pulsante destro **del** mouse sulla cartella Gruppi di disponibilità e scegliere **Creazione guidata nuovo gruppo di disponibilità.**</span><span class="sxs-lookup"><span data-stu-id="82f81-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="82f81-337">Se viene **visualizzata la** pagina Introduzione, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-338">Nella pagina **Specifica nome gruppo di** disponibilità digitare il nome del gruppo di disponibilità e fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-339">Nella pagina Selezione database selezionare i database che si desidera includere nel gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="82f81-340">Scegliere il pulsante **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="82f81-341">Non includere i **database ReportServer,** **ReportServerTempDB** o Persistent Chat nel gruppo di disponibilità, in quanto non sono supportati in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="82f81-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="82f81-342">È possibile includere tutti gli altri database di Skype for Business Server nel gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="82f81-343">Nella pagina **Specifica repliche** fare clic sulla **scheda** Repliche. Fare quindi clic **sul pulsante Aggiungi** repliche e connettersi alle altre istanze SQL unite come nodi di WSFC.</span><span class="sxs-lookup"><span data-stu-id="82f81-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="82f81-344">Per ogni istanza, selezionare le **opzioni Failover automatico** e **Commit** sincrono.</span><span class="sxs-lookup"><span data-stu-id="82f81-344">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="82f81-345">Non selezionare **l'opzione Secondaria leggibile.**</span><span class="sxs-lookup"><span data-stu-id="82f81-345">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="82f81-346">Fare clic **sulla scheda Endpoint** e verificare che il numero di **porta** sia impostato su 5022.</span><span class="sxs-lookup"><span data-stu-id="82f81-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="82f81-347">Fare clic **sulla scheda Listener** e selezionare l'opzione Crea listener del gruppo **di** disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-347">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="82f81-348">In tale opzione digitare un nome per il listener e impostare **la** porta su 1433 (altre porte non sono supportate per questa opzione).</span><span class="sxs-lookup"><span data-stu-id="82f81-348">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="82f81-349">Fare **clic su** Aggiungi e quindi nella casella Indirizzo **IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="82f81-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="82f81-350">Nella **pagina** Selezione sincronizzazione dati iniziale selezionare Completo e specificare una cartella accessibile alle repliche e per cui l'account di servizio SQL Server utilizzato da entrambe le repliche dispone delle autorizzazioni di scrittura.</span><span class="sxs-lookup"><span data-stu-id="82f81-350">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="82f81-351">Scegliere il pulsante **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82f81-351">Then click **Next**.</span></span>
    
     <span data-ttu-id="82f81-352">Questa condivisione file verrà utilizzata temporaneamente quando si inizializzano i database.</span><span class="sxs-lookup"><span data-stu-id="82f81-352">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="82f81-353">Se si gestiscono database di grandi dimensioni, è consigliabile inizializzarli manualmente nel caso in cui la larghezza di banda di rete non possa contenere le dimensioni dei backup dei database.</span><span class="sxs-lookup"><span data-stu-id="82f81-353">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="82f81-354">Nella pagina Convalida verificare che tutti i controlli di convalida siano stati eseguiti correttamente e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="82f81-355">Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su Fine.</span><span class="sxs-lookup"><span data-stu-id="82f81-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="82f81-356">Creare un nuovo archivio specificando il listener di criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="82f81-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="82f81-357">Apre lo strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="82f81-357">Open Topology Builder.</span></span> <span data-ttu-id="82f81-358">Nella topologia espandere Componenti **condivisi,** fare clic con il pulsante destro **del mouse** su SQL Server archivi e scegliere Nuovo **SQL Server Store.**</span><span class="sxs-lookup"><span data-stu-id="82f81-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="82f81-359">Nella pagina Definisci nuovo **SQL Store** selezionare  innanzitutto la casella di controllo Impostazioni disponibilità elevata e quindi verificare che i gruppi di disponibilità AlwaysOn SQL siano visualizzati nella casella di riepilogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="82f81-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="82f81-360">Nella casella **SQL Server FQDN listener** disponibilità digitare il nome di dominio completo del listener creato al momento della creazione del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="82f81-361">Nella casella **SQL Server FQDN** digitare l'FQDN del nodo primario del gruppo di disponibilità e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="82f81-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="82f81-362">Associare il nuovo gruppo di disponibilità Always On al pool Front End.</span><span class="sxs-lookup"><span data-stu-id="82f81-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="82f81-363">In Generatore di topologie fare clic con il pulsante destro del mouse sul pool da associare al gruppo di disponibilità e scegliere **Modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="82f81-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="82f81-364">In **Associazioni,** nella casella SQL Server **Store,** selezionare il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="82f81-365">Selezionare lo stesso gruppo per tutti gli altri database del pool che si desidera spostare nel gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="82f81-366">Quando si è certi che tutti i database necessari siano impostati sul gruppo di disponibilità, fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="82f81-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="82f81-367">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="82f81-367">Publish the topology.</span></span> <span data-ttu-id="82f81-368">Scegliere **Topologia** dal menu Azione **e** quindi **Pubblica.**</span><span class="sxs-lookup"><span data-stu-id="82f81-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="82f81-369">Nella pagina di conferma fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="82f81-370">Eseguire alcuni passaggi finali per verificare che gli account SQL account di accesso siano presenti in ognuna delle repliche nel gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="82f81-371">Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente** e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="82f81-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="82f81-372">Espandere Skype for Business Server, espandere la topologia ed espandere SQL Server **store.**</span><span class="sxs-lookup"><span data-stu-id="82f81-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="82f81-373">Fare clic con il pulsante SQL'archivio del nuovo gruppo di disponibilità e scegliere **Modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="82f81-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="82f81-374">Nella parte inferiore della pagina, nella casella **SQL Server FQDN,** modificare il valore in FQDN del listener del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="82f81-375">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="82f81-375">Publish the topology.</span></span> <span data-ttu-id="82f81-376">Scegliere **Topologia** dal menu Azione **e** quindi **Pubblica.**</span><span class="sxs-lookup"><span data-stu-id="82f81-376">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="82f81-377">Nella pagina di conferma fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="82f81-377">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="82f81-378">Attendere quindi alcuni minuti per la replica della nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="82f81-378">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="82f81-379">Apri SQL Server Management Studio e passa al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="82f81-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="82f81-380">Eseguire il failover su una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="82f81-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="82f81-381">Aprire Skype for Business Server Management Shell e digitare il cmdlet seguente per creare SQL account di accesso in questa replica:</span><span class="sxs-lookup"><span data-stu-id="82f81-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="82f81-382">Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria, quindi utilizzare ) per  `Install-CsDatabase -Update` ogni replica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="82f81-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
