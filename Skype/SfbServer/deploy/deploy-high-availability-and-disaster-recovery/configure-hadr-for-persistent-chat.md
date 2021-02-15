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
ms.openlocfilehash: 0b58f820c1157da8ff36f8dcc68d9e08465bcddc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830626"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="fbe1f-103">Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fbe1f-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fbe1f-104">**Riepilogo:** Leggere questo argomento per informazioni su come configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="fbe1f-105">Skype for Business Server supporta più modalità di disponibilità elevata per i server back-end, incluso il mirroring dei database.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="fbe1f-106">Per ulteriori informazioni, vedere Pianificare la disponibilità elevata e il ripristino di [emergenza in Skype for Business Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="fbe1f-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fbe1f-107">I gruppi di disponibilità AlwaysOn non sono supportati con i server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="fbe1f-108">Prima di configurare la distribuzione di Persistent Chat per la disponibilità elevata e il ripristino di emergenza, assicurarsi di avere familiarità con i concetti descritti in Pianificare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente [in Skype for Business Server 2015.](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="fbe1f-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="fbe1f-109">La soluzione di ripristino di emergenza per il server Chat persistente descritta in questi argomenti si basa su un pool di server Chat persistente estesa.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="fbe1f-110">Il contenuto della pianificazione descrive i requisiti delle risorse e la topologia del pool estesa che consente la disponibilità elevata e il ripristino di emergenza per il server Chat persistente, incluso l'utilizzo del mirroring SQL Server per la disponibilità elevata e il log shipping di SQL Server per il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="fbe1f-111">Utilizzare Generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="fbe1f-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="fbe1f-112">In Generatore di topologie eseguire la procedura seguente per configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="fbe1f-113">Aggiungere i database mirror e il database secondario di log shipping SQL Server archiviati.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="fbe1f-114">Modificare le proprietà del servizio del server Chat persistente in:</span><span class="sxs-lookup"><span data-stu-id="fbe1f-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="fbe1f-115">a.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-115">a.</span></span> <span data-ttu-id="fbe1f-116">Abilitare il mirroring per il database primario.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="fbe1f-117">b.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-117">b.</span></span> <span data-ttu-id="fbe1f-118">Aggiungere l'archivio SQL Server mirror primario.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="fbe1f-119">c.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-119">c.</span></span> <span data-ttu-id="fbe1f-120">Abilitare il SQL Server log shipping.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="fbe1f-121">d.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-121">d.</span></span> <span data-ttu-id="fbe1f-122">Aggiungere l'SQL Server log shipping secondario SQL Server archiviazione.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="fbe1f-123">e.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-123">e.</span></span> <span data-ttu-id="fbe1f-124">Aggiungere il SQL Server mirror dell'archivio per il database secondario.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="fbe1f-125">f.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-125">f.</span></span> <span data-ttu-id="fbe1f-126">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="fbe1f-127">Configurare il SQL Server log shipping per il database primario del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="fbe1f-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="fbe1f-128">Utilizzando SQL Server Management Studio, connettersi all'istanza secondaria del database di log shipping del server Chat persistente e verificare che SQL Server Agent sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="fbe1f-129">Connettersi quindi all'istanza del database principale di Persistent Chat ed eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="fbe1f-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="fbe1f-130">Fare clic con il pulsante destro del mouse sul database mgc e quindi scegliere **Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="fbe1f-131">In **Selezionare una pagina fare** clic su Log shipping delle **transazioni.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="fbe1f-132">Selezionare la **casella di controllo Abilita come database primario in una configurazione di log shipping.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="fbe1f-133">In **Backup dei registri delle transazioni** fare clic su Impostazioni **backup.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="fbe1f-134">Nella casella **Percorso di rete della cartella di backup** digitare il percorso di rete della condivisione creata per la cartella di backup del registro delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="fbe1f-135">Se la cartella di backup si trova nel server primario, digitare il percorso locale della cartella di backup nella casella Se la cartella di backup si trova nel server primario, digitare un percorso locale per la cartella **(ad esempio: c:\backup).**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-135">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box.</span></span> <span data-ttu-id="fbe1f-136">Se la cartella di backup non si trova nel server primario, è possibile lasciare vuota questa casella.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-136">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fbe1f-137">Se l'account del servizio di SQL Server sul server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server primario e specificare un percorso locale per tale cartella.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="fbe1f-138">Configurare **l'opzione Elimina file meno recenti e** Avvisa se non viene eseguito alcun backup **all'interno dei** parametri.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="fbe1f-139">Esaminare la pianificazione del backup elencata nella casella **Pianificazione** in **Processo di backup.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="fbe1f-140">Per personalizzare la pianificazione dell'installazione, fare clic su **Pianificazione** e modificare la pianificazione dell SQL Server agent in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="fbe1f-141">In **Compressione** selezionare Utilizza **l'impostazione predefinita del server** e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="fbe1f-142">In **Istanze e database del server secondario** fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="fbe1f-143">Fare **clic** su Connetti e connettersi all'istanza di SQL Server configurata come server secondario.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="fbe1f-144">Nella casella **Database secondario** selezionare il database **mgc** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="fbe1f-145">Nella scheda **Inizializza database** secondario scegliere **l'opzione Sì,** generare un backup completo del database primario e ripristinarlo nel database secondario (e creare il database secondario se non esiste).</span><span class="sxs-lookup"><span data-stu-id="fbe1f-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="fbe1f-146">Nella casella **Cartella** di  destinazione per i file copiati della scheda Copia file digitare il percorso della cartella in cui devono essere copiati i backup dei registri delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-146">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="fbe1f-147">Questa cartella si trova spesso nel server secondario.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-147">This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="fbe1f-148">Prendere nota della pianificazione della copia elencata nella **casella Pianificazione** in **Copia processo.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="fbe1f-149">Per personalizzare la pianificazione dell'installazione, fare clic su **Pianificazione** e modificare la pianificazione dell SQL Server agent in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="fbe1f-150">Questa pianificazione deve essere approssimativamente la stessa della pianificazione di backup.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="fbe1f-151">Nella scheda **Ripristino,** in **Stato database durante il ripristino dei backup,** scegliere l'opzione Nessuna modalità di **ripristino.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="fbe1f-152">In **Ritardare il ripristino dei backup selezionare** almeno **0 minuti.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="fbe1f-153">Scegliere una soglia di avviso in **Avviso se non viene eseguito alcun ripristino all'interno di**.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="fbe1f-154">Esaminare la pianificazione di ripristino elencata nella **casella Pianificazione** in Processo **di ripristino.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="fbe1f-155">Per personalizzare la pianificazione dell'installazione, fare clic su **Pianificazione,** modificare la pianificazione dell SQL Server Agent in base alle esigenze e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="fbe1f-156">Questa pianificazione deve essere approssimativamente la stessa della pianificazione di backup.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="fbe1f-157">Nella finestra **di dialogo Proprietà** database fare clic su **OK** per avviare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="fbe1f-158">Configurare il SQL Server log shipping tra il mirror primario e il database secondario</span><span class="sxs-lookup"><span data-stu-id="fbe1f-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="fbe1f-159">Eseguire la procedura seguente per continuare il log shipping se viene eseguito il backup del database di Persistent Chat primario nel relativo database mirror.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="fbe1f-160">Eseguire manualmente il failover del database principale di Persistent Chat nel mirroring.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="fbe1f-161">Questa operazione viene eseguita utilizzando Skype for Business Server Management Shell e il cmdlet **Invoke-CsDatabaseFailover.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="fbe1f-162">Utilizzando il SQL Server Management Studio, connettersi all'istanza mirror del server Chat persistente principale.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="fbe1f-163">Verificare che l'SQL Server agent sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="fbe1f-164">Fare clic con il pulsante destro del mouse sul database mgc e quindi scegliere **Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="fbe1f-165">In **Selezionare una pagina fare** clic su Log shipping delle **transazioni.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="fbe1f-166">Selezionare la **casella di controllo Abilita come database primario in una configurazione di log shipping.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="fbe1f-167">In **Backup dei registri delle transazioni** fare clic su Impostazioni **backup.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="fbe1f-168">Nella casella **Percorso di rete della cartella di backup** digitare il percorso di rete della condivisione creata per la cartella di backup del registro delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="fbe1f-169">Se la cartella di backup si trova nel server primario, digitare il percorso locale della cartella di backup nella casella Se la cartella di backup si trova nel **server primario,** digitare un percorso locale per la cartella.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-169">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="fbe1f-170">Se la cartella di backup non si trova nel server primario, è possibile lasciare vuota questa casella.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-170">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fbe1f-171">Se l'account del servizio di SQL Server sul server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server primario e specificare un percorso locale per tale cartella.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="fbe1f-172">Configurare **l'opzione Elimina file meno recenti e** Avvisa se non viene eseguito alcun backup **all'interno dei** parametri.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="fbe1f-173">Esaminare la pianificazione del backup elencata nella casella **Pianificazione** in **Processo di backup.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="fbe1f-174">Per personalizzare la pianificazione dell'installazione, fare clic su Pianificazione e modificare la pianificazione dell SQL Server agent, in base alle esigenze. </span><span class="sxs-lookup"><span data-stu-id="fbe1f-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fbe1f-175">Utilizzare le stesse impostazioni utilizzate per il database primario.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="fbe1f-176">In **Compressione** selezionare Utilizza **l'impostazione predefinita del server** e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="fbe1f-177">In **Istanze e database del server secondario** fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="fbe1f-178">Fare **clic** su Connetti e connettersi all'istanza di SQL Server configurata come server secondario.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="fbe1f-179">Nella casella **Database secondario** selezionare il database **mgc** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="fbe1f-180">Nella scheda **Inizializza database secondario** selezionare l'opzione **No, il database secondario viene inizializzato.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="fbe1f-181">Nella scheda **Copia file,** in Cartella di **destinazione** per i file copiati, digitare il percorso della cartella in cui copiare i backup dei registri delle transazioni e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-181">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**.</span></span> <span data-ttu-id="fbe1f-182">Questa cartella si trova spesso nel server secondario.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-182">This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="fbe1f-183">Aprire **l'elenco a** discesa Configurazione script e selezionare **Configurazione script in Nuova finestra query.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="fbe1f-184">Nella finestra della nuova query, in **Proprietà database,** fare clic su **OK** per avviare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="fbe1f-185">Selezionare ed eseguire la prima metà della query (vedere il passaggio 18) fino alla riga: -- Fine: script da \* \* \* \* \* \* eseguire in Primary: \* \* \* \* \* \* .</span><span class="sxs-lookup"><span data-stu-id="fbe1f-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fbe1f-186">L'esecuzione manuale di questo script è necessaria perché SQL Server Management Studio non supporta più database primari in una configurazione SQL Server log shipping.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="fbe1f-187">Selezionare **Annulla** per chiudere il pannello di configurazione log file shipping e stabilire un'installazione funzionante che implementi correttamente il file shipping per il database primario e il database con mirroring (in caso di failover).</span><span class="sxs-lookup"><span data-stu-id="fbe1f-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="fbe1f-188">Eseguire manualmente il fail back del database principale di Persistent Chat sul database primario.</span><span class="sxs-lookup"><span data-stu-id="fbe1f-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="fbe1f-189">Questa operazione viene eseguita utilizzando Skype for Business Server Management Shell e il cmdlet **Invoke-CsDatabaseFailover.**</span><span class="sxs-lookup"><span data-stu-id="fbe1f-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

