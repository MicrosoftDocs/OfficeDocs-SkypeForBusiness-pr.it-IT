---
title: Aggiornamento a Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: "Riepilogo: informazioni su come eseguire l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015. Scaricare una versione di valutazione gratuita di Skype for Business Server 2015 presso Microsoft Evaluation Center all' https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverIndirizzo:."
ms.openlocfilehash: c34cbc7ce1d755f093ac14bc85d78106216c450b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237859"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="e7a77-104">Aggiornamento a Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e7a77-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e7a77-105">**Riepilogo:** Informazioni su come eseguire l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e7a77-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="e7a77-106">Scaricare una versione di valutazione gratuita di Skype for Business Server 2015 dal [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="e7a77-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="e7a77-107">Usare le procedure descritte in questo documento per eseguire l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015 usando il generatore di topologia di Skype for Business Server e la nuova funzionalità di aggiornamento sul posto.</span><span class="sxs-lookup"><span data-stu-id="e7a77-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="e7a77-108">Se si vuole eseguire l'aggiornamento da Lync Server 2010 o Office Communications Server 2007 R2, vedere [pianificare l'aggiornamento a Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="e7a77-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e7a77-109">Gli aggiornamenti sul posto sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e7a77-109">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e7a77-110">La coesistenza affiancata è supportata, vedere [migrazione a Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="e7a77-110">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="e7a77-111">Eseguire l'aggiornamento da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7a77-111">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="e7a77-112">L'aggiornamento di Lync Server 2013 a Skype for Business Server 2015 prevede l'installazione del software prerequisito, usando il generatore di topologia di Skype for Business Server per aggiornare i database nel pool e l'uso dell'aggiornamento sul posto di Skype for Business Server su ogni Server associati al pool.</span><span class="sxs-lookup"><span data-stu-id="e7a77-112">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="e7a77-113">Per completare l'aggiornamento, fare clic su otto passaggi in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e7a77-113">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="e7a77-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e7a77-114">Before you begin</span></span>

- <span data-ttu-id="e7a77-115">Rivedere il [piano per l'aggiornamento a Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="e7a77-115">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="e7a77-116">Rivedere [i requisiti del server per Skype for Business server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7a77-116">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="e7a77-117">[Installare prerequisiti per Skype for Business Server 2015](install/install-prerequisites.md) .</span><span class="sxs-lookup"><span data-stu-id="e7a77-117">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="e7a77-118">[Installare Skype for Business Server 2015](install/install.md) .</span><span class="sxs-lookup"><span data-stu-id="e7a77-118">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="e7a77-119">Passaggio 1: installare gli strumenti di amministrazione e scaricare la topologia</span><span class="sxs-lookup"><span data-stu-id="e7a77-119">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="e7a77-120">Connettersi al computer nella topologia in cui non è installato Lync OCSCore o altri componenti Lync.</span><span class="sxs-lookup"><span data-stu-id="e7a77-120">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="e7a77-121">Dal supporto di installazione di Skype for Business Server 2015, eseguire **Setup. exe** da **OCS_Volume\Setup\AMD64**.</span><span class="sxs-lookup"><span data-stu-id="e7a77-121">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="e7a77-122">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="e7a77-122">Click **Install**.</span></span> 
    
4. <span data-ttu-id="e7a77-123">Accettare il contratto di licenza.</span><span class="sxs-lookup"><span data-stu-id="e7a77-123">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="e7a77-124">Nella distribuzione guidata fare clic su **installa strumenti di amministrazione**e seguire la procedura da installare.</span><span class="sxs-lookup"><span data-stu-id="e7a77-124">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![Schermata della distribuzione guidata con il collegamento agli strumenti di amministratore di installazione richiamati.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="e7a77-126">Nella schermata Start di Windows aprire Generatore di topologia di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e7a77-126">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="e7a77-127">Fare clic su **Scarica topologia da distribuzione esistente**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e7a77-127">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="e7a77-128">Immettere un nome per la topologia e fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e7a77-128">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="e7a77-129">Accedere alla posizione in cui è stata salvata la topologia e creare una copia della topologia.</span><span class="sxs-lookup"><span data-stu-id="e7a77-129">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="e7a77-130">Passaggio 2: aggiornare e pubblicare la topologia usando generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="e7a77-130">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="e7a77-131">Prima di avviare il processo di aggiornamento, è necessario che tutti i servizi siano in esecuzione per i pool che si prevede di eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="e7a77-131">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="e7a77-132">In questo modo le modifiche della topologia verranno replicate nel database locale dei server nel pool.</span><span class="sxs-lookup"><span data-stu-id="e7a77-132">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="e7a77-133">Salvare una copia del file della topologia prima di eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="e7a77-133">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="e7a77-134">Dopo l'aggiornamento, non sarà possibile eseguire il downgrade della topologia. > se i servizi si trovano nello stesso server dei database, ad esempio il servizio chat persistente si trova nello stesso server del database della chat persistente, ignorare questo passaggio e passare al passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="e7a77-134">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="e7a77-135">Dopo aver smesso i servizi, eseguire la configurazione di aggiornamento sul posto in ogni server per aggiornare i database locali.</span><span class="sxs-lookup"><span data-stu-id="e7a77-135">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7a77-136">Se la topologia include un database back-end con mirroring, viene visualizzato sia l'oggetto Principal che i database con mirroring visualizzati **quando si pubblica la topologia** tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="e7a77-136">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder.</span></span> <span data-ttu-id="e7a77-137">Assicurarsi che tutti i database siano in uso nell'entità e selezionare solo l'entità, non lo specchio, quando si pubblica la topologia in caso contrario verrà visualizzato un avviso dopo la pubblicazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="e7a77-137">Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="e7a77-138">Selezionare una delle opzioni seguenti per aggiornare e pubblicare una nuova topologia usando il generatore di topologia di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e7a77-138">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="e7a77-139">Dopo aver completato la procedura e pubblicato la topologia aggiornata, passare al passaggio 3 in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e7a77-139">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="e7a77-140">Opzione 1: aggiornare un pool di front end isolato e gli archivi di archiviazione e monitoraggio associati</span><span class="sxs-lookup"><span data-stu-id="e7a77-140">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="e7a77-141">Se il pool che si sta aggiornando ha una dipendenza dell'archivio di archiviazione e monitoraggio, quando si usano i passaggi seguenti, verrà aggiornato anche l'archivio archiviazione e monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="e7a77-141">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="e7a77-142">In Generatore di topologie fare clic con il pulsante destro del mouse su un pool di Lync Server 2013, scegliere **Aggiorna a Skype for Business server 2015**e seguire la procedura.</span><span class="sxs-lookup"><span data-stu-id="e7a77-142">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Screenshot del menu di scelta rapida con l'opzione di aggiornamento per Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="e7a77-144">In Generatore di topologie fare clic su **azione** > **Pubblica topologia** o**topologia** > di **azione** > **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="e7a77-144">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![Schermata del menu azione con l'opzione Pubblica topologia in Generatore di topologie.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="e7a77-146">Durante la pubblicazione, scegliere di installare un database nell'archivio archiviazione e monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="e7a77-146">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="e7a77-147">Opzione 2: aggiornare il pool Front-end senza aggiornare gli archivi di archiviazione e monitoraggio</span><span class="sxs-lookup"><span data-stu-id="e7a77-147">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="e7a77-148">Se si usano i passaggi seguenti, l'archiviazione e il monitoraggio per il pool selezionato sono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="e7a77-148">If you use the following steps, archiving and monitoring for the selected pool are disabled.</span></span> <span data-ttu-id="e7a77-149">Dopo l'aggiornamento, il pool non avrà archivi di archiviazione e monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="e7a77-149">The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="e7a77-150">In Generatore di topologie selezionare il pool di Lync Server 2013 che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="e7a77-150">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="e7a77-151">Rimuovere la dipendenza dagli archivi di archiviazione e monitoraggio di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7a77-151">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="e7a77-152">Vai alle \*\*\*\* > **proprietà modifica**azione.</span><span class="sxs-lookup"><span data-stu-id="e7a77-152">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="e7a77-153">Deselezionare la casella di controllo **archiviazione** .</span><span class="sxs-lookup"><span data-stu-id="e7a77-153">Clear the **Archiving** check box.</span></span>
    
     ![Screenshot della casella di controllo archiviazione nella finestra di dialogo Modifica proprietà.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="e7a77-155">Deselezionare la casella di controllo **monitoraggio** .</span><span class="sxs-lookup"><span data-stu-id="e7a77-155">Clear the **Monitoring** check box.</span></span>
    
     ![Screenshot della finestra di dialogo Modifica proprietà che mostra la casella di controllo monitoraggio.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="e7a77-157">Fare clic con il pulsante destro del mouse sul pool di Lync Server 2013, scegliere **Aggiorna a Skype for Business server 2015**e seguire la procedura.</span><span class="sxs-lookup"><span data-stu-id="e7a77-157">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Screenshot del menu di scelta rapida con l'opzione di aggiornamento per Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="e7a77-159">In Generatore di topologie fare clic su **azione** > **Pubblica topologia** o**topologia** > di **azione** > **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="e7a77-159">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="e7a77-160">Opzione 3: aggiornare il pool Front-end e associarlo ai nuovi archivi di archiviazione e monitoraggio di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e7a77-160">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="e7a77-161">Se si usano i passaggi seguenti, l'archiviazione e il monitoraggio si arresteranno nello Store precedente e inizieranno nel nuovo Store creato.</span><span class="sxs-lookup"><span data-stu-id="e7a77-161">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="e7a77-162">In Generatore di topologie selezionare il pool di Lync Server 2013 che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="e7a77-162">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="e7a77-163">Rimuovere la dipendenza dagli archivi di archiviazione e monitoraggio di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7a77-163">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="e7a77-164">Vai alle \*\*\*\* > **proprietà modifica**azione.</span><span class="sxs-lookup"><span data-stu-id="e7a77-164">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="e7a77-165">Deselezionare la casella di controllo **archiviazione** .</span><span class="sxs-lookup"><span data-stu-id="e7a77-165">Clear the **Archiving** check box.</span></span>
    
     ![Screenshot della casella di controllo archiviazione nella finestra di dialogo Modifica proprietà.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="e7a77-167">Deselezionare la casella di controllo **monitoraggio** .</span><span class="sxs-lookup"><span data-stu-id="e7a77-167">Clear the **Monitoring** check box.</span></span>
    
     ![Screenshot della finestra di dialogo Modifica proprietà che mostra la casella di controllo monitoraggio.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="e7a77-169">Fare clic con il pulsante destro del mouse sul pool di Lync Server 2013, scegliere **Aggiorna a Skype for Business server 2015**e seguire la procedura.</span><span class="sxs-lookup"><span data-stu-id="e7a77-169">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Screenshot del menu di scelta rapida con l'opzione di aggiornamento per Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="e7a77-171">Creare un nuovo archivio SQL per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e7a77-171">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="e7a77-172">Selezionare le proprietà di \*\*\*\* > **modifica**del pool e dell'azione.</span><span class="sxs-lookup"><span data-stu-id="e7a77-172">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="e7a77-173">Selezionare la casella di controllo **archiviazione** .</span><span class="sxs-lookup"><span data-stu-id="e7a77-173">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="e7a77-174">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e7a77-174">Click **New**.</span></span>
    
     ![Screenshot della finestra di dialogo Modifica proprietà che mostra il pulsante nuovo nella sezione archiviazione.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="e7a77-176">Creare un nuovo archivio SQL per il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="e7a77-176">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="e7a77-177">Selezionare le proprietà di \*\*\*\* > **modifica**del pool e dell'azione.</span><span class="sxs-lookup"><span data-stu-id="e7a77-177">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="e7a77-178">Selezionare la casella di controllo **monitoraggio** .</span><span class="sxs-lookup"><span data-stu-id="e7a77-178">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="e7a77-179">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e7a77-179">Click **New**.</span></span>
    
     ![Screenshot della finestra di dialogo Modifica proprietà che mostra il pulsante nuovo nella sezione monitoraggio.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="e7a77-181">In Generatore di topologie fare clic su **azione** > **Pubblica topologia** o**topologia** > di **azione** > **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="e7a77-181">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="e7a77-182">Durante la pubblicazione, scegliere di installare il database nel nuovo archivio archiviazione e monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="e7a77-182">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="e7a77-183">Passaggio 3: attendere la replica</span><span class="sxs-lookup"><span data-stu-id="e7a77-183">Step 3: Wait for replication</span></span>

<span data-ttu-id="e7a77-184">Assegna un po' di tempo alla replica per pubblicare la topologia aggiornata in tutti i server dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="e7a77-184">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="e7a77-185">Passaggio 4: arrestare tutti i servizi in pool per l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="e7a77-185">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="e7a77-186">In ogni server che sta servendo il pool che si vuole aggiornare, eseguire il cmdlet seguente in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e7a77-186">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```
Disable-CsComputer -Scorch
```

<span data-ttu-id="e7a77-187">È consigliabile usare Disable-CsComputer perché potrebbe essere necessario riavviare il server durante il processo di aggiornamento sul posto.</span><span class="sxs-lookup"><span data-stu-id="e7a77-187">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="e7a77-188">Se si usa Stop-CsWindowsService, è possibile che alcuni servizi vengano riavviati automaticamente dopo un riavvio.</span><span class="sxs-lookup"><span data-stu-id="e7a77-188">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="e7a77-189">In questo modo l'aggiornamento sul posto potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="e7a77-189">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="e7a77-190">Passaggio 5: aggiornare i pool Front-end e i server pool non front-end</span><span class="sxs-lookup"><span data-stu-id="e7a77-190">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="e7a77-191">Prima di eseguire l'aggiornamento, installare tutti i nuovi prerequisiti necessari per Skype for Business Server 2015 che includono: > almeno 32GB di spazio disponibile prima di provare un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="e7a77-191">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="e7a77-192">Inoltre, assicurati che l'unità sia un'unità locale fissa, che non sia connessa tramite USB o FireWire, sia formattata con il file system NTFS, non sia compressa e non contenga un file di pagina. > versione di PowerShell 6.2.9200.0 o successive. > l'ultimo Lync Server 2013 Aggiornamento cumulativo installato. > SQL Server 2012 SP1 installato. > installato la Knowledge Base seguente (installato automaticamente se si usa Microsoft Update): > Windows Server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623)> windows Server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2-[KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="e7a77-192">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="e7a77-193">Usare l'aggiornamento sul posto in ogni server per aggiornare il pool Front-End, il pool di Edge, il Mediation Server e il pool di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e7a77-193">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="e7a77-194">In ogni server eseguire **Setup. exe** da **OCS_Volume\Setup\amd64** nel supporto di installazione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e7a77-194">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="e7a77-195">Accettare il contratto di licenza e seguire le istruzioni per l'aggiornamento sul posto.</span><span class="sxs-lookup"><span data-stu-id="e7a77-195">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="e7a77-196">Ripetere questi passaggi per ogni server nel pool Front-end e in ogni server del pool non front-end.</span><span class="sxs-lookup"><span data-stu-id="e7a77-196">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e7a77-197">Potrebbe essere richiesto di riavviare il server durante l'aggiornamento sul posto.</span><span class="sxs-lookup"><span data-stu-id="e7a77-197">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="e7a77-198">Va bene.</span><span class="sxs-lookup"><span data-stu-id="e7a77-198">That's ok.</span></span> <span data-ttu-id="e7a77-199">Dopo il riavvio, l'aggiornamento sul posto continuerà da dove è stato interrotto.</span><span class="sxs-lookup"><span data-stu-id="e7a77-199">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="e7a77-200">Quando l'aggiornamento sul posto viene completato correttamente, viene visualizzato il messaggio seguente.</span><span class="sxs-lookup"><span data-stu-id="e7a77-200">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![Screenshot che mostra l'aggiornamento sul posto completato correttamente.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="e7a77-202">Passaggio 6: riavviare i servizi in tutti i server aggiornati</span><span class="sxs-lookup"><span data-stu-id="e7a77-202">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="e7a77-203">Prima di riavviare i servizi, assicurati che%ProgramData%\WindowsFabric non sia presente in tutti i server front-end.</span><span class="sxs-lookup"><span data-stu-id="e7a77-203">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="e7a77-204">Se esiste, eliminarlo prima di avviare i servizi.</span><span class="sxs-lookup"><span data-stu-id="e7a77-204">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="e7a77-205">Dopo aver aggiornato tutti i server nel pool Front-End, riavviare i servizi usando il comando di PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="e7a77-205">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="e7a77-206">Se è già necessario riavviare il sistema in sospeso prima di iniziare a eseguire l'aggiornamento sul posto, l'aggiornamento sul posto non richiederà il riavvio alla fine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="e7a77-206">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation.</span></span> <span data-ttu-id="e7a77-207">In questo modo verranno generate alcune eccezioni di assembly rispetto al primo server front-end quando si tenta di avviare i servizi usando il cmdlet Start-CSPool.</span><span class="sxs-lookup"><span data-stu-id="e7a77-207">This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet.</span></span> <span data-ttu-id="e7a77-208">Per risolvere questi errori, riavviare tutti i server del pool ed eseguire di nuovo il cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e7a77-208">To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="e7a77-209">Nei server pool non front-end riavviare i servizi usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e7a77-209">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```
  Start-CsWindowsService
  ```

<span data-ttu-id="e7a77-210">Dopo aver fatto clic su **OK** nella pagina di aggiornamento sul posto, viene visualizzato il promemoria seguente per completare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="e7a77-210">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![Screenshot che mostra i passaggi successivi dopo il completamento dell'aggiornamento sul posto.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="e7a77-212">Passaggio 7: verificare il funzionamento delle funzionalità di Skype for business</span><span class="sxs-lookup"><span data-stu-id="e7a77-212">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="e7a77-213">Per verificare che l'aggiornamento sia stato eseguito correttamente, per il pool aggiornato, provare Skype for business per verificare che la funzionalità funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="e7a77-213">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="e7a77-214">Passaggio 8: aggiornare i pool secondari</span><span class="sxs-lookup"><span data-stu-id="e7a77-214">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="e7a77-215">Ripetere i passaggi descritti in questo argomento per aggiornare gli eventuali pool aggiuntivi presenti nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="e7a77-215">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="e7a77-216">Risolvere i problemi relativi all'aggiornamento sul posto</span><span class="sxs-lookup"><span data-stu-id="e7a77-216">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="e7a77-217">Se l'aggiornamento sul posto non riesce, è possibile che venga visualizzato un messaggio simile a quello dell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="e7a77-217">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![Schermata che mostra il mancato aggiornamento sul posto perché non è installato un aggiornamento cumulativo obbligatorio.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="e7a77-219">Esaminare il messaggio completo nella parte inferiore della pagina per facilitare la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="e7a77-219">Review the full message at the bottom of the page to help you troubleshoot the issue.</span></span> <span data-ttu-id="e7a77-220">Fare clic su **Visualizza registri** per ottenere maggiori dettagli.</span><span class="sxs-lookup"><span data-stu-id="e7a77-220">Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="e7a77-221">Se l'aggiornamento sul posto non riesce a **verificare la disponibilità dell'aggiornamento** o l' **installazione di prerequisiti mancanti**, verificare che il server disponga di tutti gli aggiornamenti più recenti di Windows Server, Lync Server e SQL Server e che tutti i software e i ruoli necessari siano installato.</span><span class="sxs-lookup"><span data-stu-id="e7a77-221">If the In-Place Upgrade fails on **Verifying upgrade readiness** or **Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="e7a77-222">Per un elenco delle informazioni necessarie, vedere [requisiti del server per Skype for Business server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [installare i prerequisiti per Skype for Business Server 2015](install/install-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="e7a77-222">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e7a77-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7a77-223">See also</span></span>

[<span data-ttu-id="e7a77-224">Pianificare l'aggiornamento a Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e7a77-224">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="e7a77-225">Requisiti server di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e7a77-225">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="e7a77-226">Installare prerequisiti per Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e7a77-226">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="e7a77-227">Installare Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e7a77-227">Install Skype for Business Server 2015</span></span>](install/install.md)
