---
title: Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Riepilogo: leggere questo argomento per informazioni su come configurare la disponibilità elevata e il ripristino di emergenza per il server di chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: a1589dbb22b3737cab1957637b98477502445958
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798263"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="10a60-103">Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="10a60-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="10a60-104">**Riepilogo:** Leggere questo argomento per informazioni su come configurare la disponibilità elevata e il ripristino di emergenza per il server di chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="10a60-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="10a60-105">Skype for Business Server supporta più modalità di elevata disponibilità per i server back-end, incluso il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="10a60-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="10a60-106">Per altre informazioni, vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="10a60-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="10a60-107">I gruppi di disponibilità AlwaysOn non sono supportati con i server di chat permanenti.</span><span class="sxs-lookup"><span data-stu-id="10a60-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="10a60-108">Prima di configurare la distribuzione della chat persistente per l'elevata disponibilità e il ripristino di emergenza, assicurarsi di avere familiarità con i concetti in [piano per l'elevata disponibilità e il ripristino di emergenza per il server di chat persistente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="10a60-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="10a60-109">La soluzione di ripristino di emergenza per il server di chat persistente descritta in questi argomenti si basa su un pool di server di chat persistente allungato.</span><span class="sxs-lookup"><span data-stu-id="10a60-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="10a60-110">Il contenuto della pianificazione descrive i requisiti delle risorse e la topologia del pool allungata che consente la disponibilità elevata e il ripristino di emergenza per il server di chat persistente, incluso l'uso del mirroring di SQL Server per l'elevata disponibilità e la distribuzione del log ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="10a60-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="10a60-111">Usare generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="10a60-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="10a60-112">In Generatore di topologie eseguire la procedura seguente per configurare l'elevata disponibilità e il ripristino di emergenza per il server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="10a60-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="10a60-113">Aggiungere i database mirror e il database secondario del log shipping di SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="10a60-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="10a60-114">Modificare le proprietà del servizio server di chat persistente in:</span><span class="sxs-lookup"><span data-stu-id="10a60-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="10a60-115">un.</span><span class="sxs-lookup"><span data-stu-id="10a60-115">a.</span></span> <span data-ttu-id="10a60-116">Abilitare il mirroring per il database primario.</span><span class="sxs-lookup"><span data-stu-id="10a60-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="10a60-117">b.</span><span class="sxs-lookup"><span data-stu-id="10a60-117">b.</span></span> <span data-ttu-id="10a60-118">Aggiungere il mirror principale di SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="10a60-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="10a60-119">c.</span><span class="sxs-lookup"><span data-stu-id="10a60-119">c.</span></span> <span data-ttu-id="10a60-120">Abilitare il database di log shipping di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="10a60-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="10a60-121">3D.</span><span class="sxs-lookup"><span data-stu-id="10a60-121">d.</span></span> <span data-ttu-id="10a60-122">Aggiungere l'archivio SQL Server log shipping secondario di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="10a60-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="10a60-123">e.</span><span class="sxs-lookup"><span data-stu-id="10a60-123">e.</span></span> <span data-ttu-id="10a60-124">Aggiungere il mirror di SQL Server Store per il database secondario.</span><span class="sxs-lookup"><span data-stu-id="10a60-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="10a60-125">f.</span><span class="sxs-lookup"><span data-stu-id="10a60-125">f.</span></span> <span data-ttu-id="10a60-126">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="10a60-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="10a60-127">Configurare la distribuzione del log di SQL Server per il database primario del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="10a60-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="10a60-128">In SQL Server Management Studio connettersi all'istanza del database di log shipping secondario del server di chat persistente e verificare che SQL Server Agent sia in uso.</span><span class="sxs-lookup"><span data-stu-id="10a60-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="10a60-129">Quindi Connetti all'istanza del database primario della chat persistente ed Esegui i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="10a60-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="10a60-130">Fare clic con il pulsante destro del mouse sul database di MGC e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="10a60-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="10a60-131">In **selezionare una pagina**fare clic su **distribuzione log transazioni**.</span><span class="sxs-lookup"><span data-stu-id="10a60-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="10a60-132">Selezionare la casella **di controllo Abilita come database primario in una configurazione di distribuzione del log** .</span><span class="sxs-lookup"><span data-stu-id="10a60-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="10a60-133">In **backup del log delle transazioni**fare clic su **impostazioni di backup**.</span><span class="sxs-lookup"><span data-stu-id="10a60-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="10a60-134">Nella casella **percorso di rete della cartella di backup** Digitare il percorso di rete della condivisione creata per la cartella di backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="10a60-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="10a60-135">Se la cartella di backup si trova nel server principale, digitare il percorso locale della cartella di backup nella casella **se la cartella di backup si trova nel server principale, digitare un percorso locale alla cartella (esempio: c:\backup)** .</span><span class="sxs-lookup"><span data-stu-id="10a60-135">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box.</span></span> <span data-ttu-id="10a60-136">Se la cartella di backup non si trova nel server principale, è possibile lasciarla vuota.</span><span class="sxs-lookup"><span data-stu-id="10a60-136">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="10a60-137">Se l'account del servizio SQL Server nel server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server principale e specificare un percorso locale per la cartella.</span><span class="sxs-lookup"><span data-stu-id="10a60-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="10a60-138">Configurare i **file di eliminazione più vecchi e di** **avviso se non si verifica alcun backup all'interno** dei parametri.</span><span class="sxs-lookup"><span data-stu-id="10a60-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="10a60-139">Esaminare la pianificazione del backup elencata nella casella **pianificazione** in **processo di backup**.</span><span class="sxs-lookup"><span data-stu-id="10a60-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="10a60-140">Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**e regolare la pianificazione di SQL Server Agent in modo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="10a60-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="10a60-141">In **compressione**selezionare **Usa l'impostazione predefinita del server**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="10a60-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="10a60-142">In **istanze server secondarie e database**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="10a60-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="10a60-143">Fare clic su **Connetti** e Connetti all'istanza di SQL Server configurata come server secondario.</span><span class="sxs-lookup"><span data-stu-id="10a60-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="10a60-144">Nella casella **database secondario** selezionare il database **MGC** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="10a60-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="10a60-145">Nella scheda **Inizializza database secondario** scegliere l'opzione **Sì, generare un backup completo del database principale e ripristinarlo nel database secondario (e creare il database secondario se non esiste)**.</span><span class="sxs-lookup"><span data-stu-id="10a60-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="10a60-146">Nella casella **cartella di destinazione per i file copiati** della scheda **copia file** Digitare il percorso della cartella in cui devono essere copiati i backup dei log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="10a60-146">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="10a60-147">Questa cartella si trova spesso nel server secondario.</span><span class="sxs-lookup"><span data-stu-id="10a60-147">This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="10a60-148">Nota la pianificazione della copia elencata nella casella **pianificazione** in **copia processo**.</span><span class="sxs-lookup"><span data-stu-id="10a60-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="10a60-149">Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**e regolare la pianificazione di SQL Server Agent in modo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="10a60-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="10a60-150">Questa programmazione deve essere approssimativamente uguale alla programmazione di backup.</span><span class="sxs-lookup"><span data-stu-id="10a60-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="10a60-151">Nella scheda **Ripristina** , in **stato del database durante il ripristino dei backup**, scegliere l'opzione **Nessuna modalità di recupero** .</span><span class="sxs-lookup"><span data-stu-id="10a60-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="10a60-152">In **delay Restoring backups almeno:** selezionare **0 minuti**.</span><span class="sxs-lookup"><span data-stu-id="10a60-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="10a60-153">Scegliere una soglia di avviso in **avviso se non si verifica alcun ripristino all'interno**.</span><span class="sxs-lookup"><span data-stu-id="10a60-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="10a60-154">Esaminare la pianificazione di ripristino elencata nella casella **pianificazione** in **Ripristina processo**.</span><span class="sxs-lookup"><span data-stu-id="10a60-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="10a60-155">Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**, regolare la pianificazione di SQL Server Agent come richiesto e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="10a60-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="10a60-156">Questa programmazione deve essere approssimativamente uguale alla programmazione di backup.</span><span class="sxs-lookup"><span data-stu-id="10a60-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="10a60-157">Nella finestra di dialogo **Proprietà database** fare clic su **OK** per avviare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="10a60-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="10a60-158">Configurare la distribuzione del log di SQL Server tra lo specchio principale e il database secondario</span><span class="sxs-lookup"><span data-stu-id="10a60-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="10a60-159">Eseguire la procedura seguente per continuare il log shipping se il database principale della chat persistente non viene superato nel database mirror.</span><span class="sxs-lookup"><span data-stu-id="10a60-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="10a60-160">Eseguire manualmente il failover del database principale della chat persistente in mirror.</span><span class="sxs-lookup"><span data-stu-id="10a60-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="10a60-161">Questa operazione viene eseguita usando Skype for Business Server Management Shell e il cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="10a60-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="10a60-162">In SQL Server Management Studio connettersi all'istanza del mirror del server di chat persistente principale.</span><span class="sxs-lookup"><span data-stu-id="10a60-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="10a60-163">Verificare che l'agente SQL Server sia in uso.</span><span class="sxs-lookup"><span data-stu-id="10a60-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="10a60-164">Fare clic con il pulsante destro del mouse sul database di MGC e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="10a60-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="10a60-165">In **selezionare una pagina**fare clic su **distribuzione log transazioni**.</span><span class="sxs-lookup"><span data-stu-id="10a60-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="10a60-166">Selezionare la casella **di controllo Abilita come database primario in una configurazione di distribuzione del log** .</span><span class="sxs-lookup"><span data-stu-id="10a60-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="10a60-167">In **backup del log delle transazioni**fare clic su **impostazioni di backup**.</span><span class="sxs-lookup"><span data-stu-id="10a60-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="10a60-168">Nella casella **percorso di rete della cartella di backup** Digitare il percorso di rete della condivisione creata per la cartella di backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="10a60-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="10a60-169">Se la cartella di backup si trova nel server principale, digitare il percorso locale della cartella di backup nella finestra di dialogo **se la cartella di backup si trova nel server principale, digitare un percorso locale nella casella della cartella** .</span><span class="sxs-lookup"><span data-stu-id="10a60-169">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="10a60-170">Se la cartella di backup non si trova nel server principale, è possibile lasciarla vuota.</span><span class="sxs-lookup"><span data-stu-id="10a60-170">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="10a60-171">Se l'account del servizio SQL Server nel server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server principale e specificare un percorso locale per la cartella.</span><span class="sxs-lookup"><span data-stu-id="10a60-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="10a60-172">Configurare i **file di eliminazione più vecchi e di** **avviso se non si verifica alcun backup all'interno** dei parametri.</span><span class="sxs-lookup"><span data-stu-id="10a60-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="10a60-173">Esaminare la pianificazione del backup elencata nella casella **pianificazione** in **processo di backup**.</span><span class="sxs-lookup"><span data-stu-id="10a60-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="10a60-174">Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**e regolare la pianificazione di SQL Server Agent, se necessario.</span><span class="sxs-lookup"><span data-stu-id="10a60-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="10a60-175">Usa le stesse impostazioni usate per il database primario.</span><span class="sxs-lookup"><span data-stu-id="10a60-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="10a60-176">In **compressione**selezionare **Usa l'impostazione predefinita del server**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="10a60-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="10a60-177">In **istanze server secondarie e database**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="10a60-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="10a60-178">Fare clic su **Connetti**e connettersi all'istanza di SQL Server configurata come server secondario.</span><span class="sxs-lookup"><span data-stu-id="10a60-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="10a60-179">Nella casella **database secondario** selezionare il database **MGC** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="10a60-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="10a60-180">Nella scheda **Inizializza database secondario** selezionare l'opzione **No, il database secondario viene inizializzato**.</span><span class="sxs-lookup"><span data-stu-id="10a60-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="10a60-181">Nella scheda **copia file** , nella **cartella di destinazione per i file copiati**, digitare il percorso della cartella in cui devono essere copiati i backup dei log delle transazioni e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="10a60-181">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**.</span></span> <span data-ttu-id="10a60-182">Questa cartella si trova spesso nel server secondario.</span><span class="sxs-lookup"><span data-stu-id="10a60-182">This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="10a60-183">Aprire l'elenco a discesa **configurazione script** e selezionare **configurazione script nella finestra nuova query**.</span><span class="sxs-lookup"><span data-stu-id="10a60-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="10a60-184">Nella finestra nuova query, in **Proprietà database**, fare clic su **OK** per avviare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="10a60-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="10a60-185">Selezionare ed eseguire la prima metà della query (vedere il passaggio 18) fino alla riga:-- \* \* \* \* \* \* end: script da eseguire \* \* \* \* \* \*in primo piano:.</span><span class="sxs-lookup"><span data-stu-id="10a60-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="10a60-186">L'esecuzione manuale di questo script è necessaria perché in SQL Server Management Studio non è supportato più database primari in una configurazione di log shipping di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="10a60-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="10a60-187">Selezionare **Annulla** per chiudere il pannello di configurazione del file di log shipping e stabilire una configurazione di lavoro che implementi correttamente la spedizione del file di log sia per il database primario che per il mirroring (in caso di failover).</span><span class="sxs-lookup"><span data-stu-id="10a60-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="10a60-188">Non eseguire manualmente il backup del database principale della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="10a60-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="10a60-189">Questa operazione viene eseguita usando Skype for Business Server Management Shell e il cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="10a60-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

