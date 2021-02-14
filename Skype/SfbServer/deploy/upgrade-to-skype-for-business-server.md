---
title: Eseguire l'aggiornamento a Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: "Riepilogo: informazioni su come eseguire l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015. Scaricare una versione di valutazione gratuita di Skype for Business Server 2015 dal Centro di valutazione Microsoft all'indirizzo: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ."
ms.openlocfilehash: cda83d03db697a0adf404af4f6fe6e350abf6b58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820426"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="25efa-104">Eseguire l'aggiornamento a Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="25efa-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="25efa-105">**Riepilogo:** Informazioni su come eseguire l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="25efa-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="25efa-106">Scaricare una versione di valutazione gratuita di Skype for Business Server 2015 dal [Centro di valutazione Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="25efa-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="25efa-107">Utilizzare le procedure descritte in questo documento per eseguire l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015 utilizzando Generatore di topologie di Skype for Business Server e la nuova funzionalità di aggiornamento In-Place.</span><span class="sxs-lookup"><span data-stu-id="25efa-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="25efa-108">Se si desidera eseguire l'aggiornamento da Lync Server 2010 o Office Communications Server 2007 R2, vedere Pianificare l'aggiornamento a [Skype for Business Server 2015.](../plan-your-deployment/upgrade.md)</span><span class="sxs-lookup"><span data-stu-id="25efa-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>

> [!NOTE]
> <span data-ttu-id="25efa-109">Gli aggiornamenti sul posto erano disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="25efa-109">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="25efa-110">La coesistenza affiancata è supportata, vedere [Migrazione a Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="25efa-110">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="25efa-111">Aggiornamento da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25efa-111">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="25efa-112">L'aggiornamento di Lync Server 2013 a Skype for Business Server 2015 implica l'installazione di software prerequisito, l'utilizzo di Generatore di topologie di Skype for Business Server per aggiornare i database nel pool e l'aggiornamento di Skype for Business Server In-Place in ognuno dei server associati al pool.</span><span class="sxs-lookup"><span data-stu-id="25efa-112">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="25efa-113">Per completare l'aggiornamento, eseguire gli otto passaggi descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="25efa-113">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="25efa-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="25efa-114">Before you begin</span></span>

- <span data-ttu-id="25efa-115">Rivedere [Il piano per l'aggiornamento a Skype for Business Server 2015.](../plan-your-deployment/upgrade.md)</span><span class="sxs-lookup"><span data-stu-id="25efa-115">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="25efa-116">Esaminare [i requisiti del server per Skype for Business Server 2015.](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="25efa-116">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="25efa-117">[Installare i prerequisiti per Skype for Business Server 2015.](install/install-prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="25efa-117">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="25efa-118">[Installare Skype for Business Server 2015.](install/install.md)</span><span class="sxs-lookup"><span data-stu-id="25efa-118">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="25efa-119">Passaggio 1: Installare gli strumenti di amministrazione e scaricare la topologia</span><span class="sxs-lookup"><span data-stu-id="25efa-119">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="25efa-120">Connettersi al computer nella topologia in cui non è installato Lync OCSCore o altri componenti lync.</span><span class="sxs-lookup"><span data-stu-id="25efa-120">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="25efa-121">Dal supporto di installazione di Skype for Business Server 2015, **eseguire** Setup.exeda **OCS_Volume\Setup\AMD64.**</span><span class="sxs-lookup"><span data-stu-id="25efa-121">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="25efa-122">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="25efa-122">Click **Install**.</span></span> 
    
4. <span data-ttu-id="25efa-123">Accettare il contratto di licenza.</span><span class="sxs-lookup"><span data-stu-id="25efa-123">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="25efa-124">Nella Distribuzione guidata fare clic **su Installa strumenti di amministrazione** e seguire i passaggi per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="25efa-124">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![Screenshot of Deployment Wizard with link to the Install Administrator Tools called out.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="25efa-126">Dalla schermata Start di Windows, aprire Generatore di topologie di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="25efa-126">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="25efa-127">Fare **clic su Scarica topologia dalla distribuzione esistente** e quindi su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="25efa-127">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="25efa-128">Immettere un nome per la topologia e fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="25efa-128">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="25efa-129">Passare al percorso in cui è stata salvata la topologia ed eseguire una copia della topologia.</span><span class="sxs-lookup"><span data-stu-id="25efa-129">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="25efa-130">Passaggio 2: Aggiornare e pubblicare la topologia tramite Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="25efa-130">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="25efa-131">Prima di avviare il processo di aggiornamento, tutti i servizi devono essere in esecuzione per i pool che si intende aggiornare.</span><span class="sxs-lookup"><span data-stu-id="25efa-131">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="25efa-132">In questo modo le modifiche apportate alla topologia verranno replicate nel database locale dei server del pool.</span><span class="sxs-lookup"><span data-stu-id="25efa-132">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="25efa-133">Salvare una copia del file della topologia prima di eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="25efa-133">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="25efa-134">Dopo l'aggiornamento, non sarà possibile eseguire il downgrade della topologia.> Se i servizi si trovano sugli stessi server dei database, ad esempio il servizio Chat persistente si trova nello stesso server del database di Persistent Chat, ignorare questo passaggio e andare al passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="25efa-134">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="25efa-135">Dopo aver arrestare i servizi, eseguire il In-Place aggiornare il programma di installazione in ogni server per aggiornare i database locali.</span><span class="sxs-lookup"><span data-stu-id="25efa-135">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="25efa-136">Se nella topologia è disponibile un database back-end con mirroring, quando si pubblica  la topologia tramite Generatore di topologie verranno visualizzati sia i database principali che i database con mirroring.</span><span class="sxs-lookup"><span data-stu-id="25efa-136">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder.</span></span> <span data-ttu-id="25efa-137">Verificare che tutti i database siano in esecuzione nell'entità e selezionare solo l'entità, non il mirror, quando si pubblica la topologia, altrimenti verrà visualizzato un avviso dopo la pubblicazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="25efa-137">Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="25efa-138">Selezionare una delle opzioni seguenti per aggiornare e pubblicare una nuova topologia utilizzando Generatore di topologie di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="25efa-138">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="25efa-139">Dopo aver completato i passaggi e pubblicato la topologia aggiornata, andare al passaggio 3 di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="25efa-139">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="25efa-140">Opzione 1: aggiornare un pool Front End isolato e gli archivi di archiviazione e monitoraggio associati</span><span class="sxs-lookup"><span data-stu-id="25efa-140">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="25efa-141">Se il pool che si sta aggiornando ha una dipendenza dell'archivio di archiviazione e monitoraggio, quando si utilizza la procedura seguente, verrà aggiornato anche l'archivio di archiviazione e monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="25efa-141">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="25efa-142">In Generatore di topologie fare clic con il pulsante destro del mouse su un pool di Lync Server 2013, selezionare Aggiorna a **Skype for Business Server 2015** e seguire la procedura.</span><span class="sxs-lookup"><span data-stu-id="25efa-142">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Screenshot del menu di scelta rapida con l'opzione di aggiornamento per Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="25efa-144">In Generatore di topologie fare **clic** su Pubblica  >  **azione o**   >  **Pubblica topologia**  >  **azioni.**</span><span class="sxs-lookup"><span data-stu-id="25efa-144">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![Screenshot del menu Azione con l'opzione Pubblica topologia in Generatore di topologie.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="25efa-146">Durante la pubblicazione scegliere di installare un database nell'archivio di archiviazione e monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="25efa-146">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="25efa-147">Opzione 2: aggiornare il pool Front End senza aggiornare gli archivi di archiviazione e monitoraggio</span><span class="sxs-lookup"><span data-stu-id="25efa-147">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="25efa-148">Se si utilizza la procedura seguente, l'archiviazione e il monitoraggio per il pool selezionato vengono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="25efa-148">If you use the following steps, archiving and monitoring for the selected pool are disabled.</span></span> <span data-ttu-id="25efa-149">Il pool non dirà archivi di archiviazione e monitoraggio dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="25efa-149">The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="25efa-150">In Generatore di topologie selezionare il pool di Lync Server 2013 che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="25efa-150">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="25efa-151">Rimuovere la dipendenza per gli archivi di archiviazione e monitoraggio di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25efa-151">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="25efa-152">Passare ad **Azione**  >  **Modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="25efa-152">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="25efa-153">Deselezionare la **casella di** controllo Archiviazione.</span><span class="sxs-lookup"><span data-stu-id="25efa-153">Clear the **Archiving** check box.</span></span>
    
     ![Screenshot della casella di controllo Archiviazione nella finestra di dialogo Modifica proprietà.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="25efa-155">Deselezionare **la casella di** controllo Monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="25efa-155">Clear the **Monitoring** check box.</span></span>
    
     ![Screenshot della finestra di dialogo Modifica proprietà che mostra la casella di controllo Monitoraggio.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="25efa-157">Fare clic con il pulsante destro del mouse sul pool di Lync Server 2013, selezionare Aggiorna a **Skype for Business Server 2015** e seguire la procedura.</span><span class="sxs-lookup"><span data-stu-id="25efa-157">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Screenshot del menu di scelta rapida con l'opzione di aggiornamento per Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="25efa-159">In Generatore di topologie fare **clic** su Pubblica  >  **azione o**   >  **Pubblica topologia**  >  **azioni.**</span><span class="sxs-lookup"><span data-stu-id="25efa-159">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="25efa-160">Opzione 3: aggiornare il pool Front End e associarlo ai nuovi archivi di archiviazione e monitoraggio di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="25efa-160">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="25efa-161">Se si utilizza la procedura seguente, l'archiviazione e il monitoraggio si interromperanno nell'archivio precedente e inizieranno nel nuovo archivio creato.</span><span class="sxs-lookup"><span data-stu-id="25efa-161">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="25efa-162">In Generatore di topologie selezionare il pool di Lync Server 2013 che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="25efa-162">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="25efa-163">Rimuovere la dipendenza per gli archivi di archiviazione e monitoraggio di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25efa-163">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="25efa-164">Passare ad **Azione**  >  **Modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="25efa-164">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="25efa-165">Deselezionare la **casella di** controllo Archiviazione.</span><span class="sxs-lookup"><span data-stu-id="25efa-165">Clear the **Archiving** check box.</span></span>
    
     ![Screenshot della casella di controllo Archiviazione nella finestra di dialogo Modifica proprietà.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="25efa-167">Deselezionare **la casella di** controllo Monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="25efa-167">Clear the **Monitoring** check box.</span></span>
    
     ![Screenshot della finestra di dialogo Modifica proprietà che mostra la casella di controllo Monitoraggio.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="25efa-169">Fare clic con il pulsante destro del mouse sul pool di Lync Server 2013, selezionare Aggiorna a **Skype for Business Server 2015** e seguire la procedura.</span><span class="sxs-lookup"><span data-stu-id="25efa-169">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Screenshot del menu di scelta rapida con l'opzione di aggiornamento per Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="25efa-171">Creare un nuovo archivio SQL per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="25efa-171">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="25efa-172">Selezionare le proprietà pool **e**  >  **Modifica azione.**</span><span class="sxs-lookup"><span data-stu-id="25efa-172">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="25efa-173">Selezionare la **casella di controllo** Archiviazione.</span><span class="sxs-lookup"><span data-stu-id="25efa-173">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="25efa-174">Fare clic su **Nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="25efa-174">Click **New**.</span></span>
    
     ![Screenshot della finestra di dialogo Modifica proprietà che mostra il pulsante Nuovo nella sezione Archiviazione.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="25efa-176">Creare un nuovo SQL per il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="25efa-176">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="25efa-177">Selezionare le proprietà pool **e**  >  **Modifica azione.**</span><span class="sxs-lookup"><span data-stu-id="25efa-177">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="25efa-178">Selezionare la **casella di** controllo Monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="25efa-178">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="25efa-179">Fare clic su **Nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="25efa-179">Click **New**.</span></span>
    
     ![Screenshot della finestra di dialogo Modifica proprietà che mostra il pulsante Nuovo nella sezione Monitoraggio.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="25efa-181">In Generatore di topologie fare **clic** su Pubblica  >  **azione o**   >  **Pubblica topologia**  >  **azioni.**</span><span class="sxs-lookup"><span data-stu-id="25efa-181">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="25efa-182">Durante la pubblicazione scegliere di installare il database nel nuovo archivio di archiviazione e monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="25efa-182">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="25efa-183">Passaggio 3: attendere la replica</span><span class="sxs-lookup"><span data-stu-id="25efa-183">Step 3: Wait for replication</span></span>

<span data-ttu-id="25efa-184">Concedere alla replica il tempo necessario per pubblicare la topologia aggiornata in tutti i server dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="25efa-184">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="25efa-185">Passaggio 4: Arrestare tutti i servizi nel pool per l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="25efa-185">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="25efa-186">In ogni server che si sta servindo del pool che si desidera aggiornare, eseguire il cmdlet seguente in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="25efa-186">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```powershell
Disable-CsComputer -Scorch
```

<span data-ttu-id="25efa-187">È consigliabile utilizzare Disable-CsComputer perché potrebbe essere necessario riavviare il server durante il In-Place di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="25efa-187">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="25efa-188">Se si utilizza Stop-CsWindowsService, alcuni servizi potrebbero riavviarsi automaticamente dopo un riavvio.</span><span class="sxs-lookup"><span data-stu-id="25efa-188">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="25efa-189">Ciò potrebbe causare la mancata In-Place'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="25efa-189">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="25efa-190">Passaggio 5: Aggiornare pool Front End e server di pool non Front End</span><span class="sxs-lookup"><span data-stu-id="25efa-190">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="25efa-191">Prima di eseguire l'aggiornamento, installare tutti i nuovi prerequisiti necessari per Skype for Business Server 2015 che includono: > Almeno 32 GB di spazio libero prima di tentare un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="25efa-191">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="25efa-192">Inoltre, assicurati che l'unità sia un'unità locale fissa, che non sia collegata tramite USB o Firewire, è formattato con il file system NTFS, non è compresso e non contiene un file di pagina.> PowerShell versione 6.2.92 00.0 o versione successiva.> È stato installato l'aggiornamento cumulativo di Lync Server 2013 più recente.> SQL Server 2012 SP1.> La kb seguente è installata (installata automaticamente se si utilizza Microsoft Update):> Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="25efa-192">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="25efa-193">Utilizzare la In-Place in ogni server per aggiornare il pool Front End, il pool di server perimetrali, il Mediation Server e il pool di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="25efa-193">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="25efa-194">In ogni server, **eseguireSetup.exe** da **OCS_Volume\Setup\amd64** sul supporto di installazione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="25efa-194">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="25efa-195">Accettare il contratto di licenza e seguire le istruzioni per l'In-Place aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="25efa-195">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="25efa-196">Ripetere questi passaggi per ogni server nel pool Front End e in ogni server del pool non Front End.</span><span class="sxs-lookup"><span data-stu-id="25efa-196">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="25efa-197">Potrebbe essere richiesto di riavviare il server durante l'In-Place aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="25efa-197">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="25efa-198">Va bene.</span><span class="sxs-lookup"><span data-stu-id="25efa-198">That's ok.</span></span> <span data-ttu-id="25efa-199">Dopo il riavvio, lIn-Place di aggiornamento continuerà dal punto in cui è stato lasciato.</span><span class="sxs-lookup"><span data-stu-id="25efa-199">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="25efa-200">Al termine In-Place'aggiornamento, viene visualizzato il messaggio seguente.</span><span class="sxs-lookup"><span data-stu-id="25efa-200">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![Screenshot che mostra che l'aggiornamento sul posto è stato completato correttamente.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="25efa-202">Passaggio 6: Riavviare i servizi in tutti i server aggiornati</span><span class="sxs-lookup"><span data-stu-id="25efa-202">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="25efa-203">Prima di riavviare i servizi, assicurarsi che %ProgramData%\WindowsFabric non esista in tutti i Front End Server.</span><span class="sxs-lookup"><span data-stu-id="25efa-203">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="25efa-204">Se esiste, eliminarlo prima di avviare i servizi.</span><span class="sxs-lookup"><span data-stu-id="25efa-204">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="25efa-205">Dopo aver aggiornato tutti i server nel pool Front End, riavviare i servizi utilizzando il comando PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="25efa-205">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="25efa-206">Se è già necessario un riavvio del sistema in sospeso prima di avviare l'esecuzione di In-Place Upgrade, In-Place Upgrade non chiederà di riavviare il sistema al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="25efa-206">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation.</span></span> <span data-ttu-id="25efa-207">Ciò causerà la generazione di alcune eccezioni di assembly nel primo Front End Server quando si tenta di avviare i servizi utilizzando il cmdlet Start-CSPool.</span><span class="sxs-lookup"><span data-stu-id="25efa-207">This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet.</span></span> <span data-ttu-id="25efa-208">Per risolvere questi errori, riavviare tutti i server del pool ed eseguire di nuovo il cmdlet.</span><span class="sxs-lookup"><span data-stu-id="25efa-208">To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="25efa-209">Nei server del pool non Front End riavviare i servizi utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="25efa-209">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```powershell
  Start-CsWindowsService
  ```

<span data-ttu-id="25efa-210">Dopo aver fatto **clic su OK** nella In-Place aggiorna, verrà visualizzato il promemoria seguente per completare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="25efa-210">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![Screenshot che mostra i passaggi successivi dopo il completamento dell'aggiornamento sul posto.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="25efa-212">Passaggio 7: Verificare il funzionamento delle funzionalità di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="25efa-212">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="25efa-213">Per assicurarsi che l'aggiornamento sia stato eseguito correttamente, per il pool aggiornato, testare Skype for Business per verificare che la funzionalità funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="25efa-213">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="25efa-214">Passaggio 8: aggiornare i pool secondari</span><span class="sxs-lookup"><span data-stu-id="25efa-214">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="25efa-215">Ripetere i passaggi descritti in questo argomento per aggiornare eventuali pool aggiuntivi presenti nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="25efa-215">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="25efa-216">Risolvere i problemi relativi all'In-Place aggiornamento</span><span class="sxs-lookup"><span data-stu-id="25efa-216">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="25efa-217">Se lIn-Place non riesce, potrebbe essere visualizzato un messaggio simile a quello riportato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="25efa-217">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![Screenshot che mostra un errore di aggiornamento sul posto perché non è installato un aggiornamento cumulativo necessario.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="25efa-219">Esaminare il messaggio completo nella parte inferiore della pagina per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="25efa-219">Review the full message at the bottom of the page to help you troubleshoot the issue.</span></span> <span data-ttu-id="25efa-220">Fare **clic su Visualizza registri** per ottenere maggiori dettagli.</span><span class="sxs-lookup"><span data-stu-id="25efa-220">Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="25efa-221">Se l'aggiornamento di In-Place  non riesce durante la verifica della preparazione dell'aggiornamento o l'installazione dei prerequisiti **mancanti,** verificare che nel server siano applicati tutti gli aggiornamenti più recenti di Windows Server, Lync Server e SQL Server e che siano installati tutti i ruoli e il software necessari.</span><span class="sxs-lookup"><span data-stu-id="25efa-221">If the In-Place Upgrade fails on **Verifying upgrade readiness** or **Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="25efa-222">Per un elenco degli elementi necessari, vedere Requisiti server per [Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e Installare i prerequisiti per Skype for Business Server [2015.](install/install-prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="25efa-222">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="25efa-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25efa-223">See also</span></span>

[<span data-ttu-id="25efa-224">Pianificare l'aggiornamento a Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="25efa-224">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="25efa-225">Requisiti del server per Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="25efa-225">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="25efa-226">Installare i prerequisiti per Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="25efa-226">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="25efa-227">Installare Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="25efa-227">Install Skype for Business Server 2015</span></span>](install/install.md)
