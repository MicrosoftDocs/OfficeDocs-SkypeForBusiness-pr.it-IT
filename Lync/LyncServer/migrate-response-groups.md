---
title: Eseguire la migrazione di Response Group
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ef26b86b1de3fa7f9656cdb2ea82bb7a220948
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="55bea-102">Eseguire la migrazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="55bea-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55bea-103">_**Argomento Ultima modifica:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="55bea-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="55bea-104">Dopo lo spostamento degli utenti nei pool di Lync Server 2013, è possibile eseguire la migrazione dei gruppi di risposta.</span><span class="sxs-lookup"><span data-stu-id="55bea-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="55bea-105">La migrazione dei gruppi di risposte include la copia di gruppi di agenti, code, flussi di lavoro, file audio e oggetti contatto del gruppo di risposte in spostamento dalla distribuzione legacy al pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55bea-105">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="55bea-106">Dopo la migrazione dei gruppi di risposta legacy, le chiamate ai gruppi di risposta vengono gestite dall'applicazione Response Group nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55bea-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="55bea-107">Le chiamate ai gruppi di risposte non vengono più gestite dal pool legacy.</span><span class="sxs-lookup"><span data-stu-id="55bea-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55bea-108">Anche se è possibile eseguire la migrazione di gruppi di risposte prima di spostare tutti gli utenti nel pool di Lync Server 2013, è consigliabile spostare prima tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="55bea-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="55bea-109">In particolare, gli utenti che sono agenti del gruppo di risposta non avranno la piena funzionalità delle nuove caratteristiche finché non verranno spostati nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55bea-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="55bea-110">Prima di eseguire la migrazione dei gruppi di risposte, è necessario che sia stato implementato un pool di Lync Server 2013 che include l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="55bea-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="55bea-111">L'applicazione Response Group viene installata e attivata per impostazione predefinita quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="55bea-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="55bea-112">Puoi verificare che l'applicazione Response Group sia installata eseguendo il cmdlet **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="55bea-112">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55bea-113">È possibile creare nuovi gruppi di risposta di Lync Server 2013 nel pool di Lync Server 2013 prima di eseguire la migrazione dei gruppi di risposta legacy.</span><span class="sxs-lookup"><span data-stu-id="55bea-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="55bea-114">Per eseguire la migrazione dei gruppi di risposte da un pool legacy a Lync Server 2013, è possibile usare il cmdlet **Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="55bea-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="55bea-115">Il cmdlet di migrazione del gruppo di risposte sposta la configurazione del gruppo di risposte per l'intero pool.</span><span class="sxs-lookup"><span data-stu-id="55bea-115">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="55bea-116">Non è possibile selezionare gruppi, code o flussi di lavoro specifici per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="55bea-116">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="55bea-117">Dopo la migrazione dei gruppi di risposta, è necessario utilizzare il pannello di controllo di Lync Server o i cmdlet di Lync Server Management Shell per verificare che tutti i gruppi di agenti, le code e i flussi di lavoro siano stati spostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="55bea-117">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="55bea-118">Quando si esegue la migrazione dei gruppi di risposte, i gruppi di risposta di Lync Server 2010 non vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="55bea-118">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="55bea-119">Quando si gestiscono i gruppi di risposta dopo la migrazione tramite il pannello di controllo di Lync Server o Lync Server Management Shell, è possibile visualizzare i gruppi di risposta di Lync Server 2010 e i gruppi di risposta di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55bea-119">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="55bea-120">È consigliabile applicare gli aggiornamenti solo ai gruppi di risposta di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55bea-120">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="55bea-121">I gruppi di risposte di Lync Server 2010 vengono mantenuti solo per scopi di rollback.</span><span class="sxs-lookup"><span data-stu-id="55bea-121">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="55bea-122">Dopo aver completato la migrazione e creato i nuovi gruppi di risposta, il pannello di controllo di Lync Server e Lync Server Management Shell visualizzeranno le versioni Lync Server 2010 e Lync Server 2013 di ogni gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="55bea-122">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="55bea-123">Non usare il pannello di controllo di Lync Server o Lync Server Management Shell per rimuovere i gruppi di risposta di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="55bea-123">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="55bea-124">Se si rimuove uno, il gruppo di risposte corrispondente creato durante la migrazione smetterà di funzionare.</span><span class="sxs-lookup"><span data-stu-id="55bea-124">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="55bea-125">I gruppi di risposta di Lync Server 2010 verranno rimossi quando si decommissionerà il pool di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="55bea-125">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="55bea-126">È consigliabile non rimuovere i dati dalla distribuzione precedente fino a quando non si esegue la disattivazione del pool.</span><span class="sxs-lookup"><span data-stu-id="55bea-126">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="55bea-127">Inoltre, ti consigliamo vivamente di esportare i Response Group subito dopo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="55bea-127">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="55bea-128">Se un gruppo di risposte di Lync Server 2010 deve essere rimosso, è possibile ripristinare i gruppi di risposte dal backup per ottenere i gruppi di risposta di Lync Server 2013 in funzione.</span><span class="sxs-lookup"><span data-stu-id="55bea-128">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="55bea-129">Lync Server 2013 introduce una nuova funzionalità del gruppo di risposte denominata **tipo di flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="55bea-129">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="55bea-130">Il **tipo di flusso di lavoro** può essere **gestito** o **non gestito**.</span><span class="sxs-lookup"><span data-stu-id="55bea-130">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="55bea-131">Tutti i gruppi di risposte vengono migrati con il **tipo di flusso di lavoro** impostato su **non gestito** e con un elenco di gestione vuoto.</span><span class="sxs-lookup"><span data-stu-id="55bea-131">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="55bea-132">Quando si esegue il cmdlet **Move-CsRgsConfiguration** , i gruppi di agenti, le code, i flussi di lavoro e i file audio rimangono nel pool legacy per scopi di rollback.</span><span class="sxs-lookup"><span data-stu-id="55bea-132">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="55bea-133">Se si ha bisogno di eseguire il rollback al pool legacy, deve comunque essere eseguito il cmdlet **Move-CsApplicationEndpoint** per riportare gli oggetti di contatto nel pool legacy.</span><span class="sxs-lookup"><span data-stu-id="55bea-133">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="55bea-134">La procedura seguente per la migrazione delle configurazioni di Response Group presuppone che si disponga di una relazione uno-a-uno tra i pool legacy e i pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55bea-134">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="55bea-135">Se si prevede di consolidare o suddividere i pool durante la migrazione e la distribuzione, è necessario pianificare le mappe del pool legacy a cui è associato il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55bea-135">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="55bea-136">Per eseguire la migrazione delle configurazioni di Response Group</span><span class="sxs-lookup"><span data-stu-id="55bea-136">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="55bea-137">Accedere al computer con un account che sia membro del gruppo RTCUniversalServerAdmins o disponga di diritti di amministratore e autorizzazioni equivalenti.</span><span class="sxs-lookup"><span data-stu-id="55bea-137">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="55bea-138">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="55bea-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="55bea-139">Eseguire</span><span class="sxs-lookup"><span data-stu-id="55bea-139">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="55bea-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="55bea-140">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="55bea-141">Dopo la migrazione di gruppi di risposte e agenti al pool di Lync Server 2013, l'URL usato dagli agenti per accedere e disconnettersi è un URL di Lync Server 2013 ed è disponibile nel menu **strumenti** .</span><span class="sxs-lookup"><span data-stu-id="55bea-141">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="55bea-142">Ricorda agli agenti di aggiornare tutti i riferimenti, ad esempio i segnalibri, al nuovo URL.</span><span class="sxs-lookup"><span data-stu-id="55bea-142">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="55bea-143">Per verificare la migrazione dei gruppi di risposte tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="55bea-143">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="55bea-144">Accedere al computer con un account che è un membro del gruppo RTCUniversalReadOnlyAdmins o è minimamente un membro del ruolo CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="55bea-144">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="55bea-145">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="55bea-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="55bea-146">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="55bea-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="55bea-147">Nel riquadro di spostamento sinistro fare clic su **Response Groups**.</span><span class="sxs-lookup"><span data-stu-id="55bea-147">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="55bea-148">Nella scheda **flusso di lavoro** verificare che tutti i flussi di lavoro nell'ambiente Lync Server 2010 siano inclusi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="55bea-148">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="55bea-149">Fare clic sulla scheda **coda** e verificare che tutte le code nell'ambiente Lync Server 2010 siano incluse nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="55bea-149">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="55bea-150">Fare clic sulla scheda **gruppo** e verificare che tutti i gruppi di agenti nell'ambiente Lync Server 2010 siano inclusi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="55bea-150">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="55bea-151">Per verificare la migrazione dei gruppi di risposte tramite Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="55bea-151">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="55bea-152">Accedere al computer con un account che è un membro del gruppo RTCUniversalReadOnlyAdmins o è minimamente un membro del ruolo CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="55bea-152">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="55bea-153">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="55bea-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="55bea-154">Per informazioni dettagliate sui cmdlet seguenti, eseguire:</span><span class="sxs-lookup"><span data-stu-id="55bea-154">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="55bea-155">Eseguire</span><span class="sxs-lookup"><span data-stu-id="55bea-155">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="55bea-156">Verificare che tutti i gruppi di agenti nell'ambiente Lync Server 2010 siano inclusi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="55bea-156">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="55bea-157">Eseguire</span><span class="sxs-lookup"><span data-stu-id="55bea-157">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="55bea-158">Verificare che tutte le code nell'ambiente Lync Server 2010 siano incluse nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="55bea-158">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="55bea-159">Eseguire</span><span class="sxs-lookup"><span data-stu-id="55bea-159">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="55bea-160">Verificare che tutti i flussi di lavoro nell'ambiente Lync Server 2010 siano inclusi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="55bea-160">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

