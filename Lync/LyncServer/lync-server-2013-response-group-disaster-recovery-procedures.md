---
title: 'Lync Server 2013: Procedure per il ripristino di emergenza dei Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f28f13d1acdbdae58b1aadd6f73871af270b7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="d5649-102">Procedure per il ripristino di emergenza dei Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5649-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5649-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d5649-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d5649-104">Durante la fase di failover del ripristino di emergenza, i gruppi di risposte si trovano in più pool: nel pool principale (non disponibile) e nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d5649-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="d5649-105">I gruppi di risposte in entrambi i pool hanno lo stesso nome e lo stesso proprietario (il pool principale), ma hanno genitori diversi.</span><span class="sxs-lookup"><span data-stu-id="d5649-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="d5649-106">Durante questo periodo i cmdlet di Response Group funzionano in modo leggermente diverso.</span><span class="sxs-lookup"><span data-stu-id="d5649-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="d5649-107">Assicurarsi di usare i parametri specificati nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="d5649-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="d5649-108">Per informazioni dettagliate sul funzionamento dei cmdlet durante la fase di failover, vedere l'articolo di Blog di NextHop "Lync Server 2013: recupero di Response Groups durante [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)il ripristino di emergenza".</span><span class="sxs-lookup"><span data-stu-id="d5649-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="d5649-109">Questo articolo di Blog si applica anche alla versione rilasciata di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5649-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="d5649-110">Seguire i passaggi descritti nella procedura seguente per preparare ed eseguire il ripristino di emergenza per il servizio Response Group di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d5649-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="d5649-111">Per eseguire il failover e il failover del gruppo di risposte</span><span class="sxs-lookup"><span data-stu-id="d5649-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="d5649-112">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d5649-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d5649-113">Eseguire in routine i backup.</span><span class="sxs-lookup"><span data-stu-id="d5649-113">Routinely perform backups.</span></span> <span data-ttu-id="d5649-114">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="d5649-114">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="d5649-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5649-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="d5649-116">Durante un'interruzione, dopo il failover nel pool di backup, importare i Response Groups nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d5649-116">During an outage, after failover to the backup pool, import the response groups to the backup pool.</span></span> <span data-ttu-id="d5649-117">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="d5649-117">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="d5649-118">Se si vogliono sostituire le impostazioni a livello di applicazione nel pool di backup con le impostazioni del pool principale, includere il parametro – ReplaceExistingSettings.</span><span class="sxs-lookup"><span data-stu-id="d5649-118">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="d5649-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5649-119">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d5649-120">Se non Sostituisci le impostazioni nel pool di backup e il pool principale non può essere recuperato, le impostazioni del pool principale andranno perse.</span><span class="sxs-lookup"><span data-stu-id="d5649-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="d5649-121">Per informazioni dettagliate, vedere <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">pianificazione del ripristino di emergenza di Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d5649-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="d5649-122">Verificare che l'importazione abbia avuto esito positivo visualizzando i gruppi di risposta importati.</span><span class="sxs-lookup"><span data-stu-id="d5649-122">Verify that the import was successful by displaying the imported response groups.</span></span> <span data-ttu-id="d5649-123">I gruppi di risposta importati continuano a essere di proprietà del pool principale.</span><span class="sxs-lookup"><span data-stu-id="d5649-123">The imported response groups are still owned by the primary pool.</span></span> <span data-ttu-id="d5649-124">Effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="d5649-124">Do the following:</span></span>
    
      - <span data-ttu-id="d5649-125">Visualizzare tutti i flussi di lavoro nel pool di backup di proprietà del pool principale e verificare che siano inclusi tutti i flussi di lavoro del pool principale.</span><span class="sxs-lookup"><span data-stu-id="d5649-125">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included.</span></span> <span data-ttu-id="d5649-126">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="d5649-126">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="d5649-127">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5649-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="d5649-128">Visualizzare tutte le code nel pool di backup di proprietà del pool principale e verificare che siano incluse tutte le code di pool primarie.</span><span class="sxs-lookup"><span data-stu-id="d5649-128">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included.</span></span> <span data-ttu-id="d5649-129">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="d5649-129">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="d5649-130">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5649-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="d5649-131">Visualizzare tutti i gruppi di agenti nel pool di backup di proprietà del pool principale e verificare che siano inclusi tutti i gruppi di agenti di pool primari.</span><span class="sxs-lookup"><span data-stu-id="d5649-131">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included.</span></span> <span data-ttu-id="d5649-132">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="d5649-132">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="d5649-133">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5649-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="d5649-134">Visualizzare tutte le ore di attività nel pool di backup di proprietà del pool principale e verificare che siano incluse tutte le ore del pool principale.</span><span class="sxs-lookup"><span data-stu-id="d5649-134">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included.</span></span> <span data-ttu-id="d5649-135">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="d5649-135">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="d5649-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5649-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="d5649-137">Visualizzare tutti i set di festività nel pool di backup di proprietà del pool principale e verificare che siano inclusi tutti i set di festività principali del pool.</span><span class="sxs-lookup"><span data-stu-id="d5649-137">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included.</span></span> <span data-ttu-id="d5649-138">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="d5649-138">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="d5649-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5649-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="d5649-140">In alternativa, puoi visualizzare tutti i gruppi di risposte nel pool di backup, inclusi quelli di proprietà del pool principale e quelli di proprietà del pool di backup, usando il parametro – ShowAll anziché il parametro – Owner.</span><span class="sxs-lookup"><span data-stu-id="d5649-140">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter.</span></span> <span data-ttu-id="d5649-141">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5649-141">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d5649-142">Devi usare il parametro – ShowAll o il parametro – Owner.</span><span class="sxs-lookup"><span data-stu-id="d5649-142">You must use either the –ShowAll parameter or the –Owner parameter.</span></span> <span data-ttu-id="d5649-143">Se non si usa uno di questi parametri, i gruppi di risposta importati nel pool di backup non verranno elencati nei risultati restituiti dai cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5649-143">If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="d5649-144">Verificare che l'importazione abbia avuto successo effettuando una chiamata a un gruppo di risposte importato e verificando che la chiamata sia gestita correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5649-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="d5649-145">Richiedere agli agenti che sono membri di gruppi di agenti formali di accedere ai gruppi di agenti nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d5649-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="d5649-146">Gestire e modificare i gruppi di risposta importati come di consueto.</span><span class="sxs-lookup"><span data-stu-id="d5649-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d5649-147">Mentre i gruppi di risposte si trovano nel pool di backup, è necessario usare Lync Server Management Shell per gestirli.</span><span class="sxs-lookup"><span data-stu-id="d5649-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="d5649-148">Non è possibile usare il pannello di controllo di Lync Server per gestire i gruppi di risposta importati nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d5649-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="d5649-149">Dopo il ripristino del pool principale e il failback, esportare i gruppi di risposta di pool primari importati nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d5649-149">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool.</span></span> <span data-ttu-id="d5649-150">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="d5649-150">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="d5649-151">Importare di nuovo i gruppi di risposte nel pool principale.</span><span class="sxs-lookup"><span data-stu-id="d5649-151">Import the response groups back to the primary pool.</span></span> <span data-ttu-id="d5649-152">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="d5649-152">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="d5649-153">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5649-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5649-154">Se si ricompila un pool durante il recupero, sia con lo stesso nome di dominio completo o con uno diverso (FQDN), è necessario usare il parametro – OverwriteOwner.</span><span class="sxs-lookup"><span data-stu-id="d5649-154">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter.</span></span> <span data-ttu-id="d5649-155">Come regola generale, è sempre possibile usare il parametro – OverwriteOwner quando si importano nuovamente i gruppi di risposte nel pool principale.</span><span class="sxs-lookup"><span data-stu-id="d5649-155">As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="d5649-156">Se si è distribuito un nuovo pool (con lo stesso FQDN o un nome di dominio completo diverso) per sostituire il pool principale e si vuole usare le impostazioni a livello di applicazione dal pool di backup per il nuovo pool, includere il parametro – ReplaceExistingSettings.</span><span class="sxs-lookup"><span data-stu-id="d5649-156">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="d5649-157">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="d5649-157">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="d5649-158">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5649-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d5649-159">Se non si vuole sostituire le impostazioni a livello di applicazione e il file audio predefinito per la musica in blocco per il nuovo pool con le impostazioni del pool di backup, il nuovo pool utilizzerà le impostazioni a livello di applicazione predefinite.</span><span class="sxs-lookup"><span data-stu-id="d5649-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="d5649-160">Verificare che l'importazione di nuovo nel pool principale abbia avuto successo visualizzando la configurazione del gruppo di risposta importata.</span><span class="sxs-lookup"><span data-stu-id="d5649-160">Verify that the import back to the primary pool was successful by displaying the imported response group configuration.</span></span> <span data-ttu-id="d5649-161">Effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="d5649-161">Do the following:</span></span>
    
      - <span data-ttu-id="d5649-162">Visualizzare tutti i flussi di lavoro nel pool principale e verificare che siano inclusi tutti i flussi di lavoro importati.</span><span class="sxs-lookup"><span data-stu-id="d5649-162">Display all the workflows in the primary pool, and verify that all the imported workflows are included.</span></span> <span data-ttu-id="d5649-163">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="d5649-163">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="d5649-164">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5649-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="d5649-165">Visualizzare tutte le code nel pool principale e verificare che siano incluse tutte le code importate.</span><span class="sxs-lookup"><span data-stu-id="d5649-165">Display all the queues in the primary pool, and verify that all the imported queues are included.</span></span> <span data-ttu-id="d5649-166">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="d5649-166">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="d5649-167">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5649-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="d5649-168">Visualizzare tutti i gruppi di agenti nel pool principale e verificare che siano inclusi tutti i gruppi di agenti importati.</span><span class="sxs-lookup"><span data-stu-id="d5649-168">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included.</span></span> <span data-ttu-id="d5649-169">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="d5649-169">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="d5649-170">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5649-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="d5649-171">Visualizzare tutte le ore di attività nel pool principale e verificare che siano incluse tutte le ore di attività importate.</span><span class="sxs-lookup"><span data-stu-id="d5649-171">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included.</span></span> <span data-ttu-id="d5649-172">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="d5649-172">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="d5649-173">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5649-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="d5649-174">Visualizzare tutti i set di festività nel pool principale e verificare che siano inclusi tutti i set di festività importati.</span><span class="sxs-lookup"><span data-stu-id="d5649-174">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included.</span></span> <span data-ttu-id="d5649-175">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="d5649-175">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="d5649-176">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5649-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="d5649-177">Verificare che l'importazione abbia avuto successo effettuando una chiamata a un gruppo di risposte importato e verificando che la chiamata sia gestita correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5649-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="d5649-178">Facoltativamente, rimuovere i gruppi di risposte di proprietà del pool principale dal pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d5649-178">Optionally, remove the response groups owned by the primary pool from the backup pool.</span></span> <span data-ttu-id="d5649-179">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="d5649-179">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="d5649-180">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d5649-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5649-181">Questo passaggio consente di creare un nuovo file con la configurazione esportata e quindi di rimuoverlo dal pool di backup.</span><span class="sxs-lookup"><span data-stu-id="d5649-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

