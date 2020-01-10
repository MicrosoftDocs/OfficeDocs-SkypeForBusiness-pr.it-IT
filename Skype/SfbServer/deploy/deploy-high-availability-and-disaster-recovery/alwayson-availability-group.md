---
title: Distribuire un gruppo di disponibilità sempre in un server back-end in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Distribuire (installare) un gruppo sempre disponibile nella distribuzione di Skype for Business Server.
ms.openlocfilehash: eadf3c67f5d2618d7070c2a3540c2a9ad08b5942
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002916"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="a593b-103">Distribuire un gruppo di disponibilità sempre in un server back-end in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a593b-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="a593b-104">Deploy (Install) Always on Availability Group (AG) nella distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a593b-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="a593b-105">La modalità di distribuzione di un AG varia a seconda che la distribuzione venga distribuita in un nuovo pool, in un pool esistente che usa il mirroring o in un pool esistente che attualmente non ha una disponibilità elevata per il database back-end.</span><span class="sxs-lookup"><span data-stu-id="a593b-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a593b-106">L'uso di un AG con un ruolo del server di chat persistente non è supportato.</span><span class="sxs-lookup"><span data-stu-id="a593b-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="a593b-107">Distribuire un gruppo di disponibilità sempre in un nuovo pool Front-End</span><span class="sxs-lookup"><span data-stu-id="a593b-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="a593b-108">Distribuire un gruppo di disponibilità sempre disponibile in un pool esistente che usa il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="a593b-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="a593b-109">Distribuire un gruppo di disponibilità sempre disponibile in un pool esistente che non usa il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="a593b-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="a593b-110">Distribuire un gruppo di disponibilità sempre in un nuovo pool Front-End</span><span class="sxs-lookup"><span data-stu-id="a593b-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="a593b-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="a593b-111"></span></span>

1. <span data-ttu-id="a593b-112">Abilitare la caratteristica clustering di failover in tutti i server di database che faranno parte dell'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="a593b-113">In ogni server eseguire le operazioni seguenti</span><span class="sxs-lookup"><span data-stu-id="a593b-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="a593b-114">Aprire Server Manager e fare clic su **Aggiungi ruoli e funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a593b-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="a593b-115">Fare clic su **Avanti** fino a raggiungere la casella **Seleziona funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="a593b-115">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="a593b-116">Selezionare la casella di controllo **clustering di failover** .</span><span class="sxs-lookup"><span data-stu-id="a593b-116">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="a593b-117">Nella casella **Aggiungi funzionalità necessarie per il clustering di failover** fare clic su **Aggiungi funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a593b-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="a593b-118">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="a593b-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="a593b-119">Convalidare la configurazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="a593b-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="a593b-120">In Server Manager fare clic sul menu **strumenti** e quindi su **Gestione cluster di failover**.</span><span class="sxs-lookup"><span data-stu-id="a593b-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="a593b-121">In **azioni** sul lato destro dello schermo fare clic su **Convalida configurazione**.</span><span class="sxs-lookup"><span data-stu-id="a593b-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="a593b-122">Nella pagina **prima di iniziare** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-123">Selezionare i server da aggiungere al cluster e quindi fare clic su **Esegui tutti i test**.</span><span class="sxs-lookup"><span data-stu-id="a593b-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="a593b-124">Nella casella **Riepilogo** verificare gli eventuali errori segnalati dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a593b-124">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="a593b-125">Quindi fare clic su **fine** per completare la convalida.</span><span class="sxs-lookup"><span data-stu-id="a593b-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="a593b-126">La procedura guidata riporterà probabilmente diversi avvisi, soprattutto se non si usa lo spazio di archiviazione condiviso.</span><span class="sxs-lookup"><span data-stu-id="a593b-126">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="a593b-127">Non è necessario usare lo spazio di archiviazione condiviso.</span><span class="sxs-lookup"><span data-stu-id="a593b-127">You are not required to use shared storage.</span></span> <span data-ttu-id="a593b-128">Tuttavia, se vengono visualizzati messaggi di **errore** , è necessario correggere questi problemi prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a593b-128">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="a593b-129">Creare il cluster di failover di Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="a593b-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="a593b-130">Nella **Gestione guidata cluster di failover** fare clic con il pulsante destro del mouse su **Gestione cluster di failover**, quindi scegliere **Crea cluster**.</span><span class="sxs-lookup"><span data-stu-id="a593b-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="a593b-131">Nella pagina **prima di iniziare** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-132">Aggiungere il nome del cluster e l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="a593b-132">Add the cluster name and IP address.</span></span> <span data-ttu-id="a593b-133">Dopo aver convalidato le impostazioni, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-133">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-134">Nella pagina di conferma fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-135">Dopo aver creato il cluster, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="a593b-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="a593b-136">È consigliabile configurare le impostazioni del quorum del cluster per l'uso di un witness di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="a593b-136">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="a593b-137">A questo scopo, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a593b-137">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="a593b-138">Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **altre azioni**e fare clic su **Configura impostazioni quorum cluster**.</span><span class="sxs-lookup"><span data-stu-id="a593b-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="a593b-139">Nella pagina **selezionare l'opzione di configurazione quorum** fare clic su **Seleziona il testimone quorum**.</span><span class="sxs-lookup"><span data-stu-id="a593b-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="a593b-140">Nella pagina **Select quorum Witness** fare clic su **configura un witness di condivisione file**.</span><span class="sxs-lookup"><span data-stu-id="a593b-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="a593b-141">Nella pagina **Configura il witness di condivisione file** Digitare il percorso della condivisione di file che si vuole usare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-142">Nella pagina di **conferma** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="a593b-143">In ogni server del cluster abilitare la caratteristica AG in Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a593b-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="a593b-144">Aprire Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a593b-144">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="a593b-145">Nell'albero sul lato sinistro dello schermo fare clic su **servizi SQL Server**, quindi fare doppio clic sul servizio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a593b-145">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="a593b-146">Nella casella **Proprietà** selezionare la scheda **AlwaysOn High Availability** . Selezionare la casella di controllo **Abilita gruppi di disponibilità AlwaysOn** .</span><span class="sxs-lookup"><span data-stu-id="a593b-146">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="a593b-147">Riavviare il servizio SQL Server quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="a593b-147">Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="a593b-148">USA generatore di topologie per creare il pool Front-End, come spiegato in [creare e pubblicare una nuova topologia in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="a593b-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="a593b-149">Quando si esegue questa operazione, specificare l'AG come SQL Store per il pool.</span><span class="sxs-lookup"><span data-stu-id="a593b-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="a593b-150">Creare il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="a593b-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="a593b-151">Aprire SQL Server Management Studio e connettersi all'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a593b-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="a593b-152">In Esplora oggetti Espandi la cartella **sempre in alta disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="a593b-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="a593b-153">Fare clic con il pulsante destro del mouse sulla cartella **gruppi** di disponibilità e scegliere **nuova creazione guidata gruppo di disponibilità**.</span><span class="sxs-lookup"><span data-stu-id="a593b-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="a593b-154">Se viene visualizzata la pagina **Introduzione** , fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-155">Nella pagina **specificare il nome del gruppo di disponibilità** Digitare il nome del gruppo di disponibilità e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-156">Nella pagina Selezione database selezionare i database che si desidera includere nel gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="a593b-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="a593b-157">Quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="a593b-158">Non includere i database **ReportServer**, **ReportServerTempDB**o Persistent Chat nel gruppo di disponibilità AlwaysOn, perché non sono supportati in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="a593b-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="a593b-159">Puoi includere tutti gli altri database di Skype for Business Server nel gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="a593b-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="a593b-160">Nella pagina **Specifica repliche** fare clic sulla scheda **repliche** . Fare quindi clic sul pulsante **Aggiungi repliche** e connettersi alle altre istanze di SQL aggiunte come nodi del cluster di failover di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a593b-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="a593b-161">Per ogni istanza, selezionare il **failover automatico** e le opzioni di **commit sincrono** .</span><span class="sxs-lookup"><span data-stu-id="a593b-161">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="a593b-162">Non selezionare l'opzione **secondaria leggibile** .</span><span class="sxs-lookup"><span data-stu-id="a593b-162">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="a593b-163">Fare clic sulla scheda **endpoint** e verificare che il **numero di porta** sia impostato su 5022.</span><span class="sxs-lookup"><span data-stu-id="a593b-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="a593b-164">Fare clic sulla scheda **listener** e selezionare l'opzione **Crea un gruppo di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="a593b-164">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="a593b-165">In tale opzione digitare un nome per il listener e impostare la **porta** su 1433 (le altre porte non sono supportate per questa opzione).</span><span class="sxs-lookup"><span data-stu-id="a593b-165">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="a593b-166">Fare clic su **Aggiungi**e quindi nella casella **indirizzo IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a593b-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="a593b-167">Nella pagina **Seleziona sincronizzazione dati iniziale** selezionare completo e specificare una cartella accessibile alle repliche e che l'account del servizio SQL Server usato da entrambe le repliche disponga delle autorizzazioni di scrittura per.</span><span class="sxs-lookup"><span data-stu-id="a593b-167">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="a593b-168">Quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-168">Then click **Next**.</span></span>
    
     <span data-ttu-id="a593b-169">Questa condivisione file verrà usata temporaneamente quando si inizializzano i database.</span><span class="sxs-lookup"><span data-stu-id="a593b-169">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="a593b-170">Se si gestiscono database di grandi dimensioni, è consigliabile inizializzarli manualmente nel caso in cui la larghezza di banda della rete non possa contenere le dimensioni dei backup del database.</span><span class="sxs-lookup"><span data-stu-id="a593b-170">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="a593b-171">Nella pagina Convalida verificare che tutti i controlli di convalida abbiano esito positivo e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-172">Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su fine.</span><span class="sxs-lookup"><span data-stu-id="a593b-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="a593b-173">Dopo la distribuzione del pool e dell'AG, eseguire alcuni passaggi finali per verificare che gli accessi SQL si trovino in ognuna delle repliche del gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="a593b-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="a593b-174">Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a593b-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="a593b-175">Espandi Skype for Business Server, Espandi la topologia ed Espandi gli **archivi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a593b-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="a593b-176">Fare clic con il pulsante destro del mouse sull'archivio SQL del nuovo gruppo di disponibilità AlwaysOn e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a593b-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="a593b-177">Nella parte inferiore della pagina, nella casella **FQDN di SQL Server** , cambiare il valore con il nome di dominio completo del listener dell'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="a593b-178">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="a593b-178">Publish the topology.</span></span> <span data-ttu-id="a593b-179">Nel menu **azioni** fare clic su **topologia** e quindi su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="a593b-179">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="a593b-180">Nella pagina di conferma fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-180">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="a593b-181">Attendere alcuni minuti per la replica della nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="a593b-181">Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="a593b-182">Aprire SQL Server Management Studio e passare all'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="a593b-183">Fallire in una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="a593b-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="a593b-184">Aprire Skype for Business Server Management Shell e digitare il cmdlet seguente per creare gli account di accesso SQL in questa replica:</span><span class="sxs-lookup"><span data-stu-id="a593b-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="a593b-185">Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria e quindi `Install-CsDatabase -Update`usare) per ogni replica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="a593b-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="a593b-186">Distribuire un gruppo di disponibilità sempre disponibile in un pool esistente che usa il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="a593b-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="a593b-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="a593b-187"></span></span>

> [!NOTE]
> <span data-ttu-id="a593b-188">Se il pool in cui si esegue l'aggiornamento a un AG ospita l'Central Management store per l'organizzazione, è necessario prima di tutto trasferire il CMS in un altro pool prima di aggiornare questo pool.</span><span class="sxs-lookup"><span data-stu-id="a593b-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="a593b-189">Usa il cmdlet Move-CsManagementServer per trasferire il pool.</span><span class="sxs-lookup"><span data-stu-id="a593b-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="a593b-190">Se non si dispone di un altro pool nell'organizzazione, è possibile distribuire temporaneamente un server Standard Edition e trasferire il CMS in questo server prima di eseguire l'aggiornamento del pool all'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="a593b-191">Non eseguire il failover di tutti i dati dal mirror al nodo Principal aprendo Skype for Business Server Management Shell e digitando il cmdlet seguente.</span><span class="sxs-lookup"><span data-stu-id="a593b-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="a593b-192">Ripetere questo cmdlet per ogni tipo di database nel pool.</span><span class="sxs-lookup"><span data-stu-id="a593b-192">Repeat this cmdlet for each database type in the pool.</span></span> <span data-ttu-id="a593b-193">Puoi usare il cmdlet seguente per trovare tutti i tipi di database archiviati in questo pool.</span><span class="sxs-lookup"><span data-stu-id="a593b-193">You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="a593b-194">USA generatore di topologia per rimuovere il mirroring del database dal pool.</span><span class="sxs-lookup"><span data-stu-id="a593b-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="a593b-195">Aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="a593b-195">Open Topology Builder.</span></span> <span data-ttu-id="a593b-196">Nella topologia espandere **pool Enterprise Edition front-end**, fare clic con il pulsante destro del mouse sul nome del pool e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a593b-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="a593b-197">Per ogni tipo di archivio SQL nel pool, deselezionare la casella di controllo **Abilita mirroring di SQL Store** .</span><span class="sxs-lookup"><span data-stu-id="a593b-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="a593b-198">Pubblicare la topologia modificata.</span><span class="sxs-lookup"><span data-stu-id="a593b-198">Publish the changed topology.</span></span> <span data-ttu-id="a593b-199">Nel menu **azioni** fare clic su **topologia** e quindi su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="a593b-199">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="a593b-200">Nella pagina di conferma fare clic su **Avanti**</span><span class="sxs-lookup"><span data-stu-id="a593b-200">Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="a593b-201">Usare SQL Server Management Studio per suddividere lo specchio.</span><span class="sxs-lookup"><span data-stu-id="a593b-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="a593b-202">Aprire SQL Server Management Studio, passare ai database, fare clic con il pulsante destro del mouse su **attività** e scegliere **Specchia**.</span><span class="sxs-lookup"><span data-stu-id="a593b-202">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**.</span></span> <span data-ttu-id="a593b-203">Quindi fare clic su **Rimuovi mirroring** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a593b-203">Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="a593b-204">Ripetere questa operazione per tutti i database del pool che verranno convertiti in un AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="a593b-205">Configurare la funzionalità di clustering di failover in tutti i server di database che faranno parte dell'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="a593b-206">In ogni server eseguire le operazioni seguenti</span><span class="sxs-lookup"><span data-stu-id="a593b-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="a593b-207">Aprire Server Manager e fare clic su **Aggiungi ruoli e funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a593b-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="a593b-208">Fare clic su **Avanti** fino a raggiungere la casella **Seleziona funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="a593b-208">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="a593b-209">Selezionare la casella di controllo **clustering di failover** .</span><span class="sxs-lookup"><span data-stu-id="a593b-209">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="a593b-210">Nella casella **Aggiungi funzionalità necessarie per il clustering di failover** fare clic su **Aggiungi funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a593b-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="a593b-211">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="a593b-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="a593b-212">Convalidare la configurazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="a593b-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="a593b-213">In Server Manager fare clic sul menu **strumenti** e quindi su **Gestione cluster di failover**.</span><span class="sxs-lookup"><span data-stu-id="a593b-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="a593b-214">In **azioni** sul lato destro dello schermo fare clic su **Convalida configurazione**.</span><span class="sxs-lookup"><span data-stu-id="a593b-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="a593b-215">Nella pagina **prima di iniziare** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-216">Selezionare i server da aggiungere al cluster e quindi fare clic su **Esegui tutti i test**.</span><span class="sxs-lookup"><span data-stu-id="a593b-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="a593b-217">Nella casella **Riepilogo** verificare gli eventuali errori segnalati dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a593b-217">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="a593b-218">Quindi fare clic su **fine** per completare la convalida.</span><span class="sxs-lookup"><span data-stu-id="a593b-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="a593b-219">La procedura guidata riporterà probabilmente diversi avvisi, soprattutto se non si usa lo spazio di archiviazione condiviso.</span><span class="sxs-lookup"><span data-stu-id="a593b-219">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="a593b-220">Non è necessario usare lo spazio di archiviazione condiviso.</span><span class="sxs-lookup"><span data-stu-id="a593b-220">You are not required to use shared storage.</span></span> <span data-ttu-id="a593b-221">Tuttavia, se vengono visualizzati messaggi di **errore** , è necessario correggere questi problemi prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a593b-221">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="a593b-222">Creare il cluster di failover di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a593b-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="a593b-223">Nella **Gestione guidata cluster di failover** fare clic con il pulsante destro del mouse su **Gestione cluster di failover**, quindi scegliere **Crea cluster**.</span><span class="sxs-lookup"><span data-stu-id="a593b-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="a593b-224">Nella pagina **prima di iniziare** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-225">Aggiungere il nome del cluster e l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="a593b-225">Add the cluster name and IP address.</span></span> <span data-ttu-id="a593b-226">Dopo aver convalidato le impostazioni, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-226">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-227">Nella pagina di conferma fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-228">Dopo aver creato il cluster, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="a593b-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="a593b-229">È consigliabile configurare le impostazioni del quorum del cluster per l'uso di un witness di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="a593b-229">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="a593b-230">A questo scopo, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a593b-230">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="a593b-231">Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **altre azioni**e fare clic su **Configura impostazioni quorum cluster**.</span><span class="sxs-lookup"><span data-stu-id="a593b-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="a593b-232">Nella pagina **selezionare l'opzione di configurazione quorum** fare clic su **Seleziona il testimone quorum**.</span><span class="sxs-lookup"><span data-stu-id="a593b-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="a593b-233">Nella pagina **Select quorum Witness** fare clic su **configura un witness di condivisione file**.</span><span class="sxs-lookup"><span data-stu-id="a593b-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="a593b-234">Nella pagina **Configura il witness di condivisione file** Digitare il percorso della condivisione di file che si vuole usare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-235">Nella pagina di **conferma** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="a593b-236">In ogni server del cluster abilitare la caratteristica AG in Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a593b-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="a593b-237">Aprire Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a593b-237">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="a593b-238">Nell'albero sul lato sinistro dello schermo fare clic su **servizi SQL Server**, quindi fare doppio clic sul servizio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a593b-238">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="a593b-239">Nella casella **Proprietà** selezionare la scheda **AlwaysOn High Availability** . Selezionare la casella di controllo **Abilita gruppi di disponibilità AlwaysOn** .</span><span class="sxs-lookup"><span data-stu-id="a593b-239">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="a593b-240">Riavviare il servizio SQL Server quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="a593b-240">Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="a593b-241">Creare il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="a593b-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="a593b-242">Aprire SQL Server Management Studio e connettersi all'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a593b-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="a593b-243">In Esplora oggetti Espandi la cartella **sempre in alta disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="a593b-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="a593b-244">Fare clic con il pulsante destro del mouse sulla cartella **gruppi** di disponibilità e scegliere **nuova creazione guidata gruppo di disponibilità**.</span><span class="sxs-lookup"><span data-stu-id="a593b-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="a593b-245">Se viene visualizzata la pagina **Introduzione** , fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="a593b-246">Nella pagina **specificare il nome del gruppo di disponibilità** Digitare il nome del gruppo di disponibilità e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="a593b-247">Nella pagina Selezione database selezionare i database che si desidera includere nel gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="a593b-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="a593b-248">Quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="a593b-249">Non includere i database **ReportServer**, **ReportServerTempDB**o Persistent Chat nel gruppo di disponibilità AlwaysOn, perché non sono supportati in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="a593b-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="a593b-250">Puoi includere tutti gli altri database di Skype for Business Server nel gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="a593b-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="a593b-251">Nella pagina **Specifica repliche** fare clic sulla scheda **repliche** . Fare quindi clic sul pulsante **Aggiungi repliche** e connettersi alle altre istanze di SQL aggiunte come nodi del cluster di failover di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a593b-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="a593b-252">Per ogni istanza, selezionare il **failover automatico** e le opzioni di **commit sincrono** .</span><span class="sxs-lookup"><span data-stu-id="a593b-252">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="a593b-253">Non selezionare l'opzione **secondaria leggibile** .</span><span class="sxs-lookup"><span data-stu-id="a593b-253">Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="a593b-254">Fare clic sulla scheda **endpoint** e verificare che il **numero di porta** sia impostato su 5022.</span><span class="sxs-lookup"><span data-stu-id="a593b-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="a593b-255">Fare clic sulla scheda **listener** e selezionare l'opzione **Crea un gruppo di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="a593b-255">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="a593b-256">In tale opzione digitare un nome per il listener e impostare la **porta** su 1433 (le altre porte non sono supportate per questa opzione).</span><span class="sxs-lookup"><span data-stu-id="a593b-256">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="a593b-257">Fare clic su **Aggiungi**e quindi nella casella **indirizzo IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a593b-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="a593b-258">Nella pagina **Seleziona sincronizzazione dati iniziale** selezionare completo e specificare una cartella accessibile alle repliche e che l'account del servizio SQL Server usato da entrambe le repliche disponga delle autorizzazioni di scrittura per.</span><span class="sxs-lookup"><span data-stu-id="a593b-258">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="a593b-259">Quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-259">Then click **Next**.</span></span>
    
    <span data-ttu-id="a593b-260">Questa condivisione file verrà usata temporaneamente quando si inizializzano i database.</span><span class="sxs-lookup"><span data-stu-id="a593b-260">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="a593b-261">Se si gestiscono database di grandi dimensioni, è consigliabile inizializzarli manualmente nel caso in cui la larghezza di banda della rete non possa contenere le dimensioni dei backup del database.</span><span class="sxs-lookup"><span data-stu-id="a593b-261">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="a593b-262">Nella pagina Convalida verificare che tutti i controlli di convalida abbiano esito positivo e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="a593b-263">Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su fine.</span><span class="sxs-lookup"><span data-stu-id="a593b-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="a593b-264">Creare un nuovo archivio specificando il listener AG e specificando l'entità del mirror precedente come nodo principale dell'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="a593b-265">Aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="a593b-265">Open Topology Builder.</span></span> <span data-ttu-id="a593b-266">Espandere **componenti condivisi**nella topologia, fare clic con il pulsante destro del mouse su **Archivi SQL Server**e scegliere **nuovo archivio SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a593b-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="a593b-267">Nella pagina **Definisci nuovo archivio SQL** selezionare la casella di controllo **impostazioni di disponibilità elevata** e quindi verificare che i gruppi di disponibilità di SQL AlwaysOn vengano visualizzati nella casella di selezione.</span><span class="sxs-lookup"><span data-stu-id="a593b-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="a593b-268">Nella casella **FQDN listener di disponibilità di SQL Server** Digitare il nome di dominio completo del listener creato quando è stato creato il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="a593b-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="a593b-269">Nella casella **FQDN di SQL Server** Digitare il nome di dominio completo del nodo principale dell'AG e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a593b-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="a593b-270">Dovrebbe essere l'entità del mirror precedente per questo archivio.</span><span class="sxs-lookup"><span data-stu-id="a593b-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="a593b-271">Associa la nuova AG al pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="a593b-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="a593b-272">In Generatore di topologie fare clic con il pulsante destro del mouse sul pool da associare all'AG e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a593b-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="a593b-273">In **associazioni**selezionare l'AG nella casella **Archivio SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="a593b-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="a593b-274">Selezionare lo stesso gruppo per qualsiasi altro database nel pool che si vuole trasferire all'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="a593b-275">Quando si è certi che tutti i database necessari siano impostati su AG, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a593b-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="a593b-276">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="a593b-276">Publish the topology.</span></span> <span data-ttu-id="a593b-277">Nel menu **azioni** fare clic su **topologia** e quindi su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="a593b-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="a593b-278">Nella pagina di conferma fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="a593b-279">Eseguire alcuni passaggi finali per verificare che gli accessi SQL si trovino in ognuna delle repliche del gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="a593b-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="a593b-280">Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a593b-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="a593b-281">Espandi Skype for Business Server, Espandi la topologia ed Espandi gli **archivi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a593b-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="a593b-282">Fare clic con il pulsante destro del mouse sull'SQL Store della nuova AG e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a593b-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="a593b-283">Nella parte inferiore della pagina, nella casella **FQDN di SQL Server** , cambiare il valore con il nome di dominio completo del listener dell'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="a593b-284">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="a593b-284">Publish the topology.</span></span> <span data-ttu-id="a593b-285">Nel menu **azioni** fare clic su **topologia** e quindi su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="a593b-285">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="a593b-286">Nella pagina di conferma fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-286">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="a593b-287">Attendere alcuni minuti per la replica della nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="a593b-287">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="a593b-288">Aprire SQL Server Management Studio e passare all'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="a593b-289">Fallire in una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="a593b-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="a593b-290">Aprire Skype for Business Server Management Shell e digitare il cmdlet seguente per creare gli account di accesso SQL in questa replica:</span><span class="sxs-lookup"><span data-stu-id="a593b-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="a593b-291">Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria e quindi `Install-CsDatabase -Update`usare) per ogni replica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="a593b-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="a593b-292">Distribuire un gruppo di disponibilità sempre disponibile in un pool esistente che non usa il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="a593b-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="a593b-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="a593b-293"></span></span>

> [!NOTE]
> <span data-ttu-id="a593b-294">Se il pool in cui si esegue l'aggiornamento a un AG ospita l'Central Management store per l'organizzazione, è necessario prima di tutto trasferire il CMS in un altro pool prima di aggiornare questo pool.</span><span class="sxs-lookup"><span data-stu-id="a593b-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="a593b-295">Usa il cmdlet Move-CsManagementServer per trasferire il pool.</span><span class="sxs-lookup"><span data-stu-id="a593b-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="a593b-296">Se non si dispone di un altro pool nell'organizzazione, è possibile distribuire temporaneamente un server Standard Edition e trasferire il CMS in questo server prima di eseguire l'aggiornamento del pool all'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="a593b-297">Configurare la funzionalità di clustering di failover in tutti i server di database che faranno parte dell'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="a593b-298">In ogni server eseguire le operazioni seguenti</span><span class="sxs-lookup"><span data-stu-id="a593b-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="a593b-299">Aprire Server Manager e fare clic su **Aggiungi ruoli e funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a593b-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="a593b-300">Fare clic su **Avanti** fino a raggiungere la casella **Seleziona funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="a593b-300">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="a593b-301">Selezionare la casella di controllo **clustering di failover** .</span><span class="sxs-lookup"><span data-stu-id="a593b-301">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="a593b-302">Nella casella **Aggiungi funzionalità necessarie per il clustering di failover** fare clic su **Aggiungi funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a593b-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="a593b-303">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="a593b-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="a593b-304">Convalidare la configurazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="a593b-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="a593b-305">In Server Manager fare clic sul menu **strumenti** e quindi su **Gestione cluster di failover**.</span><span class="sxs-lookup"><span data-stu-id="a593b-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="a593b-306">In **azioni** sul lato destro dello schermo fare clic su **Convalida configurazione**.</span><span class="sxs-lookup"><span data-stu-id="a593b-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="a593b-307">Nella pagina **prima di iniziare** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-308">Selezionare i server da aggiungere al cluster e quindi fare clic su **Esegui tutti i test**.</span><span class="sxs-lookup"><span data-stu-id="a593b-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="a593b-309">Nella casella **Riepilogo** verificare gli eventuali errori segnalati dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a593b-309">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="a593b-310">Quindi fare clic su **fine** per completare la convalida.</span><span class="sxs-lookup"><span data-stu-id="a593b-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="a593b-311">La procedura guidata riporterà probabilmente diversi avvisi, soprattutto se non si usa lo spazio di archiviazione condiviso.</span><span class="sxs-lookup"><span data-stu-id="a593b-311">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="a593b-312">Non è necessario usare lo spazio di archiviazione condiviso.</span><span class="sxs-lookup"><span data-stu-id="a593b-312">You are not required to use shared storage.</span></span> <span data-ttu-id="a593b-313">Tuttavia, se vengono visualizzati messaggi di **errore** , è necessario correggere questi problemi prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a593b-313">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="a593b-314">Creare il cluster di failover di Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="a593b-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="a593b-315">Nella **Gestione guidata cluster di failover** fare clic con il pulsante destro del mouse su **Gestione cluster di failover**, quindi scegliere **Crea cluster**.</span><span class="sxs-lookup"><span data-stu-id="a593b-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="a593b-316">Nella pagina **prima di iniziare** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-317">Aggiungere il nome del cluster e l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="a593b-317">Add the cluster name and IP address.</span></span> <span data-ttu-id="a593b-318">Dopo aver convalidato le impostazioni, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-318">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-319">Nella pagina di conferma fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-320">Dopo aver creato il cluster, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="a593b-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="a593b-321">È consigliabile configurare le impostazioni del quorum del cluster per l'uso di un witness di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="a593b-321">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="a593b-322">A questo scopo, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a593b-322">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="a593b-323">Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **altre azioni**e fare clic su **Configura impostazioni quorum cluster**.</span><span class="sxs-lookup"><span data-stu-id="a593b-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="a593b-324">Nella pagina **selezionare l'opzione di configurazione quorum** fare clic su **Seleziona il testimone quorum**.</span><span class="sxs-lookup"><span data-stu-id="a593b-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="a593b-325">Nella pagina **Select quorum Witness** fare clic su **configura un witness di condivisione file**.</span><span class="sxs-lookup"><span data-stu-id="a593b-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="a593b-326">Nella pagina **Configura il witness di condivisione file** Digitare il percorso della condivisione di file che si vuole usare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-327">Nella pagina di **conferma** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="a593b-328">In ogni server del cluster abilitare AG in Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a593b-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="a593b-329">Aprire Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a593b-329">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="a593b-330">Nell'albero sul lato sinistro dello schermo fare clic su **servizi SQL Server**, quindi fare doppio clic sul servizio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a593b-330">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="a593b-331">Nella casella **Proprietà** selezionare la scheda **AlwaysOn High Availability** . Selezionare la casella di controllo **Abilita gruppi di disponibilità AlwaysOn** .</span><span class="sxs-lookup"><span data-stu-id="a593b-331">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="a593b-332">Riavviare il servizio SQL Server quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="a593b-332">Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="a593b-333">Creare il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="a593b-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="a593b-334">Aprire SQL Server Management Studio e connettersi all'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a593b-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="a593b-335">In Esplora oggetti Espandi la cartella **sempre in alta disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="a593b-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="a593b-336">Fare clic con il pulsante destro del mouse sulla cartella **gruppi** di disponibilità e scegliere **nuova creazione guidata gruppo di disponibilità**.</span><span class="sxs-lookup"><span data-stu-id="a593b-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="a593b-337">Se viene visualizzata la pagina **Introduzione** , fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-338">Nella pagina **specificare il nome del gruppo di disponibilità** Digitare il nome del gruppo di disponibilità e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-339">Nella pagina Selezione database selezionare i database che si desidera includere nell'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="a593b-340">Quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="a593b-341">Non includere i database **ReportServer**, **ReportServerTempDB**o Persistent Chat nell'AG, perché non sono supportati in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="a593b-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="a593b-342">Puoi includere tutti gli altri database di Skype for Business Server nell'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="a593b-343">Nella pagina **Specifica repliche** fare clic sulla scheda **repliche** . Fare quindi clic sul pulsante **Aggiungi repliche** e connettersi alle altre istanze di SQL aggiunte come nodi di WSFC.</span><span class="sxs-lookup"><span data-stu-id="a593b-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="a593b-344">Per ogni istanza, selezionare il **failover automatico** e le opzioni di **commit sincrono** .</span><span class="sxs-lookup"><span data-stu-id="a593b-344">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="a593b-345">Non selezionare l'opzione **secondaria leggibile** .</span><span class="sxs-lookup"><span data-stu-id="a593b-345">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="a593b-346">Fare clic sulla scheda **endpoint** e verificare che il **numero di porta** sia impostato su 5022.</span><span class="sxs-lookup"><span data-stu-id="a593b-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="a593b-347">Fare clic sulla scheda **listener** e selezionare l'opzione **Crea un gruppo di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="a593b-347">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="a593b-348">In tale opzione digitare un nome per il listener e impostare la **porta** su 1433 (le altre porte non sono supportate per questa opzione).</span><span class="sxs-lookup"><span data-stu-id="a593b-348">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="a593b-349">Fare clic su **Aggiungi**e quindi nella casella **indirizzo IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a593b-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="a593b-350">Nella pagina **Seleziona sincronizzazione dati iniziale** selezionare completo e specificare una cartella accessibile alle repliche e che l'account del servizio SQL Server usato da entrambe le repliche disponga delle autorizzazioni di scrittura per.</span><span class="sxs-lookup"><span data-stu-id="a593b-350">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="a593b-351">Quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-351">Then click **Next**.</span></span>
    
     <span data-ttu-id="a593b-352">Questa condivisione file verrà usata temporaneamente quando si inizializzano i database.</span><span class="sxs-lookup"><span data-stu-id="a593b-352">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="a593b-353">Se si gestiscono database di grandi dimensioni, è consigliabile inizializzarli manualmente nel caso in cui la larghezza di banda della rete non possa contenere le dimensioni dei backup del database.</span><span class="sxs-lookup"><span data-stu-id="a593b-353">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="a593b-354">Nella pagina Convalida verificare che tutti i controlli di convalida abbiano esito positivo e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="a593b-355">Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su fine.</span><span class="sxs-lookup"><span data-stu-id="a593b-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="a593b-356">Creare un nuovo archivio specificando il listener AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="a593b-357">Aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="a593b-357">Open Topology Builder.</span></span> <span data-ttu-id="a593b-358">Espandere **componenti condivisi**nella topologia, fare clic con il pulsante destro del mouse su **Archivi SQL Server**e scegliere **nuovo archivio SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a593b-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="a593b-359">Nella pagina **Definisci nuovo archivio SQL** selezionare la casella di controllo **impostazioni di disponibilità elevata** e quindi verificare che i gruppi di disponibilità di SQL AlwaysOn vengano visualizzati nella casella di selezione.</span><span class="sxs-lookup"><span data-stu-id="a593b-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="a593b-360">Nella casella **FQDN listener di disponibilità di SQL Server** Digitare il nome di dominio completo del listener creato quando è stato creato il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="a593b-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="a593b-361">Nella casella **FQDN di SQL Server** Digitare il nome di dominio completo del nodo principale dell'AG e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a593b-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="a593b-362">Associa il nuovo gruppo di disponibilità sempre con il pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="a593b-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="a593b-363">In Generatore di topologie fare clic con il pulsante destro del mouse sul pool da associare all'AG e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a593b-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="a593b-364">In **associazioni**selezionare l'AG nella casella **Archivio SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="a593b-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="a593b-365">Selezionare lo stesso gruppo per qualsiasi altro database nel pool che si vuole trasferire all'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="a593b-366">Quando si è certi che tutti i database necessari siano impostati su AG, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a593b-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="a593b-367">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="a593b-367">Publish the topology.</span></span> <span data-ttu-id="a593b-368">Nel menu **azioni** fare clic su **topologia** e quindi su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="a593b-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="a593b-369">Nella pagina di conferma fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="a593b-370">Eseguire alcuni passaggi finali per verificare che gli accessi SQL si trovino in ognuna delle repliche dell'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="a593b-371">Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a593b-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="a593b-372">Espandi Skype for Business Server, Espandi la topologia ed Espandi gli **archivi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a593b-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="a593b-373">Fare clic con il pulsante destro del mouse sull'SQL Store della nuova AG e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a593b-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="a593b-374">Nella parte inferiore della pagina, nella casella **FQDN di SQL Server** , cambiare il valore con il nome di dominio completo del listener dell'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="a593b-375">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="a593b-375">Publish the topology.</span></span> <span data-ttu-id="a593b-376">Nel menu **azioni** fare clic su **topologia** e quindi su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="a593b-376">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="a593b-377">Nella pagina di conferma fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a593b-377">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="a593b-378">Attendere alcuni minuti per la replica della nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="a593b-378">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="a593b-379">Aprire SQL Server Management Studio e passare all'AG.</span><span class="sxs-lookup"><span data-stu-id="a593b-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="a593b-380">Fallire in una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="a593b-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="a593b-381">Aprire Skype for Business Server Management Shell e digitare il cmdlet seguente per creare gli account di accesso SQL in questa replica:</span><span class="sxs-lookup"><span data-stu-id="a593b-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="a593b-382">Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria e quindi `Install-CsDatabase -Update`usare) per ogni replica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="a593b-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
