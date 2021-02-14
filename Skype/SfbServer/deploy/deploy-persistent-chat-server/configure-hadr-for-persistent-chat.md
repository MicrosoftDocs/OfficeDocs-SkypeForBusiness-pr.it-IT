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
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="b296b-103">Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b296b-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b296b-104">**Riepilogo:** Leggere questo argomento per informazioni su come configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b296b-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b296b-105">Skype for Business Server supporta più modalità di disponibilità elevata per i server back-end, incluso il mirroring dei database.</span><span class="sxs-lookup"><span data-stu-id="b296b-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="b296b-106">Per ulteriori informazioni, vedere Pianificare la disponibilità elevata e il ripristino di [emergenza in Skype for Business Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="b296b-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b296b-107">I gruppi di disponibilità AlwaysOn non sono supportati con i server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b296b-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 

> [!NOTE] 
> <span data-ttu-id="b296b-108">La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b296b-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b296b-109">Le stesse funzionalità sono disponibili in Teams.</span><span class="sxs-lookup"><span data-stu-id="b296b-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="b296b-110">Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="b296b-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="b296b-111">Se è necessario usare Chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b296b-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b296b-112">Prima di configurare la distribuzione di Persistent Chat per la disponibilità elevata e il ripristino di emergenza, assicurarsi di avere familiarità con i concetti descritti in Pianificare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente [in Skype for Business Server 2015.](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="b296b-112">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="b296b-113">La soluzione di ripristino di emergenza per il server Chat persistente descritta in questi argomenti si basa su un pool di server Chat persistente estesa.</span><span class="sxs-lookup"><span data-stu-id="b296b-113">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="b296b-114">Il contenuto della pianificazione descrive i requisiti delle risorse e la topologia del pool estesa che consente la disponibilità elevata e il ripristino di emergenza per il server Chat persistente, incluso l'utilizzo del mirroring SQL Server per la disponibilità elevata e il log shipping di SQL Server per il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="b296b-114">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="b296b-115">Utilizzare Generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="b296b-115">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="b296b-116">In Generatore di topologie eseguire la procedura seguente per configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b296b-116">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="b296b-117">Aggiungere i database mirror e il database secondario di log shipping SQL Server archiviati.</span><span class="sxs-lookup"><span data-stu-id="b296b-117">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="b296b-118">Modificare le proprietà del servizio del server Chat persistente in:</span><span class="sxs-lookup"><span data-stu-id="b296b-118">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="b296b-119">a.</span><span class="sxs-lookup"><span data-stu-id="b296b-119">a.</span></span> <span data-ttu-id="b296b-120">Abilitare il mirroring per il database primario.</span><span class="sxs-lookup"><span data-stu-id="b296b-120">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="b296b-121">b.</span><span class="sxs-lookup"><span data-stu-id="b296b-121">b.</span></span> <span data-ttu-id="b296b-122">Aggiungere l'archivio SQL Server mirror primario.</span><span class="sxs-lookup"><span data-stu-id="b296b-122">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="b296b-123">c.</span><span class="sxs-lookup"><span data-stu-id="b296b-123">c.</span></span> <span data-ttu-id="b296b-124">Abilitare il SQL Server log shipping.</span><span class="sxs-lookup"><span data-stu-id="b296b-124">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="b296b-125">d.</span><span class="sxs-lookup"><span data-stu-id="b296b-125">d.</span></span> <span data-ttu-id="b296b-126">Aggiungere l'SQL Server log shipping secondario SQL Server archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b296b-126">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="b296b-127">e.</span><span class="sxs-lookup"><span data-stu-id="b296b-127">e.</span></span> <span data-ttu-id="b296b-128">Aggiungere il SQL Server mirror dell'archivio per il database secondario.</span><span class="sxs-lookup"><span data-stu-id="b296b-128">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="b296b-129">f.</span><span class="sxs-lookup"><span data-stu-id="b296b-129">f.</span></span> <span data-ttu-id="b296b-130">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="b296b-130">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="b296b-131">Configurare il SQL Server log shipping per il database primario del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="b296b-131">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="b296b-132">Utilizzando SQL Server Management Studio, connettersi all'istanza secondaria del database di log shipping del server Chat persistente e verificare che SQL Server Agent sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b296b-132">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="b296b-133">Connettersi quindi all'istanza del database principale di Persistent Chat ed eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="b296b-133">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="b296b-134">Fare clic con il pulsante destro del mouse sul database mgc e quindi scegliere **Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="b296b-134">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="b296b-135">In **Selezionare una pagina fare** clic su Log shipping delle **transazioni.**</span><span class="sxs-lookup"><span data-stu-id="b296b-135">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="b296b-136">Selezionare la **casella di controllo Abilita come database primario in una configurazione di log shipping.**</span><span class="sxs-lookup"><span data-stu-id="b296b-136">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="b296b-137">In **Backup dei registri delle transazioni** fare clic su Impostazioni **backup.**</span><span class="sxs-lookup"><span data-stu-id="b296b-137">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="b296b-138">Nella casella **Percorso di rete della cartella di backup** digitare il percorso di rete della condivisione creata per la cartella di backup del registro delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="b296b-138">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="b296b-139">Se la cartella di backup si trova nel server primario, digitare il percorso locale della cartella di backup nella casella Se la cartella di backup si trova nel server primario, digitare un percorso locale per la cartella **(ad esempio: c:\backup).**</span><span class="sxs-lookup"><span data-stu-id="b296b-139">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box.</span></span> <span data-ttu-id="b296b-140">Se la cartella di backup non si trova nel server primario, è possibile lasciare vuota questa casella.</span><span class="sxs-lookup"><span data-stu-id="b296b-140">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b296b-141">Se l'account del servizio di SQL Server sul server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server primario e specificare un percorso locale per tale cartella.</span><span class="sxs-lookup"><span data-stu-id="b296b-141">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="b296b-142">Configurare **l'opzione Elimina file meno recenti e** Avvisa se non viene eseguito alcun backup **all'interno dei** parametri.</span><span class="sxs-lookup"><span data-stu-id="b296b-142">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="b296b-143">Esaminare la pianificazione del backup elencata nella casella **Pianificazione** in **Processo di backup.**</span><span class="sxs-lookup"><span data-stu-id="b296b-143">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="b296b-144">Per personalizzare la pianificazione dell'installazione, fare clic su **Pianificazione** e modificare la pianificazione dell SQL Server agent in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="b296b-144">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="b296b-145">In **Compressione** selezionare Utilizza **l'impostazione predefinita del server** e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="b296b-145">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="b296b-146">In **Istanze e database del server secondario** fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="b296b-146">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="b296b-147">Fare **clic** su Connetti e connettersi all'istanza di SQL Server configurata come server secondario.</span><span class="sxs-lookup"><span data-stu-id="b296b-147">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="b296b-148">Nella casella **Database secondario** selezionare il database **mgc** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="b296b-148">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="b296b-149">Nella scheda **Inizializza database** secondario scegliere **l'opzione Sì,** generare un backup completo del database primario e ripristinarlo nel database secondario (e creare il database secondario se non esiste).</span><span class="sxs-lookup"><span data-stu-id="b296b-149">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="b296b-150">Nella casella **Cartella** di  destinazione per i file copiati della scheda Copia file digitare il percorso della cartella in cui devono essere copiati i backup dei registri delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="b296b-150">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="b296b-151">Questa cartella si trova spesso nel server secondario.</span><span class="sxs-lookup"><span data-stu-id="b296b-151">This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="b296b-152">Prendere nota della pianificazione della copia elencata nella **casella Pianificazione** in **Copia processo.**</span><span class="sxs-lookup"><span data-stu-id="b296b-152">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="b296b-153">Per personalizzare la pianificazione dell'installazione, fare clic su **Pianificazione** e modificare la pianificazione dell SQL Server agent in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="b296b-153">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="b296b-154">Questa pianificazione deve essere approssimativamente la stessa della pianificazione di backup.</span><span class="sxs-lookup"><span data-stu-id="b296b-154">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="b296b-155">Nella scheda **Ripristino,** in **Stato database durante il ripristino dei backup,** scegliere l'opzione Nessuna modalità di **ripristino.**</span><span class="sxs-lookup"><span data-stu-id="b296b-155">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="b296b-156">In **Ritardare il ripristino dei backup selezionare** almeno **0 minuti.**</span><span class="sxs-lookup"><span data-stu-id="b296b-156">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="b296b-157">Scegliere una soglia di avviso in **Avviso se non viene eseguito alcun ripristino all'interno di**.</span><span class="sxs-lookup"><span data-stu-id="b296b-157">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="b296b-158">Esaminare la pianificazione di ripristino elencata nella **casella Pianificazione** in Processo **di ripristino.**</span><span class="sxs-lookup"><span data-stu-id="b296b-158">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="b296b-159">Per personalizzare la pianificazione dell'installazione, fare clic su **Pianificazione,** modificare la pianificazione dell SQL Server Agent in base alle esigenze e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="b296b-159">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="b296b-160">Questa pianificazione deve essere approssimativamente la stessa della pianificazione di backup.</span><span class="sxs-lookup"><span data-stu-id="b296b-160">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="b296b-161">Nella finestra **di dialogo Proprietà** database fare clic su **OK** per avviare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b296b-161">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="b296b-162">Configurare il SQL Server log shipping tra il mirror primario e il database secondario</span><span class="sxs-lookup"><span data-stu-id="b296b-162">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="b296b-163">Eseguire la procedura seguente per continuare il log shipping se viene eseguito il backup del database di Persistent Chat primario nel relativo database mirror.</span><span class="sxs-lookup"><span data-stu-id="b296b-163">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="b296b-164">Eseguire manualmente il failover del database principale di Persistent Chat nel mirroring.</span><span class="sxs-lookup"><span data-stu-id="b296b-164">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="b296b-165">Questa operazione viene eseguita utilizzando Skype for Business Server Management Shell e il cmdlet **Invoke-CsDatabaseFailover.**</span><span class="sxs-lookup"><span data-stu-id="b296b-165">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="b296b-166">Utilizzando il SQL Server Management Studio, connettersi all'istanza mirror del server Chat persistente principale.</span><span class="sxs-lookup"><span data-stu-id="b296b-166">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="b296b-167">Verificare che l'SQL Server agent sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b296b-167">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="b296b-168">Fare clic con il pulsante destro del mouse sul database mgc e quindi scegliere **Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="b296b-168">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="b296b-169">In **Selezionare una pagina fare** clic su Log shipping delle **transazioni.**</span><span class="sxs-lookup"><span data-stu-id="b296b-169">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="b296b-170">Selezionare la **casella di controllo Abilita come database primario in una configurazione di log shipping.**</span><span class="sxs-lookup"><span data-stu-id="b296b-170">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="b296b-171">In **Backup dei registri delle transazioni** fare clic su Impostazioni **backup.**</span><span class="sxs-lookup"><span data-stu-id="b296b-171">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="b296b-172">Nella casella **Percorso di rete della cartella di backup** digitare il percorso di rete della condivisione creata per la cartella di backup del registro delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="b296b-172">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="b296b-173">Se la cartella di backup si trova nel server primario, digitare il percorso locale della cartella di backup nella casella Se la cartella di backup si trova nel **server primario,** digitare un percorso locale per la cartella.</span><span class="sxs-lookup"><span data-stu-id="b296b-173">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="b296b-174">Se la cartella di backup non si trova nel server primario, è possibile lasciare vuota questa casella.</span><span class="sxs-lookup"><span data-stu-id="b296b-174">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b296b-175">Se l'account del servizio di SQL Server sul server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server primario e specificare un percorso locale per tale cartella.</span><span class="sxs-lookup"><span data-stu-id="b296b-175">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="b296b-176">Configurare **l'opzione Elimina file meno recenti e** Avvisa se non viene eseguito alcun backup **all'interno dei** parametri.</span><span class="sxs-lookup"><span data-stu-id="b296b-176">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="b296b-177">Esaminare la pianificazione del backup elencata nella casella **Pianificazione** in **Processo di backup.**</span><span class="sxs-lookup"><span data-stu-id="b296b-177">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="b296b-178">Per personalizzare la pianificazione dell'installazione, fare clic su Pianificazione e modificare la pianificazione dell SQL Server agent, in base alle esigenze. </span><span class="sxs-lookup"><span data-stu-id="b296b-178">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b296b-179">Utilizzare le stesse impostazioni utilizzate per il database primario.</span><span class="sxs-lookup"><span data-stu-id="b296b-179">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="b296b-180">In **Compressione** selezionare Utilizza **l'impostazione predefinita del server** e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="b296b-180">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="b296b-181">In **Istanze e database del server secondario** fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="b296b-181">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="b296b-182">Fare **clic** su Connetti e connettersi all'istanza di SQL Server configurata come server secondario.</span><span class="sxs-lookup"><span data-stu-id="b296b-182">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="b296b-183">Nella casella **Database secondario** selezionare il database **mgc** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="b296b-183">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="b296b-184">Nella scheda **Inizializza database secondario** selezionare l'opzione **No, il database secondario viene inizializzato.**</span><span class="sxs-lookup"><span data-stu-id="b296b-184">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="b296b-185">Nella scheda **Copia file,** in Cartella di **destinazione** per i file copiati, digitare il percorso della cartella in cui copiare i backup dei registri delle transazioni e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="b296b-185">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**.</span></span> <span data-ttu-id="b296b-186">Questa cartella si trova spesso nel server secondario.</span><span class="sxs-lookup"><span data-stu-id="b296b-186">This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="b296b-187">Aprire **l'elenco a** discesa Configurazione script e selezionare **Configurazione script in Nuova finestra query.**</span><span class="sxs-lookup"><span data-stu-id="b296b-187">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="b296b-188">Nella finestra della nuova query, in **Proprietà database,** fare clic su **OK** per avviare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b296b-188">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="b296b-189">Selezionare ed eseguire la prima metà della query (vedere il passaggio 18) fino alla riga: -- Fine: script da \* \* \* \* \* \* eseguire in Primary: \* \* \* \* \* \* .</span><span class="sxs-lookup"><span data-stu-id="b296b-189">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b296b-190">L'esecuzione manuale di questo script è necessaria perché SQL Server Management Studio non supporta più database primari in una configurazione SQL Server log shipping.</span><span class="sxs-lookup"><span data-stu-id="b296b-190">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="b296b-191">Selezionare **Annulla** per chiudere il pannello di configurazione log file shipping e stabilire un'installazione funzionante che implementi correttamente il file shipping per il database primario e il database con mirroring (in caso di failover).</span><span class="sxs-lookup"><span data-stu-id="b296b-191">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="b296b-192">Eseguire manualmente il fail back del database principale di Persistent Chat sul database primario.</span><span class="sxs-lookup"><span data-stu-id="b296b-192">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="b296b-193">Questa operazione viene eseguita utilizzando Skype for Business Server Management Shell e il cmdlet **Invoke-CsDatabaseFailover.**</span><span class="sxs-lookup"><span data-stu-id="b296b-193">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

