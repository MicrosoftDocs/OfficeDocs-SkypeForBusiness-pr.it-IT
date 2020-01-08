---
title: 'Lync Server 2013: Procedura di failover del pool ABC front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87b6cb610d153374f6f4c9ba8a3c2798c50b88ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a><span data-ttu-id="05d70-102">Procedura di failover del pool ABC front-end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05d70-102">Front End pool ABC failover procedure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05d70-103">_**Argomento Ultima modifica:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="05d70-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="05d70-104">Per eseguire la procedura di failover ABC, seguire i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="05d70-104">Use the following steps to perform the ABC failover procedure.</span></span> <span data-ttu-id="05d70-105">Questa procedura contiene una descrizione di alto livello di ogni passaggio, seguita da comandi e cmdlet da eseguire per ogni passaggio.</span><span class="sxs-lookup"><span data-stu-id="05d70-105">This procedure contains a high-level description of each step, followed by commands and cmdlets to be run for each step.</span></span>

<span data-ttu-id="05d70-106">Per eseguire i cmdlet, aprire un Lync Server Management Shell usando Esegui come amministratore.</span><span class="sxs-lookup"><span data-stu-id="05d70-106">To run the cmdlets, open a Lync Server Management Shell using Run as Administrator.</span></span>

<div>

## <a name="to-perform-an-abc-failover"></a><span data-ttu-id="05d70-107">Per eseguire un failover ABC</span><span class="sxs-lookup"><span data-stu-id="05d70-107">To Perform an ABC Failover</span></span>

1.  <span data-ttu-id="05d70-108">Verificare se il pool A è l'host per il server di gestione centrale (CMS).</span><span class="sxs-lookup"><span data-stu-id="05d70-108">Check whether the pool A is the host for the Central Management Server (CMS).</span></span>
    
      - <span data-ttu-id="05d70-109">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="05d70-109">Run the following cmdlet:</span></span>
        
            Get-CsService -CentralManagement
        
        <span data-ttu-id="05d70-110">Se il campo Identity del CMS attivo punta al nome di dominio completo (FQDN) del pool A, verranno usati i passaggi 2 e 3 della procedura per eseguire il failover del server di gestione centralizzato prima.</span><span class="sxs-lookup"><span data-stu-id="05d70-110">If the Identity field of the active CMS points to the fully qualified domain name (FQDN) of Pool A, then you use steps 2 and 3 of this procedure to fail over the Central Management Server first.</span></span> <span data-ttu-id="05d70-111">In caso contrario, passare al passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="05d70-111">Otherwise, skip to step 4.</span></span>

2.  <span data-ttu-id="05d70-112">Non superare il CMS per il pool B in modalità di ripristino di emergenza eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="05d70-112">Fail over the CMS to Pool B in disaster recovery mode by running the following cmdlet:</span></span>
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    <span data-ttu-id="05d70-113">Dopo aver eseguito questa operazione, è consigliabile trasferire il CMS dal pool B a un altro pool di coppie esistente per una maggiore resilienza.</span><span class="sxs-lookup"><span data-stu-id="05d70-113">After you do this, we recommend that you move the CMS from pool B to another existing paired pool for extra resiliency.</span></span> <span data-ttu-id="05d70-114">Per informazioni dettagliate, vedere [Move-csmanagementserver](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer).</span><span class="sxs-lookup"><span data-stu-id="05d70-114">For details, see [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span></span>

3.  <span data-ttu-id="05d70-115">Se il pool A contiene CMS, importare la configurazione LIS dal pool A nel database LIS del pool B (LIS. MDF).</span><span class="sxs-lookup"><span data-stu-id="05d70-115">If Pool A contains CMS, import the LIS configuration from pool A into pool B’s LIS database (Lis.mdf).</span></span> <span data-ttu-id="05d70-116">Questo funzionerà solo se è stato eseguito il backup dei dati LIS su base regolare.</span><span class="sxs-lookup"><span data-stu-id="05d70-116">This will work only if you have been backing up LIS data on a regular basis.</span></span> <span data-ttu-id="05d70-117">Per importare la configurazione LIS, eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="05d70-117">To import the LIS configuration, run the following cmdlets:</span></span>
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  <span data-ttu-id="05d70-118">Importare flussi di lavoro di servizio di Response Group di Lync Server dal pool A nel pool B.</span><span class="sxs-lookup"><span data-stu-id="05d70-118">Import backed-up Lync Server Response Group service workflows from pool A into pool B.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="05d70-119">Al momento, il cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> richiede che i nomi delle code e dei flussi di lavoro nel pool A siano distinti dai nomi delle code e dei flussi di lavoro nel pool B. Se i nomi non sono distinti, viene visualizzato un messaggio di errore quando si esegue il cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> e le code e i flussi di lavoro dovranno essere rinominati nel pool B prima di procedere con il cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="05d70-119">Currently, the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet requires that the queue and workflow names on pool A are distinct from the queue and workflow names on pool B. If the names are not distinct, you will get an error when running the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet, and the queues and workflows will need to be renamed in pool B before proceeding with <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet.</span></span>

    
    </div>
    
    <span data-ttu-id="05d70-120">Sono disponibili due opzioni per l'importazione della configurazione del gruppo di risposte dal pool A al pool B. L'opzione che si usa dipende dal fatto che si vuole sovrascrivere le impostazioni a livello di applicazione del pool B con le impostazioni a livello di applicazione in pool A.</span><span class="sxs-lookup"><span data-stu-id="05d70-120">You have two options for importing the Response Group configuration from pool A to pool B. Which option you use depends on whether you want to overwrite the application-level settings of pool B with the application-level settings in pool A.</span></span>
    
      - <span data-ttu-id="05d70-121">Se si vogliono sovrascrivere le impostazioni del pool B, eseguire il cmdlet **Import-CsRgsConfiguration** con l'opzione **ReplaceExistingSettings** :</span><span class="sxs-lookup"><span data-stu-id="05d70-121">If you want to overwrite the Pool B settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="05d70-122">Se non si vuole sovrascrivere le impostazioni del pool B, usare il cmdlet **Import-CsRgsConfiguration** senza l'opzione **ReplaceExistingSettings** .</span><span class="sxs-lookup"><span data-stu-id="05d70-122">If you do not want to overwrite the Pool B settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="05d70-123">Tieni presente che se non vuoi sovrascrivere le impostazioni a livello di applicazione del pool di backup (pool B) con le impostazioni del pool principale (pool A), le impostazioni A livello di applicazione di pool A verranno perse se il pool A viene perso, perché l'applicazione Response Group può archiviare solo un set di impostazioni a livello di applicazione per pool.</span><span class="sxs-lookup"><span data-stu-id="05d70-123">Keep in mind that if you do not want to overwrite the application-level settings of the backup pool (pool B) with the settings of the primary pool (pool A), pool A’s application-level settings will be lost if pool A is lost, because the Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="05d70-124">Quando il pool C viene distribuito in sostituzione del pool A, le impostazioni a livello di applicazione devono essere riconfigurate, incluso il file audio predefinito per la musica in blocco.</span><span class="sxs-lookup"><span data-stu-id="05d70-124">When pool C is deployed to replace pool A, the application-level settings must be reconfigured, including the default music-on-hold audio file.</span></span>

    
    </div>

5.  <span data-ttu-id="05d70-125">Verificare che l'importazione della configurazione del gruppo di risposte abbia avuto successo eseguendo i cmdlet seguenti per visualizzare i gruppi di risposta importati.</span><span class="sxs-lookup"><span data-stu-id="05d70-125">Verify that the Response Group configuration import was successful by running the following cmdlets to display the imported response groups.</span></span> <span data-ttu-id="05d70-126">Tieni presente che i gruppi di risposta importati continuano a essere di proprietà del pool A.</span><span class="sxs-lookup"><span data-stu-id="05d70-126">Note that the imported response groups are still owned by pool A.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  <span data-ttu-id="05d70-127">Per i numeri non assegnati, sposti gli intervalli di numeri non assegnati che usano "annuncio" come servizio di annuncio selezionato dalla piscina a al pool B. Per eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="05d70-127">For Unassigned Numbers, move the Unassigned Number ranges that are using "Announcement" as the selected announcement service from pool A to pool B. To do so:</span></span>
    
      - <span data-ttu-id="05d70-128">Ricrea tutti gli annunci distribuiti in pool A sul pool B. Se sono stati usati file audio durante la distribuzione degli annunci nel pool A, questi file saranno necessari per ricreare gli annunci nel pool B. Per ricreare gli annunci nel pool B, usare i cmdlet **New-CsAnnouncement** , con il pool b come servizio padre.</span><span class="sxs-lookup"><span data-stu-id="05d70-128">Re-create all announcements that were deployed in pool A on pool B. If any audio files were used when deploying the announcements in pool A, these files will be needed to re-create the announcements in pool B. To re-create the announcements in pool B, use the **New-CsAnnouncement** cmdlets, with pool B as the Parent service.</span></span>
    
      - <span data-ttu-id="05d70-129">Riassegnare la destinazione a tutti gli intervalli di numeri non assegnati destinati a un annuncio nel pool a degli annunci appena distribuiti nel pool B. eseguire il cmdlet seguente per ogni intervallo di numeri non assegnati destinato a un annuncio del pool A:</span><span class="sxs-lookup"><span data-stu-id="05d70-129">Retarget all the Unassigned Number ranges that are targeting an announcement in pool A to the newly deployed announcements in pool B. Run the following cmdlet for every Unassigned Number range targeting an announcement of pool A:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="05d70-130">Questo passaggio non è necessario per gli intervalli di numeri non assegnati che usano "messaggistica unificata di Exchange" come servizio di annuncio selezionato.</span><span class="sxs-lookup"><span data-stu-id="05d70-130">This step is not required for unassigned number ranges that use "Exchange UM" as the selected announcement service.</span></span>

    
    </div>

7.  <span data-ttu-id="05d70-131">Eseguire il failover del pool da a al pool B in modalità ripristino di emergenza (DR) eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="05d70-131">Fail over Pool A to Pool B in Disaster Recovery (DR) mode, by running the following cmdlet:</span></span>
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  <span data-ttu-id="05d70-132">Creare il pool C, ma non avviare alcun servizio nel pool C.</span><span class="sxs-lookup"><span data-stu-id="05d70-132">Build pool C, but do not start any services on pool C.</span></span>
    
    <span data-ttu-id="05d70-133">Tieni presente che questo passaggio può essere eseguito contemporaneamente ai passaggi 5 e 6.</span><span class="sxs-lookup"><span data-stu-id="05d70-133">Note that this step can be carried out concurrently with steps 5 and 6.</span></span>

9.  <span data-ttu-id="05d70-134">Imporre agli utenti ospitati nel pool a di trasferirsi nel pool C eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="05d70-134">Force users homed on pool A to move to pool C by running the following cmdlet:</span></span>
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    <span data-ttu-id="05d70-135">A questo punto, gli utenti ospitati nel pool A inizieranno a provare un'interruzione del servizio.</span><span class="sxs-lookup"><span data-stu-id="05d70-135">At this point, users homed on pool A will begin to experience a service outage.</span></span> <span data-ttu-id="05d70-136">Questa interruzione continuerà fino al passaggio 16, in cui i servizi Point vengono avviati nel pool C.</span><span class="sxs-lookup"><span data-stu-id="05d70-136">This outage will continue until step 16, at which point services are started on pool C.</span></span>

10. <span data-ttu-id="05d70-137">Forzare la directory conferenza del pool a per il passaggio al pool C eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="05d70-137">Force the conference directory of pool A to move to pool C by running the following cmdlet:</span></span>
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. <span data-ttu-id="05d70-138">Forzare l'oggetto contatto CAA (Conference Auto Attendant) a trasferirsi dal pool A al pool C eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="05d70-138">Force the Conference Auto Attendant (CAA) Contact Object to move from pool A to pool C by running the following cmdlet:</span></span>
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. <span data-ttu-id="05d70-139">Copiare il contenuto della conferenza dal pool B al pool C.</span><span class="sxs-lookup"><span data-stu-id="05d70-139">Copy conference content from pool B to pool C.</span></span>

13. <span data-ttu-id="05d70-140">Esportare i dati degli utenti dal pool B e importare i dati utente nel pool C eseguendo i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="05d70-140">Export user data from pool B and import the user data into pool C by running the following cmdlets:</span></span>
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. <span data-ttu-id="05d70-141">Ripristinare i dati dell'applicazione di parcheggio di Call backed-up da pool A in pool C e assegnare gli intervalli orbit Park Call del pool A al pool C.</span><span class="sxs-lookup"><span data-stu-id="05d70-141">Restore backed-up Call Park application data from pool A into pool C and assign the Call Park orbit ranges of pool A to pool C.</span></span>
    
      - <span data-ttu-id="05d70-142">È possibile riassegnare l'intervallo di Orbit di un parcheggio di chiamata del pool A al pool C tramite il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="05d70-142">You can reassign a Call Park orbit range of pool A to pool C either through the Lync Server Control Panel or the Lync Server Management Shell.</span></span> <span data-ttu-id="05d70-143">Per Lync Server Management Shell, eseguire il cmdlet seguente per ogni intervallo di orbit del parcheggio di chiamata assegnato al pool A (si noti che il parametro Identity fa riferimento agli intervalli di orbita del parcheggio di chiamata che appartengono al pool A):</span><span class="sxs-lookup"><span data-stu-id="05d70-143">For the Lync Server Management Shell, run the following cmdlet for every Call Park orbit range assigned to pool A (note that the Identity parameter refers to the Call Park Orbit Ranges that belong to pool A):</span></span>
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - <span data-ttu-id="05d70-144">Se una musica in blocco personalizzata è stata configurata per il parcheggio delle chiamate in pool A, ripristinare il file di musica in blocco di Call Park personalizzato nel pool C.</span><span class="sxs-lookup"><span data-stu-id="05d70-144">If a customized music-on-hold has been configured for Call Park in pool A, restore the Call Park customized music-on-hold file in pool C.</span></span>
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        <span data-ttu-id="05d70-145">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="05d70-145">For example:</span></span>
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - <span data-ttu-id="05d70-146">Infine, riconfigurare le impostazioni del parcheggio delle chiamate nel pool C usando il cmdlet **Set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="05d70-146">Finally, reconfigure the Call Park settings on pool C by using the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="05d70-147">L'applicazione per il parcheggio delle chiamate può archiviare solo un set di impostazioni e un file audio di musica in attesa personalizzato per ogni pool e queste impostazioni non vengono supportate o conservate in caso di emergenza.</span><span class="sxs-lookup"><span data-stu-id="05d70-147">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool, and these settings are not backed up or preserved in the event of a disaster.</span></span>

15. <span data-ttu-id="05d70-148">Se il pool hop successivo per la chat persistente punta al pool A, imposta e pubblica le modifiche della topologia in modo che il server hop successivo punti al pool C.</span><span class="sxs-lookup"><span data-stu-id="05d70-148">If the next hop pool for Persistent Chat is pointing to pool A, make and publish topology changes so that the next hop server points to pool C.</span></span>
    
      - <span data-ttu-id="05d70-149">In Generatore di topologie cambiare il pool di chat persistente in modo che punti al pool C come hop successivo.</span><span class="sxs-lookup"><span data-stu-id="05d70-149">In Topology Builder, change the Persistent Chat pool to point to Pool C as its next hop.</span></span> <span data-ttu-id="05d70-150">A questo scopo, fai clic con il pulsante destro del mouse sul pool di chat persistente, quindi fai clic sulla scheda **generale** e quindi digita il nome del pool C nel **pool hop successivo**.</span><span class="sxs-lookup"><span data-stu-id="05d70-150">To do so, right-click on the Persistent Chat pool, then click the **General** tab, and then type the name of Pool C in **Next Hop Pool**.</span></span>
    
      - <span data-ttu-id="05d70-151">Avviare i servizi nel pool C eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="05d70-151">Start services on pool C by running the following cmdlet:</span></span>
        
            Start-csWindowsService
    
    <span data-ttu-id="05d70-152">A questo punto, l'interruzione del servizio termina per gli utenti originariamente assegnati al pool A.</span><span class="sxs-lookup"><span data-stu-id="05d70-152">At this point, the service outage ends for users originally homed on pool A.</span></span>

16. <span data-ttu-id="05d70-153">Esportare i flussi di lavoro del servizio Response Group di Lync Server dal pool B di proprietà del pool A per l'importazione nel pool C eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="05d70-153">Export Lync Server Response Group service workflows from pool B owned by pool A for import into pool C by running the following cmdlet:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. <span data-ttu-id="05d70-154">Importare i flussi di lavoro del servizio Response Group di Lync Server nel pool C dal pool B.</span><span class="sxs-lookup"><span data-stu-id="05d70-154">Import Lync Server Response Group service workflows into pool C from pool B.</span></span>
    
    <span data-ttu-id="05d70-155">Sono disponibili due opzioni per l'importazione della configurazione del gruppo di risposte dal pool B al pool C. L'opzione che si usa dipende dal fatto che si vuole sovrascrivere le impostazioni a livello di applicazione del pool C con le impostazioni a livello di applicazione nel pool B.</span><span class="sxs-lookup"><span data-stu-id="05d70-155">You have two options are for importing the Response Group configuration from pool B to pool C. Which option you use depends on whether you want to overwrite the application-level settings of pool C with the application-level settings in pool B.</span></span>
    
      - <span data-ttu-id="05d70-156">Se si vogliono sovrascrivere le impostazioni del pool C, eseguire il cmdlet **Import-CsRgsConfiguration** con l'opzione **ReplaceExistingSettings** :</span><span class="sxs-lookup"><span data-stu-id="05d70-156">If you want to overwrite the Pool C settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="05d70-157">Se non si vogliono sovrascrivere le impostazioni del pool C, usare il cmdlet **Import-CsRgsConfiguration** senza l'opzione **ReplaceExistingSettings** .</span><span class="sxs-lookup"><span data-stu-id="05d70-157">If you do not want to overwrite the Pool C settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="05d70-158">Tieni presente che se non vuoi sovrascrivere le impostazioni a livello di applicazione del pool C con le impostazioni del pool di backup (pool B), le impostazioni a livello di applicazione del pool B andranno perse perché l'applicazione Response Group può archiviare solo un set di livello di applicazione impostazioni per pool.</span><span class="sxs-lookup"><span data-stu-id="05d70-158">Keep in mind that if you do not want to overwrite the application-level settings of Pool C with the settings of the backup pool (pool B), pool B’s application-level settings will be lost because the Response Group application can store only one set of application-level settings per pool.</span></span>

    
    </div>

18. <span data-ttu-id="05d70-159">Verificare che l'importazione della configurazione del gruppo di risposte abbia avuto successo eseguendo i cmdlet seguenti per visualizzare i gruppi di risposte importati nel pool C.</span><span class="sxs-lookup"><span data-stu-id="05d70-159">Verify that the Response Group configuration import was successful by running the following cmdlets to display the response groups that have been imported to Pool C.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. <span data-ttu-id="05d70-160">Quando la configurazione importata è stata verificata nel pool C, rimuovere i gruppi di risposta di proprietà del pool principale dal pool B. In questo modo si minimizza il tempo di inattività dei gruppi di risposta.</span><span class="sxs-lookup"><span data-stu-id="05d70-160">When the imported configuration has been verified in pool C, remove the response groups owned by the primary pool from pool B. This will minimize the downtime of the response groups.</span></span>
    
    <span data-ttu-id="05d70-161">Questo passaggio crea un nuovo file con la configurazione esportata e quindi rimuove il file dal pool B.</span><span class="sxs-lookup"><span data-stu-id="05d70-161">This step creates a new file with the exported configuration, and then removes the file from pool B.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. <span data-ttu-id="05d70-162">Sposta nel pool C gli intervalli di numeri non assegnati spostati dal pool A al pool B.</span><span class="sxs-lookup"><span data-stu-id="05d70-162">Move to pool C the Unassigned Number ranges that were moved from pool A to pool B.</span></span>
    
      - <span data-ttu-id="05d70-163">Ricrea in pool C tutti gli annunci ricreati dal pool A nel pool B. Se sono stati usati file audio durante la distribuzione degli annunci da spostare, sarà necessario usare questi file per ricreare gli annunci nel pool C. Per ricreare gli annunci nel pool C, usare i cmdlet **New-CsAnnouncement** , con il pool c come servizio padre.</span><span class="sxs-lookup"><span data-stu-id="05d70-163">Re-create in pool C all announcements that were re-created from pool A in pool B. If any audio files were used when deploying the announcements to be moved, you will need to use these files to re-create the announcements in pool C. To re-create the announcements in pool C, use the **New-CsAnnouncement** cmdlets, with pool C as the Parent service.</span></span>
    
      - <span data-ttu-id="05d70-164">Ridestinazione del pool C tutti gli intervalli di numeri non assegnati che sono stati ridestinati dal pool A al pool B. eseguire il cmdlet seguente per ogni intervallo di numeri non assegnati che deve essere destinato alla destinazione:</span><span class="sxs-lookup"><span data-stu-id="05d70-164">Retarget to pool C all the unassigned number ranges that were retargeted from pool A to pool B. Run the following cmdlet for every Unassigned Number range that needs to be retargeted:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - <span data-ttu-id="05d70-165">Opzionale Rimuovi dal pool B gli annunci che sono stati ricreati nel pool C se non sono più in uso nel pool B. Per rimuovere gli annunci, usa il cmdlet **Remove-CsAnnouncement** .</span><span class="sxs-lookup"><span data-stu-id="05d70-165">(Optional) Remove from pool B the announcements that were re-created in pool C if they are no longer in use in pool B. To remove announcements, use the **Remove-CsAnnouncement** cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="05d70-166">Questo passaggio non è necessario per gli intervalli di numeri non assegnati che usano "messaggistica unificata di Exchange" come servizio di annuncio.</span><span class="sxs-lookup"><span data-stu-id="05d70-166">This step is not required for unassigned number ranges that use "Exchange UM" as the announcement service.</span></span>

        
        </div>

21. <span data-ttu-id="05d70-167">Pulire i dati degli utenti del pool A nel pool B eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="05d70-167">Clean up user data of pool A in pool B by running the following cmdlet:</span></span>
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. <span data-ttu-id="05d70-168">Eseguire le operazioni seguenti in Generatore di topologie:</span><span class="sxs-lookup"><span data-stu-id="05d70-168">Do the following in Topology Builder:</span></span>
    
      - <span data-ttu-id="05d70-169">Raggruppamento A e pool B. Pair pool B e pool C. Quindi Rimuovi pool A dalla topologia e pubblicalo.</span><span class="sxs-lookup"><span data-stu-id="05d70-169">Unpair pool A and pool B. Pair pool B and pool C. Then remove Pool A from the topology and publish it.</span></span> <span data-ttu-id="05d70-170">Per eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="05d70-170">To do so:</span></span>
        
          - <span data-ttu-id="05d70-171">In Generatore di topologie fare clic con il pulsante destro del mouse sul pool B e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="05d70-171">In Topology Builder, right-click on Pool B, and then click **Edit Properties**.</span></span>
        
          - <span data-ttu-id="05d70-172">Fare clic su **resilienza** nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="05d70-172">Click **Resiliency** in the left pane.</span></span>
        
          - <span data-ttu-id="05d70-173">Nella casella sotto il **pool di backup associato**selezionare Pool C. si noti che la casella di selezione del pool di backup associato visualizzerà inizialmente il pool A, perché il pool B è stato associato in precedenza al pool.</span><span class="sxs-lookup"><span data-stu-id="05d70-173">In the box below **Associated Backup Pool**, select Pool C. Note that the Associated Backup Pool selection box will initially display pool A, because pool B was previously associated with this pool.</span></span>
        
          - <span data-ttu-id="05d70-174">Selezionare **failover automatico e failback per la voce**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="05d70-174">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
            
            <span data-ttu-id="05d70-175">Quando si visualizzano i dettagli su questo pool, il pool associato ora viene visualizzato nel riquadro destro in **resilienza**.</span><span class="sxs-lookup"><span data-stu-id="05d70-175">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>
        
          - <span data-ttu-id="05d70-176">Nell'albero della console fare clic con il pulsante destro del mouse su pool A e quindi scegliere Elimina.</span><span class="sxs-lookup"><span data-stu-id="05d70-176">In the console tree, right-click pool A, and then click Delete.</span></span>
        
          - <span data-ttu-id="05d70-177">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="05d70-177">Publish the topology.</span></span>

23. <span data-ttu-id="05d70-178">Eseguire l'applicazione di avvio automatico nel pool C per installare l'applicazione del servizio di backup e quindi avviare l'applicazione di servizio di backup eseguendo la seguente procedura dalla cartella di distribuzione in un computer locale nel pool C:</span><span class="sxs-lookup"><span data-stu-id="05d70-178">Run the bootstrapping application on pool C to install the backup service application, and then start the backup service application by running the following from the deployment folder on a local machine in pool C:</span></span>
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. <span data-ttu-id="05d70-179">Riavviare l'applicazione del servizio di backup nel pool B eseguendo i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="05d70-179">Restart the backup service application on pool B by running the following cmdlets:</span></span>
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. <span data-ttu-id="05d70-180">Se pool C è un pool di Standard Edition (SE) e il pool B include CMS, installare il database CMS manualmente nel pool C eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="05d70-180">If pool C is a Standard Edition (SE) Pool and pool B has CMS, install the CMS database manually on pool C by running the following cmdlet:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. <span data-ttu-id="05d70-181">Richiamare il servizio di backup per sincronizzare i vecchi contenuti di conferenza dal pool B al pool C generati prima di associare B e C insieme e per sincronizzare il contenuto di una nuova conferenza dal pool C al pool B generato dopo l'avvio del pool C e prima che le coppie di B e C vengano raggruppate.</span><span class="sxs-lookup"><span data-stu-id="05d70-181">Invoke the backup service to sync old conferencing content from pool B to pool C that was generated before pairing B and C together, and to sync new conferencing content from pool C to pool B that was generated after starting pool C and before B and C were paired together.</span></span> <span data-ttu-id="05d70-182">A questo scopo, eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="05d70-182">To do so, run the following cmdlets:</span></span>
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. <span data-ttu-id="05d70-183">Per ogni appliance Survivable Branch X associato al pool A:</span><span class="sxs-lookup"><span data-stu-id="05d70-183">For each Survivable Branch Appliance X associated with pool A:</span></span>
    
      - <span data-ttu-id="05d70-184">Arrestare SBA X eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="05d70-184">Shut down SBA X by running the following cmdlet:</span></span>
        
            Stop-CsWindowsService
    
      - <span data-ttu-id="05d70-185">Creare un file contenente un elenco di utenti ospitati in SBA X. L'elenco sarà necessario quando gli utenti verranno spostati di nuovo in SBA X nel passaggio 30.</span><span class="sxs-lookup"><span data-stu-id="05d70-185">Create a file that contains a list of users homed on SBA X. The list will be needed when the users are moved back to SBA X in step 30.</span></span> <span data-ttu-id="05d70-186">A tale scopo, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="05d70-186">To do so, run the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - <span data-ttu-id="05d70-187">Imporre agli utenti residenti in SBA X di trasferirsi nel pool C eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="05d70-187">Force users homed on SBA X to move to pool C by running the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - <span data-ttu-id="05d70-188">Aggiornare i dati di questi utenti eseguendo prima di tutto i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="05d70-188">Update the data of these users by first running the following cmdlets:</span></span>
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        <span data-ttu-id="05d70-189">E quindi Esegui questo script:</span><span class="sxs-lookup"><span data-stu-id="05d70-189">And then run this script:</span></span>
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="05d70-190">Si verificherà un'interruzione del servizio per gli utenti residenti in SBAs associati al pool A finché questi utenti non vengono spostati nel pool C.</span><span class="sxs-lookup"><span data-stu-id="05d70-190">A service outage will occur for users who are homed on SBAs that are associated with pool A until these users are moved to pool C.</span></span>

        
        </div>

28. <span data-ttu-id="05d70-191">In Generatore di topologie, per ogni SBA X precedentemente associato al pool A, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05d70-191">In Topology Builder, for each SBA X previously associated with Pool A, do the following:</span></span>
    
      - <span data-ttu-id="05d70-192">Modificare l'associazione in pool C. A questo scopo, fai clic sul sito della filiale, Espandi il nodo Survivable Branch Appliances o Servers e fai clic su **Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="05d70-192">Change the association to Pool C. To do so, click the branch site, expand the Survivable Branch Appliances or Servers node, and click **Survivable Branch Appliance**.</span></span> <span data-ttu-id="05d70-193">Selezionare quindi il pool di **Servizi utente** in cui l'appliance Survivable Branch si connette a pool C e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="05d70-193">Then select the **Front End pool, User Services Pool** that this Survivable Branch Appliance will connect to as Pool C, and then click **Next**.</span></span>
    
      - <span data-ttu-id="05d70-194">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="05d70-194">Publish the topology.</span></span> <span data-ttu-id="05d70-195">A tale scopo, nell'albero della console fare clic con il pulsante destro del mouse sul nuovo **dispositivo Survivable Branch Appliance**, scegliere **topologia**e quindi fare clic su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="05d70-195">To do so, in the console tree, right-click the new **Survivable Branch Appliance**, click **Topology**, and then click **Publish**.</span></span>

29. <span data-ttu-id="05d70-196">Per ogni SBA X ora associato al pool C:</span><span class="sxs-lookup"><span data-stu-id="05d70-196">For each SBA X now associated with pool C:</span></span>
    
      - <span data-ttu-id="05d70-197">Avviare SBA X eseguendo il cmdlet seguente nell'appliance Survivable Branch:</span><span class="sxs-lookup"><span data-stu-id="05d70-197">Start SBA X by running the following cmdlet on the survivable branch appliance:</span></span>
        
            Start-CsWindowsService
    
      - <span data-ttu-id="05d70-198">Sposta gli utenti originariamente ospitati in SBA X dal pool C a SBA X eseguendo il cmdlet seguente.</span><span class="sxs-lookup"><span data-stu-id="05d70-198">Move users who were originally homed on SBA X from pool C to SBA X by running the following cmdlet.</span></span>
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

