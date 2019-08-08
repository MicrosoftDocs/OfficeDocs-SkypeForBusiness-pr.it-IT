---
title: Eseguire la migrazione dei gruppi di risposte
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dopo lo spostamento degli utenti nei pool di Skype for Business Server 2019, è possibile eseguire la migrazione dei gruppi di risposta. La migrazione dei gruppi di risposte include la copia di gruppi di agenti, code, flussi di lavoro, file audio e oggetti contatto del gruppo di risposte in spostamento dalla distribuzione legacy al pool di Skype for Business Server 2019. Dopo la migrazione dei gruppi di risposta legacy, le chiamate ai gruppi di risposta vengono gestite dall'applicazione Response Group nel pool di Skype for Business Server 2019. Le chiamate ai gruppi di risposte non vengono più gestite dal pool legacy.
ms.openlocfilehash: b8d49205f4f54ca7c00a9aed0b6ac176c11cd617
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238462"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="80733-106">Eseguire la migrazione dei gruppi di risposte</span><span class="sxs-lookup"><span data-stu-id="80733-106">Migrate response groups</span></span>

<span data-ttu-id="80733-107">Dopo lo spostamento degli utenti nei pool di Skype for Business Server 2019, è possibile eseguire la migrazione dei gruppi di risposta.</span><span class="sxs-lookup"><span data-stu-id="80733-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="80733-108">La migrazione dei gruppi di risposte include la copia di gruppi di agenti, code, flussi di lavoro, file audio e oggetti contatto del gruppo di risposte in spostamento dalla distribuzione legacy al pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="80733-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="80733-109">Dopo la migrazione dei gruppi di risposta legacy, le chiamate ai gruppi di risposta vengono gestite dall'applicazione Response Group nel pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="80733-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="80733-110">Le chiamate ai gruppi di risposte non vengono più gestite dal pool legacy.</span><span class="sxs-lookup"><span data-stu-id="80733-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="80733-111">Anche se è possibile eseguire la migrazione di gruppi di risposte prima di spostare tutti gli utenti nel pool di Skype for Business Server 2019, è consigliabile spostare prima tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="80733-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="80733-112">In particolare, gli utenti che sono agenti del gruppo di risposta non avranno la piena funzionalità delle nuove caratteristiche finché non verranno spostati nel pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="80733-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="80733-113">Prima di eseguire la migrazione dei Response Groups, è necessario avere implementato un pool di Skype for Business Server 2019 che include l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="80733-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="80733-114">L'applicazione Response Group viene installata e attivata per impostazione predefinita quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="80733-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="80733-115">Puoi verificare che l'applicazione Response Group sia installata eseguendo il cmdlet **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="80733-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="80733-116">È possibile creare nuovi gruppi di risposta di Skype for Business Server 2019 nel pool di Skype for Business Server 2019 prima di eseguire la migrazione dei gruppi di risposta legacy.</span><span class="sxs-lookup"><span data-stu-id="80733-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="80733-117">Per eseguire la migrazione dei gruppi di risposte da un pool legacy a Skype for Business Server 2019, Esegui il cmdlet **Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="80733-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="80733-118">Il cmdlet di migrazione del gruppo di risposte sposta la configurazione del gruppo di risposte per l'intero pool.</span><span class="sxs-lookup"><span data-stu-id="80733-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="80733-119">Non è possibile selezionare gruppi, code o flussi di lavoro specifici per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="80733-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="80733-120">Dopo la migrazione dei Response Groups, è necessario usare il pannello di controllo di Skype for Business Server o i cmdlet di Skype for Business Server Management Shell per verificare che tutti i gruppi di agenti, le code e i flussi di lavoro vengano spostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="80733-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="80733-121">Quando si esegue la migrazione dei gruppi di risposte, i gruppi di risposta legacy non vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="80733-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="80733-122">Quando si gestiscono i gruppi di risposta dopo la migrazione usando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell, è possibile vedere sia i gruppi di risposta legacy che i gruppi di risposta di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="80733-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="80733-123">Dovresti applicare gli aggiornamenti solo ai gruppi di risposta di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="80733-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="80733-124">I gruppi di risposte legacy vengono conservati solo per scopi di rollback.</span><span class="sxs-lookup"><span data-stu-id="80733-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="80733-125">Dopo aver completato la migrazione e creato i nuovi gruppi di risposta, il pannello di controllo di Skype for Business Server e Skype for Business Server Management Shell visualizzeranno le versioni legacy e Skype for Business Server 2019 di ogni risposta gruppo.</span><span class="sxs-lookup"><span data-stu-id="80733-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="80733-126">Non usare il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell per rimuovere i gruppi di risposta legacy.</span><span class="sxs-lookup"><span data-stu-id="80733-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="80733-127">Se si rimuove uno, il gruppo di risposte corrispondente creato durante la migrazione smetterà di funzionare.</span><span class="sxs-lookup"><span data-stu-id="80733-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="80733-128">I gruppi di risposte legacy verranno rimossi quando si rimuove la Commissione del pool legacy.</span><span class="sxs-lookup"><span data-stu-id="80733-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="80733-129">È consigliabile non rimuovere i dati dalla distribuzione precedente fino a quando non si esegue la disattivazione del pool.</span><span class="sxs-lookup"><span data-stu-id="80733-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="80733-130">Inoltre, ti consigliamo vivamente di esportare i Response Group subito dopo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="80733-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="80733-131">Se un gruppo di risposte legacy deve essere rimosso, è possibile ripristinare i gruppi di risposte dal backup per ottenere di nuovo i gruppi di risposte di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="80733-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="80733-132">Skype for Business Server 2019 introduce una nuova funzionalità di Response Group denominata **tipo di flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="80733-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="80733-133">Il **tipo di flusso di lavoro** può essere **gestito** o **non gestito**.</span><span class="sxs-lookup"><span data-stu-id="80733-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="80733-134">Tutti i gruppi di risposte vengono migrati con il **tipo di flusso di lavoro** impostato su **non gestito** e con un elenco di gestione vuoto.</span><span class="sxs-lookup"><span data-stu-id="80733-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="80733-135">Quando si esegue il cmdlet **Move-CsRgsConfiguration** , i gruppi di agenti, le code, i flussi di lavoro e i file audio rimangono nel pool legacy per scopi di rollback.</span><span class="sxs-lookup"><span data-stu-id="80733-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="80733-136">Se si ha bisogno di eseguire il rollback al pool legacy, deve comunque essere eseguito il cmdlet **Move-CsApplicationEndpoint** per riportare gli oggetti di contatto nel pool legacy.</span><span class="sxs-lookup"><span data-stu-id="80733-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="80733-137">La procedura seguente per la migrazione delle configurazioni di Response Group presuppone che si disponga di una relazione uno-a-uno tra i pool legacy e i pool di 2019 di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="80733-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="80733-138">Se si prevede di consolidare o suddividere i pool durante la migrazione e la distribuzione, è necessario pianificare le mappe del pool legacy a cui è associato il pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="80733-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="80733-139">Per eseguire la migrazione delle configurazioni di Response Group</span><span class="sxs-lookup"><span data-stu-id="80733-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="80733-140">Accedere al computer con un account che sia membro del gruppo RTCUniversalServerAdmins o disponga di diritti di amministratore e autorizzazioni equivalenti.</span><span class="sxs-lookup"><span data-stu-id="80733-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="80733-141">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="80733-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="80733-142">Eseguire</span><span class="sxs-lookup"><span data-stu-id="80733-142">Run:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="80733-143">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="80733-143">For example:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="80733-144">Dopo la migrazione di gruppi di risposte e agenti al pool di Skype for Business Server 2019, l'URL usato dagli agenti per accedere e disconnettersi è un URL di Skype for Business Server 2019 ed è disponibile nel menu **strumenti** .</span><span class="sxs-lookup"><span data-stu-id="80733-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="80733-145">Ricorda agli agenti di aggiornare tutti i riferimenti, ad esempio i segnalibri, al nuovo URL.</span><span class="sxs-lookup"><span data-stu-id="80733-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="80733-146">Per verificare la migrazione di Response Group tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="80733-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="80733-147">Accedere al computer con un account che è un membro del gruppo RTCUniversalReadOnlyAdmins o è minimamente un membro del ruolo CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="80733-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="80733-148">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="80733-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="80733-149">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Skype for Business Server, vedere [aprire gli strumenti di amministrazione di Skype for Business server 2019](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span><span class="sxs-lookup"><span data-stu-id="80733-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="80733-150">Nel riquadro di spostamento sinistro fare clic su **Response Groups**.</span><span class="sxs-lookup"><span data-stu-id="80733-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="80733-151">Nella scheda **flusso di lavoro** verificare che tutti i flussi di lavoro nell'ambiente legacy siano inclusi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="80733-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="80733-152">Fare clic sulla scheda **coda** e verificare che tutte le code nell'ambiente legacy siano incluse nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="80733-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="80733-153">Fare clic sulla scheda **gruppo** e verificare che tutti i gruppi di agenti nell'ambiente legacy siano inclusi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="80733-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="80733-154">Per verificare la migrazione dei gruppi di risposte tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="80733-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="80733-155">Accedere al computer con un account che è un membro del gruppo RTCUniversalReadOnlyAdmins o è minimamente un membro del ruolo CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="80733-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="80733-156">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="80733-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="80733-157">Per informazioni dettagliate sui cmdlet seguenti, eseguire:</span><span class="sxs-lookup"><span data-stu-id="80733-157">For details about the following cmdlets, run:</span></span>
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="80733-158">Eseguire</span><span class="sxs-lookup"><span data-stu-id="80733-158">Run:</span></span>
    
   ```
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="80733-159">Verificare che tutti i gruppi di agenti nell'ambiente legacy siano inclusi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="80733-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="80733-160">Eseguire</span><span class="sxs-lookup"><span data-stu-id="80733-160">Run:</span></span>
    
   ```
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="80733-161">Verificare che tutte le code nell'ambiente legacy siano incluse nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="80733-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="80733-162">Eseguire</span><span class="sxs-lookup"><span data-stu-id="80733-162">Run:</span></span>
    
   ```
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="80733-163">Verificare che tutti i flussi di lavoro nell'ambiente legacy siano inclusi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="80733-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

