---
title: Eseguire la migrazione di Response Group
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eee75721eba2e9a329b9418dfb4291216fcd7f33
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="1c144-102">Eseguire la migrazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="1c144-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c144-103">_**Ultimo argomento modificato:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="1c144-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="1c144-104">Dopo lo spostamento degli utenti nei pool di Lync Server 2013, è possibile eseguire la migrazione dei Response Group.</span><span class="sxs-lookup"><span data-stu-id="1c144-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="1c144-105">La migrazione dei Response Group include i gruppi di agenti di copia, le code, i flussi di lavoro, i file audio e gli oggetti contatto del gruppo di risposta in movimento dalla distribuzione legacy al pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c144-105">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="1c144-106">Dopo aver eseguito la migrazione dei gruppi di risposta legacy, le chiamate ai Response Group vengono gestite dall'applicazione Response gruppo nel pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c144-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="1c144-107">Le chiamate ai Response Group non sono più gestite dal pool legacy.</span><span class="sxs-lookup"><span data-stu-id="1c144-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c144-108">Anche se è possibile eseguire la migrazione dei Response Group prima di spostare tutti gli utenti nel pool di Lync Server 2013, è consigliabile spostare innanzitutto tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1c144-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="1c144-109">In particolare, gli utenti che sono agenti di Response Group non disporranno di funzionalità complete di nuove funzionalità finché non verranno spostati nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c144-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="1c144-110">Prima di eseguire la migrazione dei Response Group, è necessario che sia stato distribuito un pool di Lync Server 2013 che includa l'applicazione del gruppo di risposta.</span><span class="sxs-lookup"><span data-stu-id="1c144-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="1c144-111">L'applicazione Response Group viene installata e attivata per impostazione predefinita quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="1c144-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="1c144-112">È possibile verificare che l'applicazione Response Group sia installata eseguendo il cmdlet **Get-CsService – ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="1c144-112">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c144-113">È possibile creare nuovi gruppi di risposta di Lync Server 2013 nel pool Lync Server 2013 prima di eseguire la migrazione dei Response Group Legacy.</span><span class="sxs-lookup"><span data-stu-id="1c144-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="1c144-114">Per eseguire la migrazione dei Response Group da un pool legacy a Lync Server 2013, è necessario utilizzare il cmdlet **Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1c144-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1c144-115">Il cmdlet Response Group Migration sposta la configurazione del Response Group per l'intero pool.</span><span class="sxs-lookup"><span data-stu-id="1c144-115">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="1c144-116">Non è possibile selezionare gruppi, code o flussi di lavoro specifici di cui eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="1c144-116">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="1c144-117">Dopo aver eseguito la migrazione dei Response Group, è necessario utilizzare il pannello di controllo di Lync Server o i cmdlet di Lync Server Management Shell per verificare che tutti i gruppi di agenti, le code e i flussi di lavoro siano stati spostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="1c144-117">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="1c144-118">Quando si esegue la migrazione dei Response Group, i Response Group di Lync Server 2010 non vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="1c144-118">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="1c144-119">Quando si gestiscono i Response Group dopo la migrazione utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell, è possibile visualizzare entrambi i Response Group di Lync Server 2010 e i Response Group di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c144-119">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="1c144-120">È consigliabile applicare gli aggiornamenti solo ai Response Group di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c144-120">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="1c144-121">I Response Group di Lync Server 2010 vengono mantenuti solo per scopi di rollback.</span><span class="sxs-lookup"><span data-stu-id="1c144-121">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="1c144-122">Dopo che la migrazione è stata completata e che sono stati creati i nuovi Response Group, il pannello di controllo di Lync Server e Lync Server Management Shell visualizzeranno le versioni di Lync Server 2010 e Lync Server 2013 di ogni Response Group.</span><span class="sxs-lookup"><span data-stu-id="1c144-122">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="1c144-123">Non utilizzare il pannello di controllo di Lync Server o Lync Server Management Shell per rimuovere i Response Group di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1c144-123">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="1c144-124">Se si rimuove uno, il Response Group corrispondente che è stato creato durante la migrazione smetterà di funzionare.</span><span class="sxs-lookup"><span data-stu-id="1c144-124">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="1c144-125">I Response Group di Lync Server 2010 verranno rimossi quando si rimuove la Commissione del pool di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1c144-125">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1c144-126">È consigliabile rimuovere i dati dalla distribuzione precedente solo dopo la rimozione del pool.</span><span class="sxs-lookup"><span data-stu-id="1c144-126">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="1c144-127">È inoltre consigliabile esportare i Response Group subito dopo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="1c144-127">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="1c144-128">Se un Response Group di Lync Server 2010 deve essere rimosso, è possibile ripristinare i Response Group dal backup per ottenere i Response Group di Lync Server 2013 in esecuzione di nuovo.</span><span class="sxs-lookup"><span data-stu-id="1c144-128">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="1c144-129">Lync Server 2013 introduce una nuova funzionalità Response Group denominata **tipo di flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="1c144-129">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="1c144-130">Il **Tipo di flusso di lavoro** può essere **Gestito** o **Non gestito**.</span><span class="sxs-lookup"><span data-stu-id="1c144-130">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="1c144-131">Tutti i Response Group vengono migrati con il **Tipo di flusso di lavoro** impostato su **Non gestito** e con un elenco di responsabili vuoto.</span><span class="sxs-lookup"><span data-stu-id="1c144-131">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="1c144-132">Quando si esegue il cmdlet **Move-CsRgsConfiguration**, i gruppi di agenti, le code, i flussi di lavoro e i file audio rimangono nel pool legacy per consentirne il ripristino.</span><span class="sxs-lookup"><span data-stu-id="1c144-132">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="1c144-133">Se occorre eseguire il rollback dello stato precedente nel pool legacy, tuttavia, è necessario eseguire il cmdlet **Move-CsApplicationEndpoint** per rispostare gli oggetti contatto nel pool legacy.</span><span class="sxs-lookup"><span data-stu-id="1c144-133">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="1c144-134">La procedura seguente per eseguire la migrazione delle configurazioni di Response Group presuppone che si disponga di una relazione uno-a-uno tra i pool legacy e i pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c144-134">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="1c144-135">Se si prevede di consolidare o dividere i pool durante la migrazione e la distribuzione, è necessario pianificare la mappa del pool legacy al pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c144-135">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="1c144-136">Per eseguire la migrazione delle configurazioni di Response Group</span><span class="sxs-lookup"><span data-stu-id="1c144-136">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="1c144-137">Accedere al computer con un account membro del gruppo RTCUniversalServerAdmins o con le autorizzazioni e i diritti di amministratore equivalenti.</span><span class="sxs-lookup"><span data-stu-id="1c144-137">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="1c144-138">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1c144-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1c144-139">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="1c144-139">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="1c144-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1c144-140">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="1c144-141">Dopo aver eseguito la migrazione di Response Group e agenti nel pool di Lync Server 2013, l'URL utilizzato dagli agenti per accedere e disconnettersi è un URL di Lync Server 2013 ed è disponibile dal menu **strumenti** .</span><span class="sxs-lookup"><span data-stu-id="1c144-141">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="1c144-142">Ricordare agli agenti di aggiornare eventuali riferimenti, come segnalibri, al nuovo URL.</span><span class="sxs-lookup"><span data-stu-id="1c144-142">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="1c144-143">Per verificare la migrazione di Response Group tramite il Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="1c144-143">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1c144-144">Eseguire l'accesso al computer con un account membro del gruppo RTCUniversalReadOnlyAdmins o come minimo membro del ruolo CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1c144-144">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="1c144-145">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1c144-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1c144-146">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1c144-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1c144-147">Nel riquadro di spostamento sinistro fare clic su **Response Group**.</span><span class="sxs-lookup"><span data-stu-id="1c144-147">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="1c144-148">Nella scheda **flusso di lavoro** verificare che nell'elenco siano inclusi tutti i flussi di lavoro dell'ambiente Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1c144-148">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="1c144-149">Fare clic sulla scheda **coda** e verificare che nell'elenco siano incluse tutte le code dell'ambiente Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1c144-149">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="1c144-150">Fare clic sulla scheda **gruppo** e verificare che nell'elenco siano inclusi tutti i gruppi di agenti nell'ambiente Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1c144-150">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="1c144-151">Per verificare la migrazione di Response Group tramite Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1c144-151">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="1c144-152">Eseguire l'accesso al computer con un account membro del gruppo RTCUniversalReadOnlyAdmins o come minimo membro del ruolo CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1c144-152">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="1c144-153">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1c144-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="1c144-154">Per informazioni dettagliate sui cmdlet seguenti, eseguire:</span><span class="sxs-lookup"><span data-stu-id="1c144-154">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="1c144-155">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="1c144-155">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="1c144-156">Verificare che nell'elenco siano inclusi tutti i gruppi di agenti nell'ambiente Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1c144-156">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="1c144-157">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="1c144-157">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="1c144-158">Verificare che nell'elenco siano incluse tutte le code dell'ambiente Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1c144-158">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="1c144-159">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="1c144-159">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="1c144-160">Verificare che nell'elenco siano inclusi tutti i flussi di lavoro dell'ambiente Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1c144-160">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

