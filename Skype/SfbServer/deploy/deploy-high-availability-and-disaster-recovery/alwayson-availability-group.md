---
title: Distribuire un gruppo di disponibilità sempre su un server back-end in Skype for Business Server
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
description: Distribuire (installare) un gruppo di disponibilità sempre presente nella distribuzione di Skype for Business Server.
ms.openlocfilehash: 83565efe850570ac5ab9a0695757e708f3eae566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830656"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="20d5a-103">Distribuire un gruppo di disponibilità sempre su un server back-end in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="20d5a-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="20d5a-104">Distribuire (installare) un gruppo di disponibilità sempre disponibile (AG) nella distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="20d5a-105">La modalità di distribuzione di un AG varia a seconda che la distribuzione venga distribuita in un nuovo pool, in un pool esistente che utilizza il mirroring o in un pool esistente che attualmente non dispone di disponibilità elevata per il database back-end.</span><span class="sxs-lookup"><span data-stu-id="20d5a-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="20d5a-106">L'utilizzo di un componente AG con un ruolo del server Chat persistente non è supportato.</span><span class="sxs-lookup"><span data-stu-id="20d5a-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="20d5a-107">Distribuire un gruppo di disponibilità sempre su un nuovo pool Front End</span><span class="sxs-lookup"><span data-stu-id="20d5a-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="20d5a-108">Distribuire un gruppo di disponibilità sempre su un pool esistente che utilizza il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="20d5a-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="20d5a-109">Distribuire un gruppo di disponibilità sempre su un pool esistente che non utilizza il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="20d5a-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="20d5a-110">Distribuire un gruppo di disponibilità sempre su un nuovo pool Front End</span><span class="sxs-lookup"><span data-stu-id="20d5a-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="20d5a-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="20d5a-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span></span>

1. <span data-ttu-id="20d5a-112">Abilitare la funzionalità di clustering di failover in tutti i server di database che faranno parte dell'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="20d5a-113">In ogni server, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20d5a-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="20d5a-114">Aprire Server Manager e fare clic su **Aggiungi ruoli e funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="20d5a-115">Fare clic su **Avanti** fino a raggiungere la casella **Seleziona funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-115">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="20d5a-116">Selezionare la casella di controllo **clustering di failover** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-116">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="20d5a-117">Nella casella **Aggiungi funzionalità necessarie per il clustering di failover** fare clic su **Aggiungi funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="20d5a-118">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="20d5a-119">Convalidare la configurazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="20d5a-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="20d5a-120">In Server Manager, fare clic sul menu **strumenti** , quindi fare clic su **Gestione cluster di failover**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="20d5a-121">In **azioni** nella parte destra dello schermo fare clic su **Convalida configurazione**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="20d5a-122">Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-123">Selezionare i server da aggiungere al cluster e quindi fare clic su **Esegui tutti i test**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="20d5a-124">Nella casella **Riepilogo** controllare gli eventuali errori segnalati dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="20d5a-124">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="20d5a-125">Quindi fare clic su **fine** per completare la convalida.</span><span class="sxs-lookup"><span data-stu-id="20d5a-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="20d5a-126">La procedura guidata riporterà probabilmente diversi avvisi, soprattutto se non si utilizza l'archiviazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="20d5a-126">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="20d5a-127">Non è necessario utilizzare l'archiviazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="20d5a-127">You are not required to use shared storage.</span></span> <span data-ttu-id="20d5a-128">Tuttavia, se vengono visualizzati messaggi di **errore** , è necessario correggere tali problemi prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="20d5a-128">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="20d5a-129">Creare il cluster di failover di Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="20d5a-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="20d5a-130">Nella procedura guidata **Gestione cluster di failover** fare clic con il pulsante destro del mouse su **Gestione cluster di failover** e quindi scegliere **Crea cluster**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="20d5a-131">Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-132">Aggiungere il nome del cluster e l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="20d5a-132">Add the cluster name and IP address.</span></span> <span data-ttu-id="20d5a-133">Quando le impostazioni vengono convalidate, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-133">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-134">Nella pagina Conferma, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-135">Dopo aver creato il cluster, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="20d5a-136">Si consiglia di configurare le impostazioni di quorum del cluster per l'utilizzo di un witness di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="20d5a-136">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="20d5a-137">A tale scopo, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="20d5a-137">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="20d5a-138">Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **altre azioni** e quindi **configurare le impostazioni di quorum del cluster**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="20d5a-139">Nella pagina **Seleziona opzione di configurazione quorum** fare clic su **Seleziona il controllo quorum**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="20d5a-140">Nella pagina **Seleziona controllo quorum** fare clic su **configura un witness di condivisione file**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="20d5a-141">Nella pagina **Configura testimone condivisione file** Digitare il percorso della condivisione di file che si desidera utilizzare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-142">Nella pagina **Conferma**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="20d5a-143">In ogni server del cluster abilitare la funzionalità AG in Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="20d5a-144">Aprire Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-144">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="20d5a-145">Nell'albero a sinistra dello schermo fare clic su **servizi SQL Server** e quindi fare doppio clic sul servizio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-145">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="20d5a-146">Nella casella **Proprietà** selezionare la scheda **disponibilità elevata AlwaysOn** . Selezionare la casella di controllo **Abilita gruppi di disponibilità AlwaysOn** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-146">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="20d5a-147">Quando richiesto, riavviare il servizio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-147">Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="20d5a-148">Utilizzare Generatore di topologie per creare il pool Front End, come spiegato in [creare e pubblicare una nuova topologia in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="20d5a-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="20d5a-149">Quando si esegue questa operazione, specificare l'AG come archivio SQL per il pool.</span><span class="sxs-lookup"><span data-stu-id="20d5a-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="20d5a-150">Creare il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="20d5a-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="20d5a-151">Aprire SQL Server Management Studio e connettersi all'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="20d5a-152">In Esplora oggetti espandere la cartella **Always on High Availability** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="20d5a-153">Fare clic con il pulsante destro del mouse sulla cartella **gruppi di disponibilità** e scegliere **nuova procedura guidata gruppo di disponibilità**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="20d5a-154">Se viene visualizzata la pagina **Introduzione** , fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-155">Nella pagina **specificare il nome del gruppo di disponibilità** , digitare il nome del gruppo di disponibilità e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-156">Nella pagina Seleziona database selezionare i database che si desidera includere nel gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="20d5a-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="20d5a-157">Scegliere il pulsante **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="20d5a-158">Non includere i database **ReportServer**, **ReportServerTempDB** o Persistent Chat nel gruppo di disponibilità AlwaysOn, in quanto questi non sono supportati in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="20d5a-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="20d5a-159">È possibile includere tutti gli altri database di Skype for Business Server nel gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="20d5a-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="20d5a-160">Nella pagina **Specifica repliche** fare clic sulla scheda **repliche** . Fare quindi clic sul pulsante **Aggiungi repliche** e connettersi alle altre istanze di SQL aggiunte come nodi del cluster di failover di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="20d5a-161">Per ogni istanza, selezionare il **failover automatico** e le opzioni di **commit sincrono** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-161">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="20d5a-162">Non selezionare l'opzione **secondaria leggibile** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-162">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="20d5a-163">Fare clic sulla scheda **endpoint** e verificare che il **numero di porta** sia impostato su 5022.</span><span class="sxs-lookup"><span data-stu-id="20d5a-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="20d5a-164">Fare clic sulla scheda **listener** e selezionare l'opzione **Crea un listener del gruppo di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-164">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="20d5a-165">In tale opzione digitare un nome per il listener e impostare la **porta** su 1433 (altre porte non sono supportate per questa opzione).</span><span class="sxs-lookup"><span data-stu-id="20d5a-165">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="20d5a-166">Fare clic su **Aggiungi**, quindi nella casella **indirizzo IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="20d5a-167">Nella pagina **Seleziona sincronizzazione dati iniziale** selezionare completo e specificare una cartella accessibile alle repliche e che l'account di servizio di SQL Server utilizzato da entrambe le repliche disponga delle autorizzazioni di scrittura per.</span><span class="sxs-lookup"><span data-stu-id="20d5a-167">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="20d5a-168">Scegliere il pulsante **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-168">Then click **Next**.</span></span>
    
     <span data-ttu-id="20d5a-169">Questa condivisione file verrà utilizzata temporaneamente quando si inizializzano i database.</span><span class="sxs-lookup"><span data-stu-id="20d5a-169">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="20d5a-170">Se si ha a che fare con database di grandi dimensioni, è consigliabile inizializzarli manualmente se la larghezza di banda di rete non è in grado di soddisfare le dimensioni dei backup del database.</span><span class="sxs-lookup"><span data-stu-id="20d5a-170">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="20d5a-171">Nella pagina Convalida verificare che tutti i controlli di convalida siano stati eseguiti correttamente e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-172">Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su fine.</span><span class="sxs-lookup"><span data-stu-id="20d5a-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="20d5a-173">Dopo che il pool e l'AG sono stati distribuiti, eseguire alcuni passaggi finali per assicurarsi che gli account di accesso di SQL siano su ognuna delle repliche del gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="20d5a-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="20d5a-174">Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="20d5a-175">Espandi Skype for Business Server, Espandi la topologia ed Espandi gli **archivi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="20d5a-176">Fare clic con il pulsante destro del mouse sull'archivio SQL del nuovo gruppo di disponibilità AlwaysOn e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="20d5a-177">Nella parte inferiore della pagina, nella casella **FQDN di SQL Server** , impostare il valore sul nome di dominio completo del listener dell'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="20d5a-178">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="20d5a-178">Publish the topology.</span></span> <span data-ttu-id="20d5a-179">Dal menu **azione** fare clic su **topologia** e quindi su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-179">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="20d5a-180">Nella pagina di conferma fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-180">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="20d5a-181">Attendere quindi alcuni minuti per la replica della nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="20d5a-181">Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="20d5a-182">Aprire SQL Server Management Studio e passare all'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="20d5a-183">Eseguire il failover su una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="20d5a-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="20d5a-184">Aprire Skype for Business Server Management Shell e digitare il seguente cmdlet per creare gli account di accesso di SQL in questa replica:</span><span class="sxs-lookup"><span data-stu-id="20d5a-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="20d5a-185">Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria e quindi utilizzare  `Install-CsDatabase -Update` ) per ogni replica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="20d5a-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="20d5a-186">Distribuire un gruppo di disponibilità sempre su un pool esistente che utilizza il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="20d5a-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="20d5a-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="20d5a-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="20d5a-188">Se il pool in cui si esegue l'aggiornamento a un AG ospita l'archivio di gestione centrale per l'organizzazione, è necessario prima di tutto spostare il CMS in un altro pool prima di aggiornare questo pool.</span><span class="sxs-lookup"><span data-stu-id="20d5a-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="20d5a-189">Utilizzare il cmdlet Move-CsManagementServer per spostare il pool.</span><span class="sxs-lookup"><span data-stu-id="20d5a-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="20d5a-190">Se non si dispone di un altro pool nell'organizzazione, è possibile distribuire temporaneamente un server Standard Edition e spostare il CMS in questo server prima di eseguire l'aggiornamento del pool all'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="20d5a-191">Eseguire il failover di tutti i dati dal mirror al nodo principale aprendo Skype for Business Server Management Shell e digitando il cmdlet seguente.</span><span class="sxs-lookup"><span data-stu-id="20d5a-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="20d5a-192">Ripetere questo cmdlet per ogni tipo di database del pool.</span><span class="sxs-lookup"><span data-stu-id="20d5a-192">Repeat this cmdlet for each database type in the pool.</span></span> <span data-ttu-id="20d5a-193">È possibile utilizzare il cmdlet seguente per individuare tutti i tipi di database archiviati in questo pool.</span><span class="sxs-lookup"><span data-stu-id="20d5a-193">You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="20d5a-194">Utilizzare Generatore di topologie per rimuovere il mirroring del database dal pool.</span><span class="sxs-lookup"><span data-stu-id="20d5a-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="20d5a-195">Apre lo strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="20d5a-195">Open Topology Builder.</span></span> <span data-ttu-id="20d5a-196">Nella topologia espandere **pool Enterprise Edition front end**, fare clic con il pulsante destro del mouse sul nome del pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="20d5a-197">Per ogni tipo di archivio SQL nel pool, deselezionare la casella di controllo **Abilita mirroring dell'archivio SQL** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="20d5a-198">Pubblicare la topologia modificata.</span><span class="sxs-lookup"><span data-stu-id="20d5a-198">Publish the changed topology.</span></span> <span data-ttu-id="20d5a-199">Dal menu **azione** fare clic su **topologia** e quindi su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-199">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="20d5a-200">Quindi nella pagina di conferma fare clic su **Avanti**</span><span class="sxs-lookup"><span data-stu-id="20d5a-200">Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="20d5a-201">Utilizzare SQL Server Management Studio per interrompere il mirroring.</span><span class="sxs-lookup"><span data-stu-id="20d5a-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="20d5a-202">Aprire SQL Server Management Studio, accedere ai database, fare clic con il pulsante destro del mouse su **attività** e scegliere **mirror**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-202">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**.</span></span> <span data-ttu-id="20d5a-203">Quindi fare clic su **Rimuovi mirroring** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-203">Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="20d5a-204">Ripetere questa operazione per tutti i database del pool che verranno convertiti in un AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="20d5a-205">Configurare la funzionalità di clustering di failover in tutti i server di database che faranno parte dell'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="20d5a-206">In ogni server, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20d5a-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="20d5a-207">Aprire Server Manager e fare clic su **Aggiungi ruoli e funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="20d5a-208">Fare clic su **Avanti** fino a raggiungere la casella **Seleziona funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-208">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="20d5a-209">Selezionare la casella di controllo **clustering di failover** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-209">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="20d5a-210">Nella casella **Aggiungi funzionalità necessarie per il clustering di failover** fare clic su **Aggiungi funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="20d5a-211">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="20d5a-212">Convalidare la configurazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="20d5a-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="20d5a-213">In Server Manager, fare clic sul menu **strumenti** , quindi fare clic su **Gestione cluster di failover**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="20d5a-214">In **azioni** nella parte destra dello schermo fare clic su **Convalida configurazione**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="20d5a-215">Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-216">Selezionare i server da aggiungere al cluster e quindi fare clic su **Esegui tutti i test**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="20d5a-217">Nella casella **Riepilogo** controllare gli eventuali errori segnalati dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="20d5a-217">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="20d5a-218">Quindi fare clic su **fine** per completare la convalida.</span><span class="sxs-lookup"><span data-stu-id="20d5a-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="20d5a-219">La procedura guidata riporterà probabilmente diversi avvisi, soprattutto se non si utilizza l'archiviazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="20d5a-219">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="20d5a-220">Non è necessario utilizzare l'archiviazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="20d5a-220">You are not required to use shared storage.</span></span> <span data-ttu-id="20d5a-221">Tuttavia, se vengono visualizzati messaggi di **errore** , è necessario correggere tali problemi prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="20d5a-221">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="20d5a-222">Creare il cluster di failover di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="20d5a-223">Nella procedura guidata **Gestione cluster di failover** fare clic con il pulsante destro del mouse su **Gestione cluster di failover** e quindi scegliere **Crea cluster**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="20d5a-224">Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-225">Aggiungere il nome del cluster e l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="20d5a-225">Add the cluster name and IP address.</span></span> <span data-ttu-id="20d5a-226">Quando le impostazioni vengono convalidate, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-226">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-227">Nella pagina Conferma, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-228">Dopo aver creato il cluster, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="20d5a-229">Si consiglia di configurare le impostazioni di quorum del cluster per l'utilizzo di un witness di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="20d5a-229">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="20d5a-230">A tale scopo, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="20d5a-230">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="20d5a-231">Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **altre azioni** e quindi **configurare le impostazioni di quorum del cluster**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="20d5a-232">Nella pagina **Seleziona opzione di configurazione quorum** fare clic su **Seleziona il controllo quorum**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="20d5a-233">Nella pagina **Seleziona controllo quorum** fare clic su **configura un witness di condivisione file**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="20d5a-234">Nella pagina **Configura testimone condivisione file** Digitare il percorso della condivisione di file che si desidera utilizzare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-235">Nella pagina **Conferma**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="20d5a-236">In ogni server del cluster abilitare la funzionalità AG in Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="20d5a-237">Aprire Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-237">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="20d5a-238">Nell'albero a sinistra dello schermo fare clic su **servizi SQL Server** e quindi fare doppio clic sul servizio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-238">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="20d5a-239">Nella casella **Proprietà** selezionare la scheda **disponibilità elevata AlwaysOn** . Selezionare la casella di controllo **Abilita gruppi di disponibilità AlwaysOn** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-239">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="20d5a-240">Quando richiesto, riavviare il servizio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-240">Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="20d5a-241">Creare il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="20d5a-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="20d5a-242">Aprire SQL Server Management Studio e connettersi all'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="20d5a-243">In Esplora oggetti espandere la cartella **Always on High Availability** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="20d5a-244">Fare clic con il pulsante destro del mouse sulla cartella **gruppi di disponibilità** e scegliere **nuova procedura guidata gruppo di disponibilità**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="20d5a-245">Se viene visualizzata la pagina **Introduzione** , fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="20d5a-246">Nella pagina **specificare il nome del gruppo di disponibilità** , digitare il nome del gruppo di disponibilità e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="20d5a-247">Nella pagina Seleziona database selezionare i database che si desidera includere nel gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="20d5a-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="20d5a-248">Scegliere il pulsante **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="20d5a-249">Non includere i database **ReportServer**, **ReportServerTempDB** o Persistent Chat nel gruppo di disponibilità AlwaysOn, in quanto questi non sono supportati in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="20d5a-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="20d5a-250">È possibile includere tutti gli altri database di Skype for Business Server nel gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="20d5a-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="20d5a-251">Nella pagina **Specifica repliche** fare clic sulla scheda **repliche** . Fare quindi clic sul pulsante **Aggiungi repliche** e connettersi alle altre istanze di SQL aggiunte come nodi del cluster di failover di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="20d5a-252">Per ogni istanza, selezionare il **failover automatico** e le opzioni di **commit sincrono** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-252">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="20d5a-253">Non selezionare l'opzione **secondaria leggibile** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-253">Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="20d5a-254">Fare clic sulla scheda **endpoint** e verificare che il **numero di porta** sia impostato su 5022.</span><span class="sxs-lookup"><span data-stu-id="20d5a-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="20d5a-255">Fare clic sulla scheda **listener** e selezionare l'opzione **Crea un listener del gruppo di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-255">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="20d5a-256">In tale opzione digitare un nome per il listener e impostare la **porta** su 1433 (altre porte non sono supportate per questa opzione).</span><span class="sxs-lookup"><span data-stu-id="20d5a-256">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="20d5a-257">Fare clic su **Aggiungi**, quindi nella casella **indirizzo IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="20d5a-258">Nella pagina **Seleziona sincronizzazione dati iniziale** selezionare completo e specificare una cartella accessibile alle repliche e che l'account di servizio di SQL Server utilizzato da entrambe le repliche disponga delle autorizzazioni di scrittura per.</span><span class="sxs-lookup"><span data-stu-id="20d5a-258">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="20d5a-259">Scegliere il pulsante **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-259">Then click **Next**.</span></span>
    
    <span data-ttu-id="20d5a-260">Questa condivisione file verrà utilizzata temporaneamente quando si inizializzano i database.</span><span class="sxs-lookup"><span data-stu-id="20d5a-260">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="20d5a-261">Se si ha a che fare con database di grandi dimensioni, è consigliabile inizializzarli manualmente se la larghezza di banda di rete non è in grado di soddisfare le dimensioni dei backup del database.</span><span class="sxs-lookup"><span data-stu-id="20d5a-261">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="20d5a-262">Nella pagina Convalida verificare che tutti i controlli di convalida siano stati eseguiti correttamente e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="20d5a-263">Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su fine.</span><span class="sxs-lookup"><span data-stu-id="20d5a-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="20d5a-264">Creare un nuovo archivio specificando il listener AG e specificando il principale del mirror precedente come nodo primario dell'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="20d5a-265">Apre lo strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="20d5a-265">Open Topology Builder.</span></span> <span data-ttu-id="20d5a-266">Nella topologia espandere **componenti condivisi**, fare clic con il pulsante destro del mouse su **Archivi SQL Server** e scegliere **nuovo archivio SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="20d5a-267">Nella pagina **Definisci nuovo archivio SQL** selezionare la casella di controllo **Impostazioni disponibilità elevata** e quindi verificare che nella casella a discesa vengano visualizzati i gruppi di disponibilità di SQL AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="20d5a-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="20d5a-268">Nella casella **nome di dominio completo listener di disponibilità di SQL Server** Digitare il nome di dominio completo del listener creato durante la creazione del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="20d5a-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="20d5a-269">Nella casella **FQDN di SQL Server** , digitare il nome di dominio completo del nodo primario dell'AG, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="20d5a-270">Questo dovrebbe essere l'entità del mirror precedente per questo archivio.</span><span class="sxs-lookup"><span data-stu-id="20d5a-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="20d5a-271">Associare la nuova AG al pool Front end.</span><span class="sxs-lookup"><span data-stu-id="20d5a-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="20d5a-272">In Generatore di topologie fare clic con il pulsante destro del mouse sul pool da associare all'AG e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="20d5a-273">In **associazioni**, nella casella **Archivio SQL Server** Selezionare l'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="20d5a-274">Selezionare lo stesso gruppo per qualsiasi altro database del pool che si desidera spostare nell'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="20d5a-275">Quando si è certi che tutti i database necessari sono impostati sull'AG, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="20d5a-276">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="20d5a-276">Publish the topology.</span></span> <span data-ttu-id="20d5a-277">Dal menu **azione** fare clic su **topologia** e quindi su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="20d5a-278">Nella pagina di conferma fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="20d5a-279">Eseguire alcuni passaggi finali per assicurarsi che gli account di accesso di SQL siano su ognuna delle repliche del gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="20d5a-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="20d5a-280">Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="20d5a-281">Espandi Skype for Business Server, Espandi la topologia ed Espandi gli **archivi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="20d5a-282">Fare clic con il pulsante destro del mouse sull'archivio SQL della nuova AG e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="20d5a-283">Nella parte inferiore della pagina, nella casella **FQDN di SQL Server** , impostare il valore sul nome di dominio completo del listener dell'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="20d5a-284">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="20d5a-284">Publish the topology.</span></span> <span data-ttu-id="20d5a-285">Dal menu **azione** fare clic su **topologia** e quindi su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-285">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="20d5a-286">Nella pagina di conferma fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-286">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="20d5a-287">Attendere quindi alcuni minuti per la replica della nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="20d5a-287">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="20d5a-288">Aprire SQL Server Management Studio e passare all'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="20d5a-289">Eseguire il failover su una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="20d5a-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="20d5a-290">Aprire Skype for Business Server Management Shell e digitare il seguente cmdlet per creare gli account di accesso di SQL in questa replica:</span><span class="sxs-lookup"><span data-stu-id="20d5a-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="20d5a-291">Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria e quindi utilizzare  `Install-CsDatabase -Update` ) per ogni replica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="20d5a-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="20d5a-292">Distribuire un gruppo di disponibilità sempre su un pool esistente che non utilizza il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="20d5a-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="20d5a-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="20d5a-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="20d5a-294">Se il pool in cui si esegue l'aggiornamento a un AG ospita l'archivio di gestione centrale per l'organizzazione, è necessario prima di tutto spostare il CMS in un altro pool prima di aggiornare questo pool.</span><span class="sxs-lookup"><span data-stu-id="20d5a-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="20d5a-295">Utilizzare il cmdlet Move-CsManagementServer per spostare il pool.</span><span class="sxs-lookup"><span data-stu-id="20d5a-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="20d5a-296">Se non si dispone di un altro pool nell'organizzazione, è possibile distribuire temporaneamente un server Standard Edition e spostare il CMS in questo server prima di eseguire l'aggiornamento del pool all'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="20d5a-297">Configurare la funzionalità di clustering di failover in tutti i server di database che faranno parte dell'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="20d5a-298">In ogni server, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20d5a-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="20d5a-299">Aprire Server Manager e fare clic su **Aggiungi ruoli e funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="20d5a-300">Fare clic su **Avanti** fino a raggiungere la casella **Seleziona funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-300">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="20d5a-301">Selezionare la casella di controllo **clustering di failover** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-301">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="20d5a-302">Nella casella **Aggiungi funzionalità necessarie per il clustering di failover** fare clic su **Aggiungi funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="20d5a-303">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="20d5a-304">Convalidare la configurazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="20d5a-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="20d5a-305">In Server Manager, fare clic sul menu **strumenti** , quindi fare clic su **Gestione cluster di failover**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="20d5a-306">In **azioni** nella parte destra dello schermo fare clic su **Convalida configurazione**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="20d5a-307">Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-308">Selezionare i server da aggiungere al cluster e quindi fare clic su **Esegui tutti i test**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="20d5a-309">Nella casella **Riepilogo** controllare gli eventuali errori segnalati dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="20d5a-309">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="20d5a-310">Quindi fare clic su **fine** per completare la convalida.</span><span class="sxs-lookup"><span data-stu-id="20d5a-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="20d5a-311">La procedura guidata riporterà probabilmente diversi avvisi, soprattutto se non si utilizza l'archiviazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="20d5a-311">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="20d5a-312">Non è necessario utilizzare l'archiviazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="20d5a-312">You are not required to use shared storage.</span></span> <span data-ttu-id="20d5a-313">Tuttavia, se vengono visualizzati messaggi di **errore** , è necessario correggere tali problemi prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="20d5a-313">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="20d5a-314">Creare il cluster di failover di Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="20d5a-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="20d5a-315">Nella procedura guidata **Gestione cluster di failover** fare clic con il pulsante destro del mouse su **Gestione cluster di failover** e quindi scegliere **Crea cluster**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="20d5a-316">Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-317">Aggiungere il nome del cluster e l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="20d5a-317">Add the cluster name and IP address.</span></span> <span data-ttu-id="20d5a-318">Quando le impostazioni vengono convalidate, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-318">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-319">Nella pagina Conferma, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-320">Dopo aver creato il cluster, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="20d5a-321">Si consiglia di configurare le impostazioni di quorum del cluster per l'utilizzo di un witness di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="20d5a-321">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="20d5a-322">A tale scopo, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="20d5a-322">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="20d5a-323">Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **altre azioni** e quindi **configurare le impostazioni di quorum del cluster**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="20d5a-324">Nella pagina **Seleziona opzione di configurazione quorum** fare clic su **Seleziona il controllo quorum**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="20d5a-325">Nella pagina **Seleziona controllo quorum** fare clic su **configura un witness di condivisione file**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="20d5a-326">Nella pagina **Configura testimone condivisione file** Digitare il percorso della condivisione di file che si desidera utilizzare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-327">Nella pagina **Conferma**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="20d5a-328">In ogni server del cluster abilitare l'AG in Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="20d5a-329">Aprire Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-329">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="20d5a-330">Nell'albero a sinistra dello schermo fare clic su **servizi SQL Server** e quindi fare doppio clic sul servizio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-330">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="20d5a-331">Nella casella **Proprietà** selezionare la scheda **disponibilità elevata AlwaysOn** . Selezionare la casella di controllo **Abilita gruppi di disponibilità AlwaysOn** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-331">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="20d5a-332">Quando richiesto, riavviare il servizio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-332">Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="20d5a-333">Creare il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="20d5a-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="20d5a-334">Aprire SQL Server Management Studio e connettersi all'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20d5a-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="20d5a-335">In Esplora oggetti espandere la cartella **Always on High Availability** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="20d5a-336">Fare clic con il pulsante destro del mouse sulla cartella **gruppi di disponibilità** e scegliere **nuova procedura guidata gruppo di disponibilità**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="20d5a-337">Se viene visualizzata la pagina **Introduzione** , fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-338">Nella pagina **specificare il nome del gruppo di disponibilità** , digitare il nome del gruppo di disponibilità e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-339">Nella pagina Seleziona database selezionare i database che si desidera includere nell'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="20d5a-340">Scegliere il pulsante **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="20d5a-341">Non includere i database **ReportServer**, **ReportServerTempDB** o Persistent Chat nell'AG, in quanto questi non sono supportati in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="20d5a-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="20d5a-342">È possibile includere tutti gli altri database di Skype for Business Server nell'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="20d5a-343">Nella pagina **Specifica repliche** fare clic sulla scheda **repliche** . Fare quindi clic sul pulsante **Aggiungi repliche** e connettersi alle altre istanze di SQL aggiunte come nodi di WSFC.</span><span class="sxs-lookup"><span data-stu-id="20d5a-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="20d5a-344">Per ogni istanza, selezionare il **failover automatico** e le opzioni di **commit sincrono** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-344">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="20d5a-345">Non selezionare l'opzione **secondaria leggibile** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-345">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="20d5a-346">Fare clic sulla scheda **endpoint** e verificare che il **numero di porta** sia impostato su 5022.</span><span class="sxs-lookup"><span data-stu-id="20d5a-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="20d5a-347">Fare clic sulla scheda **listener** e selezionare l'opzione **Crea un listener del gruppo di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="20d5a-347">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="20d5a-348">In tale opzione digitare un nome per il listener e impostare la **porta** su 1433 (altre porte non sono supportate per questa opzione).</span><span class="sxs-lookup"><span data-stu-id="20d5a-348">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="20d5a-349">Fare clic su **Aggiungi**, quindi nella casella **indirizzo IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="20d5a-350">Nella pagina **Seleziona sincronizzazione dati iniziale** selezionare completo e specificare una cartella accessibile alle repliche e che l'account di servizio di SQL Server utilizzato da entrambe le repliche disponga delle autorizzazioni di scrittura per.</span><span class="sxs-lookup"><span data-stu-id="20d5a-350">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="20d5a-351">Scegliere il pulsante **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-351">Then click **Next**.</span></span>
    
     <span data-ttu-id="20d5a-352">Questa condivisione file verrà utilizzata temporaneamente quando si inizializzano i database.</span><span class="sxs-lookup"><span data-stu-id="20d5a-352">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="20d5a-353">Se si ha a che fare con database di grandi dimensioni, è consigliabile inizializzarli manualmente se la larghezza di banda di rete non è in grado di soddisfare le dimensioni dei backup del database.</span><span class="sxs-lookup"><span data-stu-id="20d5a-353">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="20d5a-354">Nella pagina Convalida verificare che tutti i controlli di convalida siano stati eseguiti correttamente e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="20d5a-355">Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su fine.</span><span class="sxs-lookup"><span data-stu-id="20d5a-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="20d5a-356">Creare un nuovo archivio che specifichi il listener AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="20d5a-357">Apre lo strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="20d5a-357">Open Topology Builder.</span></span> <span data-ttu-id="20d5a-358">Nella topologia espandere **componenti condivisi**, fare clic con il pulsante destro del mouse su **Archivi SQL Server** e scegliere **nuovo archivio SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="20d5a-359">Nella pagina **Definisci nuovo archivio SQL** selezionare la casella di controllo **Impostazioni disponibilità elevata** e quindi verificare che nella casella a discesa vengano visualizzati i gruppi di disponibilità di SQL AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="20d5a-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="20d5a-360">Nella casella **nome di dominio completo listener di disponibilità di SQL Server** Digitare il nome di dominio completo del listener creato durante la creazione del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="20d5a-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="20d5a-361">Nella casella **FQDN di SQL Server** , digitare il nome di dominio completo del nodo primario dell'AG, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="20d5a-362">Associare il nuovo gruppo di disponibilità sempre con il pool Front end.</span><span class="sxs-lookup"><span data-stu-id="20d5a-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="20d5a-363">In Generatore di topologie fare clic con il pulsante destro del mouse sul pool da associare all'AG e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="20d5a-364">In **associazioni**, nella casella **Archivio SQL Server** Selezionare l'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="20d5a-365">Selezionare lo stesso gruppo per qualsiasi altro database del pool che si desidera spostare nell'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="20d5a-366">Quando si è certi che tutti i database necessari sono impostati sull'AG, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="20d5a-367">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="20d5a-367">Publish the topology.</span></span> <span data-ttu-id="20d5a-368">Dal menu **azione** fare clic su **topologia** e quindi su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="20d5a-369">Nella pagina di conferma fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="20d5a-370">Eseguire alcuni passaggi finali per assicurarsi che gli account di accesso di SQL siano su ognuna delle repliche nell'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="20d5a-371">Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="20d5a-372">Espandi Skype for Business Server, Espandi la topologia ed Espandi gli **archivi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="20d5a-373">Fare clic con il pulsante destro del mouse sull'archivio SQL della nuova AG e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="20d5a-374">Nella parte inferiore della pagina, nella casella **FQDN di SQL Server** , impostare il valore sul nome di dominio completo del listener dell'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="20d5a-375">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="20d5a-375">Publish the topology.</span></span> <span data-ttu-id="20d5a-376">Dal menu **azione** fare clic su **topologia** e quindi su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-376">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="20d5a-377">Nella pagina di conferma fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20d5a-377">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="20d5a-378">Attendere quindi alcuni minuti per la replica della nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="20d5a-378">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="20d5a-379">Aprire SQL Server Management Studio e passare all'AG.</span><span class="sxs-lookup"><span data-stu-id="20d5a-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="20d5a-380">Eseguire il failover su una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="20d5a-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="20d5a-381">Aprire Skype for Business Server Management Shell e digitare il seguente cmdlet per creare gli account di accesso di SQL in questa replica:</span><span class="sxs-lookup"><span data-stu-id="20d5a-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="20d5a-382">Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria e quindi utilizzare  `Install-CsDatabase -Update` ) per ogni replica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="20d5a-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
