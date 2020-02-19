---
title: 'Lync Server 2013: procedura di failover del pool ABC front end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38943d8e7d374fdd5b1fe202eaef44101bfeb321
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a><span data-ttu-id="aeb97-102">Procedura di failover del pool ABC front end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb97-102">Front End pool ABC failover procedure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aeb97-103">_**Ultimo argomento modificato:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="aeb97-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="aeb97-104">Per eseguire la procedura di failover ABC, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="aeb97-104">Use the following steps to perform the ABC failover procedure.</span></span> <span data-ttu-id="aeb97-105">Questa procedura contiene una descrizione di alto livello di ogni passaggio, seguito dai comandi e dai cmdlet da eseguire per ogni passaggio.</span><span class="sxs-lookup"><span data-stu-id="aeb97-105">This procedure contains a high-level description of each step, followed by commands and cmdlets to be run for each step.</span></span>

<span data-ttu-id="aeb97-106">Per eseguire i cmdlet, aprire una Lync Server Management Shell utilizzando Esegui come amministratore.</span><span class="sxs-lookup"><span data-stu-id="aeb97-106">To run the cmdlets, open a Lync Server Management Shell using Run as Administrator.</span></span>

<div>

## <a name="to-perform-an-abc-failover"></a><span data-ttu-id="aeb97-107">Per eseguire un failover ABC</span><span class="sxs-lookup"><span data-stu-id="aeb97-107">To Perform an ABC Failover</span></span>

1.  <span data-ttu-id="aeb97-108">Controllare se il pool A è l'host per il server di gestione centrale (CMS).</span><span class="sxs-lookup"><span data-stu-id="aeb97-108">Check whether the pool A is the host for the Central Management Server (CMS).</span></span>
    
      - <span data-ttu-id="aeb97-109">Eseguire il seguente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="aeb97-109">Run the following cmdlet:</span></span>
        
            Get-CsService -CentralManagement
        
        <span data-ttu-id="aeb97-110">Se il campo Identity del CMS attivo punta al nome di dominio completo (FQDN) del pool A, è necessario utilizzare i passaggi 2 e 3 di questa procedura per eseguire il failover del server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="aeb97-110">If the Identity field of the active CMS points to the fully qualified domain name (FQDN) of Pool A, then you use steps 2 and 3 of this procedure to fail over the Central Management Server first.</span></span> <span data-ttu-id="aeb97-111">In caso contrario, passare al passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="aeb97-111">Otherwise, skip to step 4.</span></span>

2.  <span data-ttu-id="aeb97-112">Eseguire il failover del CMS nel pool B in modalità di ripristino di emergenza eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="aeb97-112">Fail over the CMS to Pool B in disaster recovery mode by running the following cmdlet:</span></span>
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    <span data-ttu-id="aeb97-113">Dopo aver eseguito questa operazione, è consigliabile spostare il CMS dal pool B a un altro pool di coppie esistente per una maggiore resilienza.</span><span class="sxs-lookup"><span data-stu-id="aeb97-113">After you do this, we recommend that you move the CMS from pool B to another existing paired pool for extra resiliency.</span></span> <span data-ttu-id="aeb97-114">Per informazioni dettagliate, vedere [Move-csmanagementserver](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span><span class="sxs-lookup"><span data-stu-id="aeb97-114">For details, see [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span></span>

3.  <span data-ttu-id="aeb97-115">Se il pool A contiene CMS, importare la configurazione LIS dal pool A nel database LIS del pool B (LIS. MDF).</span><span class="sxs-lookup"><span data-stu-id="aeb97-115">If Pool A contains CMS, import the LIS configuration from pool A into pool B’s LIS database (Lis.mdf).</span></span> <span data-ttu-id="aeb97-116">Questo funzionerà solo se è stato eseguito il backup dei dati LIS su base regolare.</span><span class="sxs-lookup"><span data-stu-id="aeb97-116">This will work only if you have been backing up LIS data on a regular basis.</span></span> <span data-ttu-id="aeb97-117">Per importare la configurazione LIS, eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="aeb97-117">To import the LIS configuration, run the following cmdlets:</span></span>
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  <span data-ttu-id="aeb97-118">Importare i flussi di lavoro di servizio di Response Group per Lync Server di cui è stato eseguito il backup dal pool A nel pool B.</span><span class="sxs-lookup"><span data-stu-id="aeb97-118">Import backed-up Lync Server Response Group service workflows from pool A into pool B.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aeb97-119">Al momento, il cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> richiede che la coda e i nomi dei flussi di lavoro del pool a siano distinti dalla coda e dai nomi dei flussi di lavoro del pool B. Se i nomi non sono distinti, verrà visualizzato un errore durante l'esecuzione del cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> e le code e i flussi di lavoro dovranno essere rinominati nel pool B prima di continuare con il cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="aeb97-119">Currently, the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet requires that the queue and workflow names on pool A are distinct from the queue and workflow names on pool B. If the names are not distinct, you will get an error when running the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet, and the queues and workflows will need to be renamed in pool B before proceeding with <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet.</span></span>

    
    </div>
    
    <span data-ttu-id="aeb97-120">Sono disponibili due opzioni per l'importazione della configurazione di Response Group dal pool A al pool B. L'opzione utilizzata varia a seconda che si desideri sovrascrivere le impostazioni a livello di applicazione del pool B con le impostazioni a livello di applicazione nel pool A.</span><span class="sxs-lookup"><span data-stu-id="aeb97-120">You have two options for importing the Response Group configuration from pool A to pool B. Which option you use depends on whether you want to overwrite the application-level settings of pool B with the application-level settings in pool A.</span></span>
    
      - <span data-ttu-id="aeb97-121">Se si desidera sovrascrivere le impostazioni del pool B, eseguire il cmdlet **Import-CsRgsConfiguration** con l'opzione **ReplaceExistingSettings** :</span><span class="sxs-lookup"><span data-stu-id="aeb97-121">If you want to overwrite the Pool B settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="aeb97-122">Se non si desidera sovrascrivere le impostazioni del pool B, utilizzare il cmdlet **Import-CsRgsConfiguration** senza l'opzione **ReplaceExistingSettings** .</span><span class="sxs-lookup"><span data-stu-id="aeb97-122">If you do not want to overwrite the Pool B settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="aeb97-123">Tenere presente che se non si desidera sovrascrivere le impostazioni a livello di applicazione del pool di backup (pool B) con le impostazioni del pool primario (pool A), le impostazioni A livello di applicazione del pool A devono essere perse se il pool A viene perso, in quanto l'applicazione Response Group può Archivia solo un set di impostazioni a livello di applicazione per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="aeb97-123">Keep in mind that if you do not want to overwrite the application-level settings of the backup pool (pool B) with the settings of the primary pool (pool A), pool A’s application-level settings will be lost if pool A is lost, because the Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="aeb97-124">Dopo la distribuzione del pool C per la sostituzione del pool A, è necessario riconfigurare le impostazioni a livello di applicazione, incluso il file audio predefinito per la musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="aeb97-124">When pool C is deployed to replace pool A, the application-level settings must be reconfigured, including the default music-on-hold audio file.</span></span>

    
    </div>

5.  <span data-ttu-id="aeb97-125">Verificare che l'importazione della configurazione di Response Group abbia avuto esito positivo eseguendo i cmdlet seguenti per visualizzare i Response Group importati.</span><span class="sxs-lookup"><span data-stu-id="aeb97-125">Verify that the Response Group configuration import was successful by running the following cmdlets to display the imported response groups.</span></span> <span data-ttu-id="aeb97-126">Si noti che i Response Group importati sono ancora di proprietà del pool A.</span><span class="sxs-lookup"><span data-stu-id="aeb97-126">Note that the imported response groups are still owned by pool A.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  <span data-ttu-id="aeb97-127">Per i numeri non assegnati, spostare gli intervalli di numeri non assegnati che utilizzano "annuncio" come servizio annuncio selezionato dal pool A al pool B. Per eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="aeb97-127">For Unassigned Numbers, move the Unassigned Number ranges that are using "Announcement" as the selected announcement service from pool A to pool B. To do so:</span></span>
    
      - <span data-ttu-id="aeb97-128">Ricreare tutti gli annunci che sono stati distribuiti nel pool A del pool B. Se i file audio sono stati utilizzati durante la distribuzione degli annunci nel pool A, questi file saranno necessari per ricreare gli annunci nel pool B. Per ricreare gli annunci nel pool B, utilizzare i cmdlet **New-CsAnnouncement** , con il pool b come servizio padre.</span><span class="sxs-lookup"><span data-stu-id="aeb97-128">Re-create all announcements that were deployed in pool A on pool B. If any audio files were used when deploying the announcements in pool A, these files will be needed to re-create the announcements in pool B. To re-create the announcements in pool B, use the **New-CsAnnouncement** cmdlets, with pool B as the Parent service.</span></span>
    
      - <span data-ttu-id="aeb97-129">Reindirizzare tutti gli intervalli di numeri non assegnati che puntano a un annuncio nel pool a per gli annunci appena distribuiti nel pool B. eseguire il cmdlet seguente per ogni intervallo di numeri non assegnati che mira a un annuncio del pool A:</span><span class="sxs-lookup"><span data-stu-id="aeb97-129">Retarget all the Unassigned Number ranges that are targeting an announcement in pool A to the newly deployed announcements in pool B. Run the following cmdlet for every Unassigned Number range targeting an announcement of pool A:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aeb97-130">Questo passaggio non è necessario per gli intervalli di numeri non assegnati che utilizzano "messaggistica unificata di Exchange" come servizio annuncio selezionato.</span><span class="sxs-lookup"><span data-stu-id="aeb97-130">This step is not required for unassigned number ranges that use "Exchange UM" as the selected announcement service.</span></span>

    
    </div>

7.  <span data-ttu-id="aeb97-131">Eseguire il failover del pool a nel pool B in modalità ripristino di emergenza (DR) eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="aeb97-131">Fail over Pool A to Pool B in Disaster Recovery (DR) mode, by running the following cmdlet:</span></span>
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  <span data-ttu-id="aeb97-132">Creare il pool C, ma non avviare alcun servizio nel pool C.</span><span class="sxs-lookup"><span data-stu-id="aeb97-132">Build pool C, but do not start any services on pool C.</span></span>
    
    <span data-ttu-id="aeb97-133">Si noti che questo passaggio può essere eseguito contemporaneamente ai passaggi 5 e 6.</span><span class="sxs-lookup"><span data-stu-id="aeb97-133">Note that this step can be carried out concurrently with steps 5 and 6.</span></span>

9.  <span data-ttu-id="aeb97-134">Forzare gli utenti ospitati nel pool a per passare al pool C eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="aeb97-134">Force users homed on pool A to move to pool C by running the following cmdlet:</span></span>
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    <span data-ttu-id="aeb97-135">A questo punto, gli utenti ospitati nel pool A inizieranno a verificarsi un'interruzione del servizio.</span><span class="sxs-lookup"><span data-stu-id="aeb97-135">At this point, users homed on pool A will begin to experience a service outage.</span></span> <span data-ttu-id="aeb97-136">Questa interruzione continuerà fino al passaggio 16, a questo punto i servizi vengono avviati nel pool C.</span><span class="sxs-lookup"><span data-stu-id="aeb97-136">This outage will continue until step 16, at which point services are started on pool C.</span></span>

10. <span data-ttu-id="aeb97-137">Forzare la directory conferenze del pool a per passare al pool C eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="aeb97-137">Force the conference directory of pool A to move to pool C by running the following cmdlet:</span></span>
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. <span data-ttu-id="aeb97-138">Forzare l'oggetto contatto dell'operatore automatico conferenza (CAA) a passare dal pool A al pool C eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="aeb97-138">Force the Conference Auto Attendant (CAA) Contact Object to move from pool A to pool C by running the following cmdlet:</span></span>
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. <span data-ttu-id="aeb97-139">Copiare il contenuto delle conferenze dal pool B al pool C.</span><span class="sxs-lookup"><span data-stu-id="aeb97-139">Copy conference content from pool B to pool C.</span></span>

13. <span data-ttu-id="aeb97-140">Esportare i dati degli utenti dal pool B e importare i dati degli utenti nel pool C eseguendo i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="aeb97-140">Export user data from pool B and import the user data into pool C by running the following cmdlets:</span></span>
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. <span data-ttu-id="aeb97-141">Ripristinare i dati dell'applicazione Parcheggio di chiamata di cui è stato eseguito il backup dal pool A nel pool C e assegnare gli intervalli di orbit del parcheggio di chiamata del pool A al pool C.</span><span class="sxs-lookup"><span data-stu-id="aeb97-141">Restore backed-up Call Park application data from pool A into pool C and assign the Call Park orbit ranges of pool A to pool C.</span></span>
    
      - <span data-ttu-id="aeb97-142">È possibile riassegnare un intervallo di orbit del parcheggio di chiamata del pool A al pool C tramite il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="aeb97-142">You can reassign a Call Park orbit range of pool A to pool C either through the Lync Server Control Panel or the Lync Server Management Shell.</span></span> <span data-ttu-id="aeb97-143">Per Lync Server Management Shell, eseguire il cmdlet seguente per ogni intervallo di orbit del parcheggio di chiamata assegnato al pool A (si noti che il parametro Identity si riferisce agli intervalli di orbit del parcheggio di chiamata appartenenti al pool A):</span><span class="sxs-lookup"><span data-stu-id="aeb97-143">For the Lync Server Management Shell, run the following cmdlet for every Call Park orbit range assigned to pool A (note that the Identity parameter refers to the Call Park Orbit Ranges that belong to pool A):</span></span>
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - <span data-ttu-id="aeb97-144">Se un brano musicale personalizzato è stato configurato per il parcheggio di chiamata nel pool A, ripristinare il parcheggio di chiamata personalizzato file di musica di attesa nel pool C.</span><span class="sxs-lookup"><span data-stu-id="aeb97-144">If a customized music-on-hold has been configured for Call Park in pool A, restore the Call Park customized music-on-hold file in pool C.</span></span>
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        <span data-ttu-id="aeb97-145">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="aeb97-145">For example:</span></span>
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - <span data-ttu-id="aeb97-146">Infine, riconfigurare le impostazioni del parcheggio di chiamata nel pool C utilizzando il cmdlet **Set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="aeb97-146">Finally, reconfigure the Call Park settings on pool C by using the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="aeb97-147">L'applicazione Parcheggio di chiamata è in grado di archiviare un solo set di impostazioni e un file audio di musica di attesa personalizzato per pool e tali impostazioni non vengono sottoposte a backup o conservate in caso di emergenza.</span><span class="sxs-lookup"><span data-stu-id="aeb97-147">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool, and these settings are not backed up or preserved in the event of a disaster.</span></span>

15. <span data-ttu-id="aeb97-148">Se il pool hop successivo per la chat persistente punta al pool A, creare e pubblicare le modifiche della topologia in modo che il server dell'hop successivo punti al pool C.</span><span class="sxs-lookup"><span data-stu-id="aeb97-148">If the next hop pool for Persistent Chat is pointing to pool A, make and publish topology changes so that the next hop server points to pool C.</span></span>
    
      - <span data-ttu-id="aeb97-149">In Generatore di topologie, impostare il pool di chat persistente in modo che punti al pool C come hop successivo.</span><span class="sxs-lookup"><span data-stu-id="aeb97-149">In Topology Builder, change the Persistent Chat pool to point to Pool C as its next hop.</span></span> <span data-ttu-id="aeb97-150">A tale scopo, fare clic con il pulsante destro del mouse sul pool di chat persistente, quindi fare clic sulla scheda **generale** e quindi digitare il nome del pool C nel **pool di hop successivo**.</span><span class="sxs-lookup"><span data-stu-id="aeb97-150">To do so, right-click on the Persistent Chat pool, then click the **General** tab, and then type the name of Pool C in **Next Hop Pool**.</span></span>
    
      - <span data-ttu-id="aeb97-151">Avviare i servizi nel pool C eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="aeb97-151">Start services on pool C by running the following cmdlet:</span></span>
        
            Start-csWindowsService
    
    <span data-ttu-id="aeb97-152">A questo punto, l'interruzione del servizio termina per gli utenti originariamente ospitati nel pool A.</span><span class="sxs-lookup"><span data-stu-id="aeb97-152">At this point, the service outage ends for users originally homed on pool A.</span></span>

16. <span data-ttu-id="aeb97-153">Esportare i flussi di lavoro di servizio di Response Group di Lync Server dal pool B di proprietà del pool A per l'importazione nel pool C eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="aeb97-153">Export Lync Server Response Group service workflows from pool B owned by pool A for import into pool C by running the following cmdlet:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. <span data-ttu-id="aeb97-154">Importare i flussi di lavoro di servizio di Response Group di Lync Server nel pool C dal pool B.</span><span class="sxs-lookup"><span data-stu-id="aeb97-154">Import Lync Server Response Group service workflows into pool C from pool B.</span></span>
    
    <span data-ttu-id="aeb97-155">Sono disponibili due opzioni per l'importazione della configurazione di Response Group dal pool B al pool C. L'opzione utilizzata varia a seconda che si desideri sovrascrivere le impostazioni a livello di applicazione del pool C con le impostazioni a livello di applicazione nel pool B.</span><span class="sxs-lookup"><span data-stu-id="aeb97-155">You have two options are for importing the Response Group configuration from pool B to pool C. Which option you use depends on whether you want to overwrite the application-level settings of pool C with the application-level settings in pool B.</span></span>
    
      - <span data-ttu-id="aeb97-156">Se si desidera sovrascrivere le impostazioni del pool C, eseguire il cmdlet **Import-CsRgsConfiguration** con l'opzione **ReplaceExistingSettings** :</span><span class="sxs-lookup"><span data-stu-id="aeb97-156">If you want to overwrite the Pool C settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="aeb97-157">Se non si desidera sovrascrivere le impostazioni del pool C, utilizzare il cmdlet **Import-CsRgsConfiguration** senza l'opzione **ReplaceExistingSettings** .</span><span class="sxs-lookup"><span data-stu-id="aeb97-157">If you do not want to overwrite the Pool C settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="aeb97-158">Tenere presente che se non si desidera sovrascrivere le impostazioni a livello di applicazione del pool C con le impostazioni del pool di backup (pool B), le impostazioni a livello di applicazione del pool B andranno perse perché l'applicazione Response Group può archiviare solo un set di applicazioni a livello di applicazione. impostazioni per pool.</span><span class="sxs-lookup"><span data-stu-id="aeb97-158">Keep in mind that if you do not want to overwrite the application-level settings of Pool C with the settings of the backup pool (pool B), pool B’s application-level settings will be lost because the Response Group application can store only one set of application-level settings per pool.</span></span>

    
    </div>

18. <span data-ttu-id="aeb97-159">Verificare che l'importazione della configurazione di Response Group abbia avuto esito positivo eseguendo i cmdlet seguenti per visualizzare i Response Group che sono stati importati nel pool C.</span><span class="sxs-lookup"><span data-stu-id="aeb97-159">Verify that the Response Group configuration import was successful by running the following cmdlets to display the response groups that have been imported to Pool C.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. <span data-ttu-id="aeb97-160">Quando la configurazione importata è stata verificata nel pool C, rimuovere i Response Group di proprietà del pool primario dal pool B. Questo consente di ridurre al minimo i tempi di inattività dei Response Group.</span><span class="sxs-lookup"><span data-stu-id="aeb97-160">When the imported configuration has been verified in pool C, remove the response groups owned by the primary pool from pool B. This will minimize the downtime of the response groups.</span></span>
    
    <span data-ttu-id="aeb97-161">Questo passaggio consente di creare un nuovo file con la configurazione esportata e quindi di rimuovere il file dal pool B.</span><span class="sxs-lookup"><span data-stu-id="aeb97-161">This step creates a new file with the exported configuration, and then removes the file from pool B.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. <span data-ttu-id="aeb97-162">Sposta nel pool C gli intervalli di numeri non assegnati spostati dal pool A al pool B.</span><span class="sxs-lookup"><span data-stu-id="aeb97-162">Move to pool C the Unassigned Number ranges that were moved from pool A to pool B.</span></span>
    
      - <span data-ttu-id="aeb97-163">Ricreare nel pool C tutti gli annunci che sono stati ricreati dal pool A nel pool B. Se i file audio sono stati utilizzati durante la distribuzione degli annunci da spostare, sarà necessario utilizzare questi file per ricreare gli annunci nel pool C. Per ricreare gli annunci nel pool C, utilizzare i cmdlet **New-CsAnnouncement** , con pool c come servizio padre.</span><span class="sxs-lookup"><span data-stu-id="aeb97-163">Re-create in pool C all announcements that were re-created from pool A in pool B. If any audio files were used when deploying the announcements to be moved, you will need to use these files to re-create the announcements in pool C. To re-create the announcements in pool C, use the **New-CsAnnouncement** cmdlets, with pool C as the Parent service.</span></span>
    
      - <span data-ttu-id="aeb97-164">Reindirizzare al pool C tutti gli intervalli di numeri non assegnati che sono stati ridestinati dal pool A al pool B. eseguire il cmdlet seguente per ogni intervallo di numeri non assegnati che deve essere reindirizzato:</span><span class="sxs-lookup"><span data-stu-id="aeb97-164">Retarget to pool C all the unassigned number ranges that were retargeted from pool A to pool B. Run the following cmdlet for every Unassigned Number range that needs to be retargeted:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - <span data-ttu-id="aeb97-165">Optional Rimuovi dal pool B gli annunci che sono stati ricreati nel pool C se non sono più in uso nel pool B. Per rimuovere gli annunci, utilizzare il cmdlet **Remove-CsAnnouncement** .</span><span class="sxs-lookup"><span data-stu-id="aeb97-165">(Optional) Remove from pool B the announcements that were re-created in pool C if they are no longer in use in pool B. To remove announcements, use the **Remove-CsAnnouncement** cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="aeb97-166">Questo passaggio non è necessario per gli intervalli di numeri non assegnati che utilizzano "messaggistica unificata di Exchange" come servizio annuncio.</span><span class="sxs-lookup"><span data-stu-id="aeb97-166">This step is not required for unassigned number ranges that use "Exchange UM" as the announcement service.</span></span>

        
        </div>

21. <span data-ttu-id="aeb97-167">Pulire i dati degli utenti del pool A nel pool B eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="aeb97-167">Clean up user data of pool A in pool B by running the following cmdlet:</span></span>
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. <span data-ttu-id="aeb97-168">Eseguire le operazioni seguenti in Generatore di topologie:</span><span class="sxs-lookup"><span data-stu-id="aeb97-168">Do the following in Topology Builder:</span></span>
    
      - <span data-ttu-id="aeb97-169">Dispair pool A e pool B. coppia pool B e pool C. Quindi rimuovere il pool A dalla topologia e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="aeb97-169">Unpair pool A and pool B. Pair pool B and pool C. Then remove Pool A from the topology and publish it.</span></span> <span data-ttu-id="aeb97-170">A questo scopo:</span><span class="sxs-lookup"><span data-stu-id="aeb97-170">To do so:</span></span>
        
          - <span data-ttu-id="aeb97-171">In Generatore di topologie fare clic con il pulsante destro del mouse sul pool B e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="aeb97-171">In Topology Builder, right-click on Pool B, and then click **Edit Properties**.</span></span>
        
          - <span data-ttu-id="aeb97-172">Fare clic su **resilienza** nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="aeb97-172">Click **Resiliency** in the left pane.</span></span>
        
          - <span data-ttu-id="aeb97-173">Nella casella al di sotto del **pool di backup associato**selezionare Pool C. tenere presente che la casella di selezione del pool di backup associato visualizzerà inizialmente il pool A, perché il pool B è stato precedentemente associato al pool.</span><span class="sxs-lookup"><span data-stu-id="aeb97-173">In the box below **Associated Backup Pool**, select Pool C. Note that the Associated Backup Pool selection box will initially display pool A, because pool B was previously associated with this pool.</span></span>
        
          - <span data-ttu-id="aeb97-174">Selezionare **Failover e failback automatico per VoIP** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="aeb97-174">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
            
            <span data-ttu-id="aeb97-175">Quando vengono visualizzati i dettagli su questo pool, il pool associato apparirà nel riquadro a destra sotto **Resilienza**.</span><span class="sxs-lookup"><span data-stu-id="aeb97-175">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>
        
          - <span data-ttu-id="aeb97-176">Nell'albero della console fare clic con il pulsante destro del mouse su pool A e quindi scegliere Elimina.</span><span class="sxs-lookup"><span data-stu-id="aeb97-176">In the console tree, right-click pool A, and then click Delete.</span></span>
        
          - <span data-ttu-id="aeb97-177">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="aeb97-177">Publish the topology.</span></span>

23. <span data-ttu-id="aeb97-178">Eseguire l'applicazione di avvio automatico nel pool C per installare l'applicazione del servizio di backup e quindi avviare l'applicazione del servizio di backup eseguendo la seguente procedura dalla cartella di distribuzione di un computer locale nel pool C:</span><span class="sxs-lookup"><span data-stu-id="aeb97-178">Run the bootstrapping application on pool C to install the backup service application, and then start the backup service application by running the following from the deployment folder on a local machine in pool C:</span></span>
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. <span data-ttu-id="aeb97-179">Riavviare l'applicazione del servizio di backup nel pool B eseguendo i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="aeb97-179">Restart the backup service application on pool B by running the following cmdlets:</span></span>
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. <span data-ttu-id="aeb97-180">Se pool C è un pool Standard Edition (SE) e il pool B ha CMS, installare il database CMS manualmente sul pool C eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="aeb97-180">If pool C is a Standard Edition (SE) Pool and pool B has CMS, install the CMS database manually on pool C by running the following cmdlet:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. <span data-ttu-id="aeb97-181">Richiamare il servizio di backup per sincronizzare il contenuto delle conferenze obsolete dal pool B al pool C generato prima di associare insieme B e C e sincronizzare il nuovo contenuto delle conferenze dal pool C al pool B che è stato generato dopo l'avvio del pool C e prima che B e C siano stati accoppiati.</span><span class="sxs-lookup"><span data-stu-id="aeb97-181">Invoke the backup service to sync old conferencing content from pool B to pool C that was generated before pairing B and C together, and to sync new conferencing content from pool C to pool B that was generated after starting pool C and before B and C were paired together.</span></span> <span data-ttu-id="aeb97-182">A tale scopo, eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="aeb97-182">To do so, run the following cmdlets:</span></span>
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. <span data-ttu-id="aeb97-183">Per ogni Survivable Branch Appliance X associata al pool A:</span><span class="sxs-lookup"><span data-stu-id="aeb97-183">For each Survivable Branch Appliance X associated with pool A:</span></span>
    
      - <span data-ttu-id="aeb97-184">Arrestare SBA X eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="aeb97-184">Shut down SBA X by running the following cmdlet:</span></span>
        
            Stop-CsWindowsService
    
      - <span data-ttu-id="aeb97-185">Creare un file contenente un elenco di utenti ospitati in SBA X. L'elenco sarà necessario quando gli utenti vengono spostati di nuovo su SBA X nel passaggio 30.</span><span class="sxs-lookup"><span data-stu-id="aeb97-185">Create a file that contains a list of users homed on SBA X. The list will be needed when the users are moved back to SBA X in step 30.</span></span> <span data-ttu-id="aeb97-186">A tale scopo, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="aeb97-186">To do so, run the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - <span data-ttu-id="aeb97-187">Forzare gli utenti ospitati in SBA X a passare al pool C eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="aeb97-187">Force users homed on SBA X to move to pool C by running the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - <span data-ttu-id="aeb97-188">Aggiornare i dati di tali utenti eseguendo innanzitutto i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="aeb97-188">Update the data of these users by first running the following cmdlets:</span></span>
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        <span data-ttu-id="aeb97-189">E quindi Esegui questo script:</span><span class="sxs-lookup"><span data-stu-id="aeb97-189">And then run this script:</span></span>
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="aeb97-190">Si verificherà un'interruzione del servizio per gli utenti che si trovano in SBA associati al pool A fino allo spostamento di tali utenti nel pool C.</span><span class="sxs-lookup"><span data-stu-id="aeb97-190">A service outage will occur for users who are homed on SBAs that are associated with pool A until these users are moved to pool C.</span></span>

        
        </div>

28. <span data-ttu-id="aeb97-191">In Generatore di topologie, per ogni SBA X precedentemente associato al pool A, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aeb97-191">In Topology Builder, for each SBA X previously associated with Pool A, do the following:</span></span>
    
      - <span data-ttu-id="aeb97-192">Modificare l'associazione nel pool C. A tale scopo, fare clic sul sito di succursale, espandere il nodo Survivable Branch Appliances or Servers e fare clic su **Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="aeb97-192">Change the association to Pool C. To do so, click the branch site, expand the Survivable Branch Appliances or Servers node, and click **Survivable Branch Appliance**.</span></span> <span data-ttu-id="aeb97-193">Quindi selezionare il pool **front end, il pool di servizi utente** a cui si connetterà il Survivable Branch Appliance come pool C e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aeb97-193">Then select the **Front End pool, User Services Pool** that this Survivable Branch Appliance will connect to as Pool C, and then click **Next**.</span></span>
    
      - <span data-ttu-id="aeb97-194">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="aeb97-194">Publish the topology.</span></span> <span data-ttu-id="aeb97-195">A tale scopo, nell'albero della console fare clic con il pulsante destro del mouse sul nuovo **Survivable Branch Appliance**, scegliere **topologia**e quindi fare clic su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="aeb97-195">To do so, in the console tree, right-click the new **Survivable Branch Appliance**, click **Topology**, and then click **Publish**.</span></span>

29. <span data-ttu-id="aeb97-196">Per ogni SBA X ora associato al pool C:</span><span class="sxs-lookup"><span data-stu-id="aeb97-196">For each SBA X now associated with pool C:</span></span>
    
      - <span data-ttu-id="aeb97-197">Avviare SBA X eseguendo il cmdlet seguente nel Survivable Branch Appliance:</span><span class="sxs-lookup"><span data-stu-id="aeb97-197">Start SBA X by running the following cmdlet on the survivable branch appliance:</span></span>
        
            Start-CsWindowsService
    
      - <span data-ttu-id="aeb97-198">Spostare gli utenti originariamente ospitati in SBA X dal pool C a SBA X eseguendo il cmdlet seguente.</span><span class="sxs-lookup"><span data-stu-id="aeb97-198">Move users who were originally homed on SBA X from pool C to SBA X by running the following cmdlet.</span></span>
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

