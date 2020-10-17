---
title: Lync Server 2013 Response Group procedure di ripristino di emergenza
description: Lync Server 2013 Response Group procedure di ripristino di emergenza.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9021fb75c8f937bfd298578a9241d6256d26d85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563892"
---
# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="1a9a8-103">Procedure per il ripristino di emergenza di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a9a8-103">Response group disaster recovery procedures in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a9a8-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1a9a8-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1a9a8-105">Durante la fase di failover del ripristino di emergenza, i Response Group risiedono in più pool, ovvero nel pool principale (che non è disponibile) e nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-105">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="1a9a8-106">I Response Group in entrambi i pool hanno lo stesso nome e lo stesso proprietario (il pool principale), ma hanno elementi padre diversi.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-106">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="1a9a8-107">Durante questo periodo, i cmdlet Response Group funzionano leggermente in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-107">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="1a9a8-108">Prestare attenzione a utilizzare i parametri esattamente come specificato nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-108">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="1a9a8-109">Per informazioni dettagliate sul funzionamento dei cmdlet durante la fase di failover, vedere l'articolo del Blog di NextHop "Lync Server 2013: ripristino dei Response Group durante il recupero di emergenza" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957) .</span><span class="sxs-lookup"><span data-stu-id="1a9a8-109">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="1a9a8-110">Questo articolo del Blog si applica anche alla versione rilasciata di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-110">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="1a9a8-111">Utilizzare la procedura seguente per preparare ed eseguire il ripristino di emergenza per il servizio Response Group di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-111">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="1a9a8-112">Per eseguire il failover e il failback di Response Group</span><span class="sxs-lookup"><span data-stu-id="1a9a8-112">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="1a9a8-113">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1a9a8-p102">Eseguire regolarmente i backup. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p102">Routinely perform backups. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="1a9a8-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-116">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="1a9a8-p103">Durante un'interruzione del servizio, dopo il failover al pool di backup, importare i Response Group nel pool di backup. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p103">During an outage, after failover to the backup pool, import the response groups to the backup pool. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="1a9a8-p104">Se si desidera sostituire le impostazioni a livello di applicazione nel pool di backup con le impostazioni del pool principale, includere il parametro –ReplaceExistingSettings. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p104">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter. For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1a9a8-121">Se non si sostituiscono le impostazioni nel pool di backup e il pool principale non può essere ripristinato, le impostazioni del pool principale andranno perse.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-121">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="1a9a8-122">Per informazioni dettagliate, vedere <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for Response Group Disaster Recovery in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-122">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="1a9a8-p106">Verificare che l'importazione sia stata eseguita correttamente visualizzando i Response Group importati. Tali Response Group sono ancora di proprietà del pool principale. Eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p106">Verify that the import was successful by displaying the imported response groups. The imported response groups are still owned by the primary pool. Do the following:</span></span>
    
      - <span data-ttu-id="1a9a8-p107">Visualizzare tutti i flussi di lavoro nel pool di backup che sono di proprietà del pool principale e verificare che siano inclusi tutti i flussi di lavoro del pool principale. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p107">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included. At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="1a9a8-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-128">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="1a9a8-p108">Visualizzare tutte le code nel pool di backup che sono di proprietà del pool principale e verificare che siano incluse tutte le code del pool principale. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p108">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included. At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="1a9a8-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-131">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="1a9a8-p109">Visualizzare tutti i gruppi di agenti nel pool di backup che sono di proprietà del pool principale e verificare che siano inclusi tutti i gruppi di agenti del pool principale. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p109">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included. At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="1a9a8-134">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-134">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="1a9a8-p110">Visualizzare tutti gli orari di ufficio nel pool di backup che sono di proprietà del pool principale e verificare che siano inclusi tutti gli orari di ufficio del pool principale. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p110">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included. At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="1a9a8-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-137">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="1a9a8-p111">Visualizzare tutti i set di festività nel pool di backup che sono di proprietà del pool principale e verificare che siano inclusi tutti i set di festività del pool principale. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p111">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included. At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="1a9a8-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-140">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="1a9a8-p112">In alternativa, è possibile visualizzare tutti i Response Group presenti nel pool di backup, inclusi quelli di proprietà del pool principale e quelli di proprietà del pool di backup, utilizzando il parametro –ShowAll anziché il parametro –Owner. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p112">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter. For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1a9a8-p113">È necessario utilizzare il parametro –ShowAll oppure il parametro –Owner, altrimenti i Response Group importati nel pool di backup non verranno elencati nei risultati restituiti dai cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p113">You must use either the –ShowAll parameter or the –Owner parameter. If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="1a9a8-145">Verificare che l'importazione sia stata eseguita correttamente effettuando una chiamata a un Response Group importato e controllando che la chiamata venga gestita correttamente.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-145">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="1a9a8-146">Richiedere agli agenti membri dei gruppi di agenti formali di connettersi ai rispettivi gruppi nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-146">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="1a9a8-147">Gestire e modificare come di consueto i Response Group importati.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-147">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1a9a8-148">Mentre i Response Group si trovano nel pool di backup, è necessario utilizzare Lync Server Management Shell per gestirli.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-148">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="1a9a8-149">Non è possibile utilizzare il pannello di controllo di Lync Server per gestire i Response Group importati nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-149">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="1a9a8-p115">Dopo il ripristino del pool principale e il completamento del failback, esportare i Response Group del pool principale che erano stati importati nel pool di backup. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p115">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="1a9a8-p116">Reimportare i Response Group nel pool principale. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p116">Import the response groups back to the primary pool. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="1a9a8-154">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-154">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1a9a8-p117">Se si rigenera un pool durante il ripristino, con lo stesso o con un altro nome di dominio completo (FQDN), è necessario utilizzare il parametro –OverwriteOwner. Come regola generale, è sempre possibile utilizzare il parametro –OverwriteOwner quando si reimportano i Response Group nel pool principale.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p117">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter. As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="1a9a8-p118">Se è stato distribuito un nuovo pool (con lo stesso o con un altro FQDN) per sostituire il pool principale e si desidera utilizzare le impostazioni a livello di applicazione del pool di backup per il nuovo pool, includere il parametro –ReplaceExistingSettings. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p118">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="1a9a8-159">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-159">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1a9a8-160">Se non si desidera sostituire le impostazioni a livello di applicazione e il file audio predefinito della musica di attesa per il nuovo pool con le impostazioni del pool di backup, il nuovo pool utilizzerà le impostazioni predefinite a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-160">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="1a9a8-p119">Verificare che la reimportazione nel pool principale sia stata eseguita correttamente visualizzando la configurazione di Response Group importata. Eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p119">Verify that the import back to the primary pool was successful by displaying the imported response group configuration. Do the following:</span></span>
    
      - <span data-ttu-id="1a9a8-p120">Visualizzare tutti i flussi di lavoro nel pool principale e verificare che siano inclusi tutti i flussi di lavoro importati. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p120">Display all the workflows in the primary pool, and verify that all the imported workflows are included. At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="1a9a8-165">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-165">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="1a9a8-p121">Visualizzare tutte le code nel pool principale e verificare che siano incluse tutte le code importate. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p121">Display all the queues in the primary pool, and verify that all the imported queues are included. At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="1a9a8-168">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-168">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="1a9a8-p122">Visualizzare tutti i gruppi di agenti nel pool principale e verificare che siano inclusi tutti i gruppi di agenti importati. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p122">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included. At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="1a9a8-171">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-171">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="1a9a8-p123">Visualizzare tutti i gli orari di ufficio nel pool principale e verificare che siano inclusi tutti gli orari di ufficio importati. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p123">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included. At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="1a9a8-174">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-174">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="1a9a8-p124">Visualizzare tutti i set di festività nel pool principale e verificare che siano inclusi tutti i set di festività importati. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p124">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included. At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="1a9a8-177">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-177">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="1a9a8-178">Verificare che l'importazione sia stata eseguita correttamente effettuando una chiamata a un Response Group importato e controllando che la chiamata venga gestita correttamente.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-178">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="1a9a8-p125">Facoltativamente, rimuovere dal pool di backup i Response Group di proprietà del pool principale. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-p125">Optionally, remove the response groups owned by the primary pool from the backup pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="1a9a8-181">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a9a8-181">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1a9a8-182">Questo passaggio consente di creare un nuovo file con la configurazione esportata e quindi di rimuoverlo dal pool di backup.</span><span class="sxs-lookup"><span data-stu-id="1a9a8-182">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

