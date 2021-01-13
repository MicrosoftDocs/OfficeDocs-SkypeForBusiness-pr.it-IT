---
title: Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Riepilogo: leggere questo argomento per informazioni su come configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 10d9e2eb76873cedc82daea817a732b8feb379da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802136"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="b6d7f-103">Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b6d7f-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b6d7f-104">**Riepilogo:** Leggere questo argomento per informazioni su come configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b6d7f-105">Skype for Business Server supporta più modalità di disponibilità elevata per i server back-end, incluso il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="b6d7f-106">Per ulteriori informazioni, vedere [pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="b6d7f-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6d7f-107">I gruppi di disponibilità AlwaysOn non sono supportati con i server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 

> [!NOTE] 
> <span data-ttu-id="b6d7f-108">La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b6d7f-109">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="b6d7f-110">Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="b6d7f-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="b6d7f-111">Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b6d7f-112">Prima di configurare la distribuzione di chat persistente per la disponibilità elevata e il ripristino di emergenza, accertarsi di conoscere i concetti in [piano per la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="b6d7f-112">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="b6d7f-113">La soluzione di ripristino di emergenza per il server Chat persistente descritta in questi argomenti è basata su un pool di server Chat persistente esteso.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-113">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="b6d7f-114">Il contenuto di pianificazione descrive i requisiti delle risorse e la topologia del pool esteso che consente la disponibilità elevata e il ripristino di emergenza per il server Chat persistente, incluso l'utilizzo del mirroring di SQL Server per la disponibilità elevata e il log shipping di SQL Server per il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-114">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="b6d7f-115">Utilizzo di generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="b6d7f-115">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="b6d7f-116">All'interno di generatore di topologie, eseguire la procedura seguente per configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-116">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="b6d7f-117">Aggiungere i database mirror e gli archivi SQL Server del database secondario di log shipping.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-117">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="b6d7f-118">Modificare le proprietà del servizio del server Chat persistente in:</span><span class="sxs-lookup"><span data-stu-id="b6d7f-118">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="b6d7f-119">a.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-119">a.</span></span> <span data-ttu-id="b6d7f-120">Abilitare il mirroring per il database primario.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-120">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="b6d7f-121">b.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-121">b.</span></span> <span data-ttu-id="b6d7f-122">Aggiungere l'archivio SQL Server mirror primario.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-122">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="b6d7f-123">c.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-123">c.</span></span> <span data-ttu-id="b6d7f-124">Abilitare il database di log shipping di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-124">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="b6d7f-125">d.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-125">d.</span></span> <span data-ttu-id="b6d7f-126">Aggiungere l'archivio SQL Server secondario di log shipping di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-126">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="b6d7f-127">e.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-127">e.</span></span> <span data-ttu-id="b6d7f-128">Aggiungere il mirror dell'archivio SQL Server per il database secondario.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-128">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="b6d7f-129">f.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-129">f.</span></span> <span data-ttu-id="b6d7f-130">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-130">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="b6d7f-131">Configurare il log shipping di SQL Server per il database primario del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="b6d7f-131">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="b6d7f-132">Se si utilizza SQL Server Management Studio, connettersi all'istanza del database secondario di log shipping del server di chat persistente e verificare che SQL Server Agent sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-132">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="b6d7f-133">Connettersi quindi all'istanza del database primario di Persistent Chat ed eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6d7f-133">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="b6d7f-134">Fare clic con il pulsante destro del mouse sul database mgc e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-134">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="b6d7f-135">In **Seleziona una pagina** fare clic su **log shipping delle transazioni**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-135">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="b6d7f-136">Selezionare la casella **di controllo Abilita come database primario in una configurazione per il log shipping** .</span><span class="sxs-lookup"><span data-stu-id="b6d7f-136">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="b6d7f-137">In **backup dei log delle transazioni** fare clic su **impostazioni di backup**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-137">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="b6d7f-138">Nella casella **percorso di rete della cartella di backup** Digitare il percorso di rete della condivisione creata per la cartella di backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-138">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="b6d7f-139">Se la cartella di backup si trova sul server primario, digitare il percorso locale della cartella di backup nella casella **se la cartella di backup si trova sul server primario, digitare un percorso locale per la cartella (ad esempio: c:\backup)** .</span><span class="sxs-lookup"><span data-stu-id="b6d7f-139">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box.</span></span> <span data-ttu-id="b6d7f-140">Se la cartella di backup non è presente nel server primario, è possibile lasciare vuota questa casella.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-140">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b6d7f-141">Se l'account di servizio di SQL Server nel server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server primario e specificare un percorso locale per tale cartella.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-141">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="b6d7f-142">Configurare i **file di eliminazione precedenti e di** **avviso se nessun backup viene eseguito all'interno** dei parametri.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-142">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="b6d7f-143">Esaminare la pianificazione di backup elencata nella casella **pianificazione** in **processo di backup**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-143">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="b6d7f-144">Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione** e modificare la pianificazione di SQL Server Agent in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-144">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="b6d7f-145">In **compressione** selezionare **utilizza l'impostazione predefinita del server** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-145">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="b6d7f-146">In **istanze e database secondari del server**, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-146">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="b6d7f-147">Fare clic su **Connetti** e connettersi all'istanza di SQL Server configurata come server secondario.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-147">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="b6d7f-148">Nella casella **database secondario** selezionare il database di **MGC** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-148">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="b6d7f-149">Nella scheda **Inizializza database secondario** selezionare l'opzione **Sì, generare un backup completo del database primario e ripristinarlo nel database secondario (e creare il database secondario se non esiste)**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-149">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="b6d7f-150">Nella casella **cartella di destinazione per i file copiati** della scheda **copia file** Digitare il percorso della cartella in cui devono essere copiati i backup dei registri delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-150">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="b6d7f-151">Questa cartella si trova spesso nel server secondario.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-151">This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="b6d7f-152">Tenere presente la pianificazione della copia elencata nella casella **pianificazione** in **copia processo**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-152">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="b6d7f-153">Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione** e modificare la pianificazione di SQL Server Agent in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-153">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="b6d7f-154">Questa pianificazione deve essere approssimativamente uguale alla pianificazione del backup.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-154">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="b6d7f-155">Nella scheda **Ripristina** , in **stato di database durante il ripristino dei backup**, scegliere l'opzione **modalità No Recovery** .</span><span class="sxs-lookup"><span data-stu-id="b6d7f-155">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="b6d7f-156">In **delay Restoring backups almeno:**, selezionare **0 minuti**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-156">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="b6d7f-157">Scegliere una soglia di avviso in **avviso se non si verifica alcun ripristino all'interno**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-157">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="b6d7f-158">Esaminare la pianificazione di ripristino elencata nella casella **pianificazione** in **Ripristina processo**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-158">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="b6d7f-159">Per personalizzare la pianificazione dell'installazione, fare clic su **pianificazione**, modificare la pianificazione di SQL Server Agent in base alle esigenze e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-159">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="b6d7f-160">Questa pianificazione deve essere approssimativamente uguale alla pianificazione del backup.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-160">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="b6d7f-161">Nella finestra di dialogo **Proprietà database** fare clic su **OK** per avviare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-161">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="b6d7f-162">Configurare il log shipping di SQL Server tra il mirror primario e il database secondario</span><span class="sxs-lookup"><span data-stu-id="b6d7f-162">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="b6d7f-163">Eseguire la procedura seguente per continuare il log shipping se il database di Persistent Chat primario non viene eseguito nel database mirror.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-163">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="b6d7f-164">Eseguire manualmente il failover del database di Persistent Chat principale nel mirror.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-164">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="b6d7f-165">A tale scopo, è possibile utilizzare Skype for Business Server Management Shell e il cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="b6d7f-165">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="b6d7f-166">Se si utilizza SQL Server Management Studio, connettersi all'istanza del mirror del server di Persistent Chat principale.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-166">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="b6d7f-167">Verificare che SQL Server Agent sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-167">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="b6d7f-168">Fare clic con il pulsante destro del mouse sul database mgc e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-168">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="b6d7f-169">In **Seleziona una pagina** fare clic su **log shipping delle transazioni**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-169">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="b6d7f-170">Selezionare la casella **di controllo Abilita come database primario in una configurazione per il log shipping** .</span><span class="sxs-lookup"><span data-stu-id="b6d7f-170">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="b6d7f-171">In **backup dei log delle transazioni** fare clic su **impostazioni di backup**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-171">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="b6d7f-172">Nella casella **percorso di rete della cartella di backup** Digitare il percorso di rete della condivisione creata per la cartella di backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-172">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="b6d7f-173">Se la cartella di backup si trova sul server primario, digitare il percorso locale della cartella di backup nella casella **se la cartella di backup si trova sul server primario, digitare il percorso locale della cartella** .</span><span class="sxs-lookup"><span data-stu-id="b6d7f-173">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="b6d7f-174">Se la cartella di backup non è presente nel server primario, è possibile lasciare vuota questa casella.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-174">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b6d7f-175">Se l'account di servizio di SQL Server nel server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server primario e specificare un percorso locale per tale cartella.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-175">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="b6d7f-176">Configurare i **file di eliminazione precedenti e di** **avviso se nessun backup viene eseguito all'interno** dei parametri.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-176">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="b6d7f-177">Esaminare la pianificazione di backup elencata nella casella **pianificazione** in **processo di backup**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-177">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="b6d7f-178">Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione** e modificare la pianificazione di SQL Server Agent, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-178">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b6d7f-179">Utilizzare le stesse impostazioni utilizzate per il database primario.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-179">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="b6d7f-180">In **compressione** selezionare **utilizza l'impostazione predefinita del server** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-180">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="b6d7f-181">In **istanze e database secondari del server**, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-181">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="b6d7f-182">Fare clic su **Connetti** e connettersi all'istanza di SQL Server configurata come server secondario.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-182">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="b6d7f-183">Nella casella **database secondario** selezionare il database di **MGC** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-183">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="b6d7f-184">Nella scheda **Inizializza database secondario** selezionare l'opzione **No, il database secondario viene inizializzato**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-184">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="b6d7f-185">Nella scheda **copia file** , nella **cartella di destinazione per i file copiati**, digitare il percorso della cartella in cui devono essere copiati i backup dei registri delle transazioni e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-185">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**.</span></span> <span data-ttu-id="b6d7f-186">Questa cartella si trova spesso nel server secondario.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-186">This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="b6d7f-187">Aprire l'elenco a discesa **configurazione script** e selezionare **configurazione script nella nuova finestra di query**.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-187">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="b6d7f-188">Nella finestra nuova query, in **Proprietà database**, fare clic su **OK** per avviare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-188">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="b6d7f-189">Selezionare ed eseguire la prima metà della query (vedere il passaggio 18) fino alla riga:-- \* \* \* \* \* \* end: script da eseguire su Primary: \* \* \* \* \* \* .</span><span class="sxs-lookup"><span data-stu-id="b6d7f-189">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b6d7f-190">L'esecuzione manuale di questo script è necessaria perché SQL Server Management Studio non supporta più database primari in una configurazione di log shipping di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-190">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="b6d7f-191">Selezionare **Annulla** per chiudere il pannello di configurazione per la distribuzione dei file di registro e per stabilire una configurazione funzionante che implementi correttamente il file di log shipping sia per il database primario che per quello con mirroring (in caso di failover).</span><span class="sxs-lookup"><span data-stu-id="b6d7f-191">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="b6d7f-192">Non eseguire manualmente il backup del database primario di chat persistente sul primario.</span><span class="sxs-lookup"><span data-stu-id="b6d7f-192">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="b6d7f-193">A tale scopo, è possibile utilizzare la shell di gestione di Skype for Business Server e il cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="b6d7f-193">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

