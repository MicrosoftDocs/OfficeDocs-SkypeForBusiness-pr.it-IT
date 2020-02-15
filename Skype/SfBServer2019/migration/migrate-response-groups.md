---
title: Eseguire la migrazione di Response Group
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dopo lo spostamento degli utenti nei pool di Skype for Business Server 2019, è possibile eseguire la migrazione dei Response Group. La migrazione dei Response Group include i gruppi di agenti di copia, le code, i flussi di lavoro, i file audio e gli oggetti contatto del gruppo di risposta in movimento dalla distribuzione legacy al pool di Skype for Business Server 2019. Dopo aver eseguito la migrazione dei gruppi di risposta legacy, le chiamate ai Response Group vengono gestite dall'applicazione Response gruppo nel pool Skype for Business Server 2019. Le chiamate ai Response Group non sono più gestite dal pool legacy.
ms.openlocfilehash: 2d439462fa103cc16fd7ae70b79364be7d79803a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42016107"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="c702c-106">Eseguire la migrazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="c702c-106">Migrate response groups</span></span>

<span data-ttu-id="c702c-107">Dopo lo spostamento degli utenti nei pool di Skype for Business Server 2019, è possibile eseguire la migrazione dei Response Group.</span><span class="sxs-lookup"><span data-stu-id="c702c-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="c702c-108">La migrazione dei Response Group include i gruppi di agenti di copia, le code, i flussi di lavoro, i file audio e gli oggetti contatto del gruppo di risposta in movimento dalla distribuzione legacy al pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c702c-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="c702c-109">Dopo aver eseguito la migrazione dei gruppi di risposta legacy, le chiamate ai Response Group vengono gestite dall'applicazione Response gruppo nel pool Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c702c-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="c702c-110">Le chiamate ai Response Group non sono più gestite dal pool legacy.</span><span class="sxs-lookup"><span data-stu-id="c702c-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c702c-111">Anche se è possibile eseguire la migrazione dei Response Group prima di spostare tutti gli utenti nel pool di Skype for Business Server 2019, è consigliabile spostare innanzitutto tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c702c-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="c702c-112">In particolare, gli utenti che sono agenti di Response Group non disporranno di funzionalità complete di nuove funzionalità finché non verranno spostati nel pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c702c-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="c702c-113">Prima di eseguire la migrazione dei Response Group, è necessario che sia stato distribuito un pool Skype for Business Server 2019 che includa l'applicazione Response gruppo.</span><span class="sxs-lookup"><span data-stu-id="c702c-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="c702c-114">L'applicazione Response Group viene installata e attivata per impostazione predefinita quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c702c-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="c702c-115">È possibile verificare che l'applicazione Response Group sia installata eseguendo il cmdlet **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="c702c-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c702c-116">È possibile creare nuovi Response Group di Skype for Business Server 2019 nel pool Skype for Business Server 2019 prima di eseguire la migrazione dei Response Group Legacy.</span><span class="sxs-lookup"><span data-stu-id="c702c-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="c702c-117">Per eseguire la migrazione dei Response Group da un pool legacy a Skype for Business Server 2019, si esegue il cmdlet **Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="c702c-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c702c-118">Il cmdlet Response Group Migration sposta la configurazione del Response Group per l'intero pool.</span><span class="sxs-lookup"><span data-stu-id="c702c-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="c702c-119">Non è possibile selezionare gruppi, code o flussi di lavoro specifici di cui eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="c702c-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="c702c-120">Dopo aver eseguito la migrazione dei Response Group, è necessario utilizzare il pannello di controllo di Skype for Business Server o i cmdlet di Skype for Business Server Management Shell per verificare che tutti i gruppi di agenti, le code e i flussi di lavoro siano stati spostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="c702c-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="c702c-121">Quando si esegue la migrazione dei Response Group, i Response Group Legacy non vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="c702c-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="c702c-122">Quando si gestiscono i Response Group dopo la migrazione usando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell, è possibile visualizzare sia i Response Group Legacy che i Response Group di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c702c-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="c702c-123">È consigliabile applicare gli aggiornamenti solo ai Response Group di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c702c-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="c702c-124">I Response Group Legacy vengono mantenuti solo per scopi di rollback.</span><span class="sxs-lookup"><span data-stu-id="c702c-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="c702c-125">Dopo che la migrazione è stata completata e i nuovi Response Group sono stati creati, il pannello di controllo di Skype for Business Server e Skype for Business Server Management Shell visualizzeranno le versioni legacy e Skype for Business Server 2019 di ogni risposta gruppo.</span><span class="sxs-lookup"><span data-stu-id="c702c-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="c702c-126">Non utilizzare il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell per rimuovere i Response Group Legacy.</span><span class="sxs-lookup"><span data-stu-id="c702c-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="c702c-127">Se si rimuove uno, il Response Group corrispondente che è stato creato durante la migrazione smetterà di funzionare.</span><span class="sxs-lookup"><span data-stu-id="c702c-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="c702c-128">I Response Group Legacy verranno rimossi quando si rimuove la Commissione del pool legacy.</span><span class="sxs-lookup"><span data-stu-id="c702c-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c702c-129">È consigliabile rimuovere i dati dalla distribuzione precedente solo dopo la rimozione del pool.</span><span class="sxs-lookup"><span data-stu-id="c702c-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="c702c-130">È inoltre consigliabile esportare i Response Group subito dopo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="c702c-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="c702c-131">Se un Response Group Legacy deve essere rimosso, è possibile ripristinare i Response Group dal backup per ottenere i Response Group di Skype for Business Server 2019 in esecuzione di nuovo.</span><span class="sxs-lookup"><span data-stu-id="c702c-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="c702c-132">Skype for Business Server 2019 introduce una nuova funzionalità Response Group denominata **tipo di flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="c702c-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="c702c-133">Il **Tipo di flusso di lavoro** può essere **Gestito** o **Non gestito**.</span><span class="sxs-lookup"><span data-stu-id="c702c-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="c702c-134">Tutti i Response Group vengono migrati con il **Tipo di flusso di lavoro** impostato su **Non gestito** e con un elenco di responsabili vuoto.</span><span class="sxs-lookup"><span data-stu-id="c702c-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="c702c-135">Quando si esegue il cmdlet **Move-CsRgsConfiguration**, i gruppi di agenti, le code, i flussi di lavoro e i file audio rimangono nel pool legacy per consentirne il ripristino.</span><span class="sxs-lookup"><span data-stu-id="c702c-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="c702c-136">Se occorre eseguire il rollback dello stato precedente nel pool legacy, tuttavia, è necessario eseguire il cmdlet **Move-CsApplicationEndpoint** per rispostare gli oggetti contatto nel pool legacy.</span><span class="sxs-lookup"><span data-stu-id="c702c-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="c702c-137">La procedura seguente per eseguire la migrazione delle configurazioni di Response Group presuppone che si disponga di una relazione uno-a-uno tra i pool legacy e i pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c702c-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="c702c-138">Se si prevede di consolidare o dividere i pool durante la migrazione e la distribuzione, è necessario pianificare il pool legacy in cui si esegue il pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c702c-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="c702c-139">Per eseguire la migrazione delle configurazioni di Response Group</span><span class="sxs-lookup"><span data-stu-id="c702c-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="c702c-140">Accedere al computer con un account membro del gruppo RTCUniversalServerAdmins o con le autorizzazioni e i diritti di amministratore equivalenti.</span><span class="sxs-lookup"><span data-stu-id="c702c-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="c702c-141">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c702c-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c702c-142">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="c702c-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="c702c-143">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c702c-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="c702c-144">Dopo aver eseguito la migrazione di Response Group e agenti al pool di Skype for Business Server 2019, l'URL utilizzato dagli agenti per accedere e disconnettersi è un URL di Skype for Business Server 2019 ed è disponibile dal menu **strumenti** .</span><span class="sxs-lookup"><span data-stu-id="c702c-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="c702c-145">Ricordare agli agenti di aggiornare eventuali riferimenti, come segnalibri, al nuovo URL.</span><span class="sxs-lookup"><span data-stu-id="c702c-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c702c-146">Per verificare la migrazione di Response Group tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c702c-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c702c-147">Eseguire l'accesso al computer con un account membro del gruppo RTCUniversalReadOnlyAdmins o come minimo membro del ruolo CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c702c-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="c702c-148">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c702c-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="c702c-149">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Skype for Business Server, vedere [aprire gli strumenti di amministrazione di Skype for Business server 2019](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx).</span><span class="sxs-lookup"><span data-stu-id="c702c-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="c702c-150">Nel riquadro di spostamento sinistro fare clic su **Response Group**.</span><span class="sxs-lookup"><span data-stu-id="c702c-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="c702c-151">Nella scheda **flusso di lavoro** verificare che nell'elenco siano inclusi tutti i flussi di lavoro dell'ambiente legacy.</span><span class="sxs-lookup"><span data-stu-id="c702c-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="c702c-152">Fare clic sulla scheda **coda** e verificare che nell'elenco siano incluse tutte le code dell'ambiente legacy.</span><span class="sxs-lookup"><span data-stu-id="c702c-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="c702c-153">Fare clic sulla scheda **gruppo** e verificare che nell'elenco siano inclusi tutti i gruppi di agenti dell'ambiente legacy.</span><span class="sxs-lookup"><span data-stu-id="c702c-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c702c-154">Per verificare la migrazione di Response Group tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="c702c-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="c702c-155">Eseguire l'accesso al computer con un account membro del gruppo RTCUniversalReadOnlyAdmins o come minimo membro del ruolo CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c702c-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="c702c-156">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c702c-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="c702c-157">Per informazioni dettagliate sui cmdlet seguenti, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c702c-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="c702c-158">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="c702c-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="c702c-159">Verificare che nell'elenco siano inclusi tutti i gruppi di agenti nell'ambiente legacy.</span><span class="sxs-lookup"><span data-stu-id="c702c-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="c702c-160">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="c702c-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="c702c-161">Verificare che nell'elenco siano incluse tutte le code dell'ambiente legacy.</span><span class="sxs-lookup"><span data-stu-id="c702c-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="c702c-162">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="c702c-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="c702c-163">Verificare che nell'elenco siano inclusi tutti i flussi di lavoro dell'ambiente legacy.</span><span class="sxs-lookup"><span data-stu-id="c702c-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

