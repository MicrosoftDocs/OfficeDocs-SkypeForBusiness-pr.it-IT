---
title: Eseguire la migrazione di Response Group
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e06b7cec1b02a194b1bb892af0e60771a15ebd5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527453"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="ff4be-102">Eseguire la migrazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="ff4be-102">Migrate response groups</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff4be-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ff4be-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ff4be-104">Dopo lo spostamento degli utenti nei pool di Lync Server 2013, è possibile eseguire la migrazione dei Response Group.</span><span class="sxs-lookup"><span data-stu-id="ff4be-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="ff4be-105">La migrazione dei Response Group include i gruppi di agenti, le code, i flussi di lavoro e i file audio e lo spostamento degli oggetti contatto del gruppo di risposta dalla distribuzione legacy al pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ff4be-105">Migrating response groups includes copying agent groups, queues, workflows, and audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="ff4be-106">Dopo aver eseguito la migrazione dei gruppi di risposta legacy, le chiamate ai Response Group vengono gestite dall'applicazione Response gruppo nel pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ff4be-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="ff4be-107">Le chiamate ai Response Group non sono più gestite dal pool legacy.</span><span class="sxs-lookup"><span data-stu-id="ff4be-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff4be-108">Anche se è possibile eseguire la migrazione dei Response Group prima di spostare tutti gli utenti nel pool di Lync Server 2013, è consigliabile spostare innanzitutto tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="ff4be-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="ff4be-109">In particolare, gli utenti che sono agenti di Response Group non disporranno di funzionalità complete di nuove funzionalità finché non verranno spostati nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ff4be-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="ff4be-110">Prima di eseguire la migrazione dei Response Group, è necessario che sia stato distribuito un pool di Lync Server 2013 che includa l'applicazione del gruppo di risposta.</span><span class="sxs-lookup"><span data-stu-id="ff4be-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="ff4be-111">L'applicazione Response Group viene installata e attivata per impostazione predefinita quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="ff4be-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="ff4be-112">È possibile verificare che l'applicazione Response Group sia installata eseguendo il cmdlet **Get-CsService – ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="ff4be-112">You can ensure that the Response Group application is installed by running the **Get-CsService–ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff4be-113">È possibile creare nuovi gruppi di risposta di Lync Server 2013 nel pool Lync Server 2013 prima di eseguire la migrazione dei Response Group Legacy.</span><span class="sxs-lookup"><span data-stu-id="ff4be-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="ff4be-114">Per eseguire la migrazione dei Response Group da un pool legacy a Lync Server 2013, è necessario utilizzare il cmdlet **Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="ff4be-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="ff4be-115">Prima di poter eseguire **Move-CsRgsConfiguration**, è innanzitutto necessario installare il pacchetto di interfacce di compatibilità con le versioni precedenti di Strumentazione gestione Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="ff4be-115">Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package.</span></span> <span data-ttu-id="ff4be-116">Installare l'applicazione eseguendo OCSWMIBC.msi.</span><span class="sxs-lookup"><span data-stu-id="ff4be-116">Install this application by running OCSWMIBC.msi.</span></span> <span data-ttu-id="ff4be-117">È possibile trovare OCSWMIBC.msi nel supporto di installazione nella cartella Setup.</span><span class="sxs-lookup"><span data-stu-id="ff4be-117">You can find OCSWMIBC.msi on the installation media in the Setup folder.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ff4be-118">Il cmdlet Response Group Migration sposta la configurazione del Response Group per l'intero pool.</span><span class="sxs-lookup"><span data-stu-id="ff4be-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="ff4be-119">Non è possibile selezionare gruppi, code o flussi di lavoro specifici di cui eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="ff4be-119">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="ff4be-120">Dopo aver eseguito la migrazione dei Response Group, è necessario aggiornare l'URL utilizzato dagli agenti formali per accedere ai propri Response Group e utilizzare il pannello di controllo di Lync Server o i cmdlet di Lync Server Management Shell per verificare che tutti i gruppi di agenti, le code e i flussi di lavoro siano stati spostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="ff4be-120">After you migrate the response groups, you need to update the URL that formal agents use to sign into and out of their response groups, and use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="ff4be-121">Quando si esegue la migrazione dei Response Group, i Response Group di Office Communications Server 2007 R2 non vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="ff4be-121">When you migrate response groups, the Office Communications Server 2007 R2 response groups are not removed.</span></span> <span data-ttu-id="ff4be-122">Non rimuovere i Response Group di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ff4be-122">Do not remove Office Communications Server 2007 R2 response groups.</span></span> <span data-ttu-id="ff4be-123">Se si rimuove un Response Group di Office Communications Server 2007 R2, i Response Group in Lync Server 2013 smettono di funzionare.</span><span class="sxs-lookup"><span data-stu-id="ff4be-123">If you remove an Office Communications Server 2007 R2 response group, the response groups in Lync Server 2013 stop working.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ff4be-124">È consigliabile rimuovere i dati dalla distribuzione precedente solo dopo la rimozione del pool.</span><span class="sxs-lookup"><span data-stu-id="ff4be-124">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="ff4be-125">È inoltre consigliabile esportare i Response Group subito dopo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="ff4be-125">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="ff4be-126">Se viene rimosso un Response Group di Office Communications Server 2007 R2, è possibile ripristinare i Response Group dal backup per ottenere i Response Group di Lync Server 2013 in esecuzione di nuovo.</span><span class="sxs-lookup"><span data-stu-id="ff4be-126">If an Office Communications Server 2007 R2 response group gets removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="ff4be-127">Quando si esegue il cmdlet **Move-CsRgsConfiguration**, i gruppi di agenti, le code, i flussi di lavoro e i file audio rimangono nel pool legacy per consentirne il ripristino.</span><span class="sxs-lookup"><span data-stu-id="ff4be-127">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="ff4be-128">Se occorre eseguire il ripristino dello stato precedente nel pool legacy, tuttavia, è necessario eseguire il cmdlet **Move-CsApplicationEndpoint** per rispostare gli oggetti contatto nel pool legacy.</span><span class="sxs-lookup"><span data-stu-id="ff4be-128">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ff4be-129">È consigliabile eliminare eventuali dati dei Response Group nel pool legacy solo dopo la rimozione del pool.</span><span class="sxs-lookup"><span data-stu-id="ff4be-129">We recommend that you don't delete any response group data from the legacy pool until you decommission the pool.</span></span>



</div>

<span data-ttu-id="ff4be-130">La procedura seguente per la migrazione delle configurazioni dei Response Group presuppone che si disponga di una relazione uno-a-uno tra i pool legacy e i pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ff4be-130">The procedure that follows for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="ff4be-131">Se si prevede di consolidare o dividere i pool durante la migrazione e la distribuzione, è necessario pianificare la mappa del pool legacy al pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ff4be-131">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="ff4be-132">Per eseguire la migrazione delle configurazioni di Response Group</span><span class="sxs-lookup"><span data-stu-id="ff4be-132">To Migrate Response Group Configurations</span></span>

1.  <span data-ttu-id="ff4be-133">Individuare il file OCSWMIBC.msi nella cartella Setup dei supporti di installazione e installarlo.</span><span class="sxs-lookup"><span data-stu-id="ff4be-133">Locate OCSWMIBC.msi in the Setup folder of the installation media and install it.</span></span>

2.  <span data-ttu-id="ff4be-134">Accedere al computer con un account membro del gruppo RTCUniversalServerAdmins o con le autorizzazioni e i diritti di amministratore equivalenti.</span><span class="sxs-lookup"><span data-stu-id="ff4be-134">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

3.  <span data-ttu-id="ff4be-135">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ff4be-135">Open the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="ff4be-136">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ff4be-136">At the command line, type the following:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="ff4be-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ff4be-137">For example:</span></span>
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  <span data-ttu-id="ff4be-138">Se è stata distribuita la scheda Response Group per Microsoft Office Communicator 2007 R2 nell'ambiente Office Communications Server 2007 R2, rimuovere la scheda dal file di tabs.xml di Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ff4be-138">If you deployed the Response Group tab for Microsoft Office Communicator 2007 R2 in your Office Communications Server 2007 R2 environment, remove the tab from the Office Communicator 2007 R2 tabs.xml file.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff4be-139">Gli agenti formali utilizzavano la scheda Response Group per accedere ai Response Group in modo da poter ricevere le chiamate.</span><span class="sxs-lookup"><span data-stu-id="ff4be-139">Formal agents used the Response Group tab to sign in to their response groups before they could receive calls.</span></span> <span data-ttu-id="ff4be-140">Se è stata distribuita la scheda Response Group, si è scelto il percorso del file di tabs.xml di Office Communicator 2007 R2 quando è stata distribuita.</span><span class="sxs-lookup"><span data-stu-id="ff4be-140">If you deployed the Response Group tab, you chose the location for the Office Communicator 2007 R2 tabs.xml file when you deployed it.</span></span>

    
    </div>

6.  <span data-ttu-id="ff4be-141">Fornire agli utenti l'URL aggiornato richiesto dagli agenti per l'accesso e la disconnessione dai Response Group.</span><span class="sxs-lookup"><span data-stu-id="ff4be-141">Provide users with the updated URL that agents need to sign into and out of their response groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff4be-142">L'URL in genere è la https://webpoolFQDN/RgsClients/Tab.aspx posizione in cui FQDNpoolWeb è il nome di dominio completo (FQDN) del pool Web associato al pool di cui è stata eseguita la migrazione in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ff4be-142">The URL is typically https://webpoolFQDN/RgsClients/Tab.aspx, where webpoolFQDN is the fully qualified domain name (FQDN) of the web pool that is associated with the pool that you just migrated to Lync Server 2013.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff4be-143">Questo passaggio non è necessario dopo che gli utenti eseguono l'aggiornamento a Lync 2013, poiché l'URL è disponibile dal menu <STRONG>strumenti</STRONG> in Lync.</span><span class="sxs-lookup"><span data-stu-id="ff4be-143">This step is not required after users upgrade to Lync 2013 because the URL is available from the <STRONG>Tools</STRONG> menu in Lync.</span></span>

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="ff4be-144">Per verificare la migrazione di Response Group tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff4be-144">To Verify Response Group Migration by Using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ff4be-145">Aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff4be-145">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="ff4be-146">Nel riquadro di spostamento sinistro fare clic su **Response Group**.</span><span class="sxs-lookup"><span data-stu-id="ff4be-146">In the left navigation pane, click **Response Groups**.</span></span>

3.  <span data-ttu-id="ff4be-147">Nella scheda **flusso di lavoro** verificare che nell'elenco siano inclusi tutti i flussi di lavoro dell'ambiente Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ff4be-147">On the **Workflow** tab, verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="ff4be-148">Fare clic sulla scheda **coda** e verificare che nell'elenco siano incluse tutte le code dell'ambiente Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ff4be-148">Click the **Queue** tab, and verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

5.  <span data-ttu-id="ff4be-149">Fare clic sulla scheda **gruppo** e verificare che nell'elenco siano inclusi tutti i gruppi di agenti nell'ambiente Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ff4be-149">Click the **Group** tab, and verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a><span data-ttu-id="ff4be-150">Per verificare la migrazione dei Response Group tramite i cmdlet</span><span class="sxs-lookup"><span data-stu-id="ff4be-150">To Verify Response Group Migration by Using Cmdlets</span></span>

1.  <span data-ttu-id="ff4be-151">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ff4be-151">Open the Lync Server Management Shell.</span></span>
    
    <span data-ttu-id="ff4be-152">Per informazioni dettagliate sui cmdlet seguenti, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ff4be-152">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

2.  <span data-ttu-id="ff4be-153">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ff4be-153">At the command line, type the following:</span></span>
    
        Get-CsRgsAgentGroup

3.  <span data-ttu-id="ff4be-154">Verificare che nell'elenco siano inclusi tutti i gruppi di agenti nell'ambiente Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ff4be-154">Verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="ff4be-155">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ff4be-155">At the command line, type the following:</span></span>
    
        Get-CsRgsQueue

5.  <span data-ttu-id="ff4be-156">Verificare che nell'elenco siano incluse tutte le code dell'ambiente Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ff4be-156">Verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

6.  <span data-ttu-id="ff4be-157">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ff4be-157">At the command line, type the following:</span></span>
    
        Get-CsRgsWorkflow

7.  <span data-ttu-id="ff4be-158">Verificare che nell'elenco siano inclusi tutti i flussi di lavoro nell'ambiente Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ff4be-158">Verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

