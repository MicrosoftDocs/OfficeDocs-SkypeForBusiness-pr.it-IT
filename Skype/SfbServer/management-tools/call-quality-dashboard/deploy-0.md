---
title: Distribuire dashboard qualità chiamata per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Riepilogo: informazioni sul processo di distribuzione per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.'
ms.openlocfilehash: 797288428530a055987d8b0a8e1ebf6a9e8b9dcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832716"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="41a14-104">Distribuire dashboard qualità chiamata per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="41a14-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="41a14-105">**Riepilogo:** Informazioni sul processo di distribuzione per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="41a14-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="41a14-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="41a14-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="41a14-107">Panoramica della distribuzione</span><span class="sxs-lookup"><span data-stu-id="41a14-107">Deployment Overview</span></span>

<span data-ttu-id="41a14-108">Call Quality Dashboard (CQD) è costituito da tre componenti principali:</span><span class="sxs-lookup"><span data-stu-id="41a14-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="41a14-109">**Database di archiviazione**, in cui vengono replicati e archiviati i dati QoE (Quality of Experience).</span><span class="sxs-lookup"><span data-stu-id="41a14-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="41a14-110">**Cubo**, in cui i dati provenienti dal database di archiviazione QoE vengono aggregati per ottimizzare e velocizzare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="41a14-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="41a14-111">**Portale**, in cui gli utenti possono facilmente interrogare e visualizzare i dati QoE.</span><span class="sxs-lookup"><span data-stu-id="41a14-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![Componenti di CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="41a14-113">Il processo di installazione per l'archivio QoE implica la creazione del database di archiviazione QoE, la distribuzione di una stored procedure SQL Server che sposterà i dati dal database di metriche QoE di origine nel database di archiviazione QoE e la configurazione del processo di SQL Server Agent per l'esecuzione della stored procedure a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="41a14-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="41a14-114">La distribuzione del cubo consente di ottenere informazioni dall'utente in cui si trova l'archivio QoE, distribuire il cubo e configurare un processo normale di agente SQL Server che aggiornerà il cubo a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="41a14-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="41a14-115">L'installazione del portale crea un database del repository che archivia il mapping degli utenti di CQD ai report/query di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="41a14-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="41a14-116">Viene quindi impostata un'applicazione Web IIS che è il dashboard in cui gli utenti possono visualizzare un insieme predefinito di report, nonché personalizzare e creare le proprie query per visualizzare i dati del cubo.</span><span class="sxs-lookup"><span data-stu-id="41a14-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="41a14-117">L'installazione del portale crea due ulteriori applicazioni Web che espongono le API per gli utenti a accedere a livello di programmazione all'archivio e al cubo.</span><span class="sxs-lookup"><span data-stu-id="41a14-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="41a14-118">(Queste API vengono utilizzate internamente anche dal dashboard).</span><span class="sxs-lookup"><span data-stu-id="41a14-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="41a14-119">**Fase**</span><span class="sxs-lookup"><span data-stu-id="41a14-119">**Phase**</span></span>|<span data-ttu-id="41a14-120">**Procedura**</span><span class="sxs-lookup"><span data-stu-id="41a14-120">**Steps**</span></span>|<span data-ttu-id="41a14-121">**Ruoli e appartenenza ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="41a14-121">**Roles and group membership**</span></span>|<span data-ttu-id="41a14-122">**Documentazione**</span><span class="sxs-lookup"><span data-stu-id="41a14-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41a14-123">Installare l'hardware e il software prerequisito.</span><span class="sxs-lookup"><span data-stu-id="41a14-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="41a14-124">Decidere la configurazione di CQD e scegliere un SQL Server da cui eseguire l'installazione.</span><span class="sxs-lookup"><span data-stu-id="41a14-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="41a14-125">Utente del dominio membro del gruppo Administrators locale</span><span class="sxs-lookup"><span data-stu-id="41a14-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="41a14-126">Sezione "requisiti di pre-installazione" nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="41a14-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="41a14-127">Installare CQD.</span><span class="sxs-lookup"><span data-stu-id="41a14-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="41a14-128">Eseguire il MSI dopo il documento di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="41a14-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="41a14-129">Per eseguire il programma di installazione, è necessario che l'account di installazione sia un utente di dominio membro del gruppo Administrators locale e che disponga dell'accesso in lettura al database delle metriche QoE sul Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="41a14-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="41a14-130">Sezione "account e passaggi di distribuzione" nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="41a14-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="41a14-131">Concedere l'accesso degli utenti.</span><span class="sxs-lookup"><span data-stu-id="41a14-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="41a14-132">Per la gestione dell'autorizzazione utente per il portale, è consigliabile utilizzare l'autorizzazione URL, introdotta in IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="41a14-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="41a14-133">Per ulteriori informazioni, vedere [Understanding IIS 7,0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="41a14-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="41a14-134">Utente del dominio membro del gruppo Administrators locale</span><span class="sxs-lookup"><span data-stu-id="41a14-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="41a14-135">Gestione dell'accesso degli utenti per la sezione portale nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="41a14-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="41a14-136">Facoltativo: fornire informazioni di mapping della subnet.</span><span class="sxs-lookup"><span data-stu-id="41a14-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="41a14-137">Popolare le tabelle di mapping di rete e creazione nel database di archivio QoE.</span><span class="sxs-lookup"><span data-stu-id="41a14-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="41a14-138">Un account con accesso in scrittura al database di archiviazione QoE.</span><span class="sxs-lookup"><span data-stu-id="41a14-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="41a14-139">Sezione "informazioni sulla subnet per la fornitura" nella documentazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="41a14-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="41a14-140">La distribuzione del dashboard per la qualità delle chiamate implica la configurazione dell'infrastruttura e l'installazione del software.</span><span class="sxs-lookup"><span data-stu-id="41a14-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="41a14-141">Nella procedura seguente viene illustrato il processo.</span><span class="sxs-lookup"><span data-stu-id="41a14-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="41a14-142">Passaggi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="41a14-142">Deployment Steps</span></span>

1. <span data-ttu-id="41a14-143">Copiare il CallQualityDashboard.msi nel computer in cui deve essere installato il componente di database di archiviazione di CQD (ovvero il computer in cui è installato SQL Server).</span><span class="sxs-lookup"><span data-stu-id="41a14-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="41a14-144">Eseguire il MSI (Windows verrà richiesto di eseguire con privilegi di amministratore, farlo).</span><span class="sxs-lookup"><span data-stu-id="41a14-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="41a14-145">Accettare il contratto di licenza.</span><span class="sxs-lookup"><span data-stu-id="41a14-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="41a14-146">Selezionare la cartella di destinazione in cui si trovano i file correlati ai componenti del dashboard qualità chiamata oppure accettare il percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="41a14-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="41a14-147">Selezionare tutte le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="41a14-147">Select all features.</span></span>
    
6. <span data-ttu-id="41a14-148">Nella pagina Configurazione archivio QoE, specificare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41a14-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="41a14-149">**Metriche QoE SQL Server:** Nome dell'istanza di SQL Server per la posizione in cui si trova il database di metriche QoE (questa sarà l'origine dati).</span><span class="sxs-lookup"><span data-stu-id="41a14-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="41a14-150">**Nome SQL Server di archiviazione QoE:** Si tratta di un campo di sola lettura e viene fissato al nome di dominio completo del computer locale.</span><span class="sxs-lookup"><span data-stu-id="41a14-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="41a14-151">È possibile installare il database di archiviazione solo nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="41a14-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="41a14-152">**Istanza di SQL Server di archiviazione QoE:** Nome di istanza di SQL Server locale in cui deve essere creato il database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="41a14-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="41a14-153">Per utilizzare un'istanza di SQL Server predefinita, lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="41a14-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="41a14-154">Per utilizzare un'istanza di SQL Server denominata, specificare il nome dell'istanza (ad esempio, il nome dopo la " \" ).</span><span class="sxs-lookup"><span data-stu-id="41a14-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="41a14-155">**Database di archiviazione QoE:** Per impostazione predefinita, questa opzione è impostata su "Crea nuovo database".</span><span class="sxs-lookup"><span data-stu-id="41a14-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="41a14-156">Dal momento che l'aggiornamento di archiviazione DB non è supportato, l'unica circostanza in cui è possibile utilizzare l'opzione "Usa database esistente" è se il database di archiviazione esistente ha lo stesso schema della build da installare.</span><span class="sxs-lookup"><span data-stu-id="41a14-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="41a14-157">**Directory file di database:** Percorso in cui devono essere posizionati i file di database (con estensione MDF e ldf) per il DB di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="41a14-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="41a14-158">Questo dovrebbe essere su un'unità (HDD2 nella configurazione hardware consigliata) separata dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="41a14-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="41a14-159">Si noti che, poiché i nomi dei file vengono corretti nell'installazione, per evitare potenziali conflitti, è consigliabile utilizzare una directory vuota senza file.</span><span class="sxs-lookup"><span data-stu-id="41a14-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="41a14-160">**Utilizzo di più partizioni:** Il valore predefinito è "multiple Partition", che richiede Business Intelligence Edition o Enterprise Edition di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="41a14-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="41a14-161">Per Standard Edition selezionare l'opzione "partizione singola".</span><span class="sxs-lookup"><span data-stu-id="41a14-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="41a14-162">Si noti che le prestazioni di elaborazione del cubo possono essere influenzate se si utilizza una singola partizione.</span><span class="sxs-lookup"><span data-stu-id="41a14-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="41a14-163">L'opzione selezione per l'utilizzo di più partizioni non può essere modificata dopo il completamento dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="41a14-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="41a14-164">Per modificarlo, è necessario prima disinstallare la caratteristica cubo e quindi reinstallarla utilizzando l'opzione "cambia" nel pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="41a14-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="41a14-165">**Directory file di partizione:** Percorso in cui deve essere posizionata la partizione per il database di archiviazione QoE.</span><span class="sxs-lookup"><span data-stu-id="41a14-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="41a14-166">Questo dovrebbe essere su un'unità (HDD3 nella configurazione hardware consigliata) separata dall'unità del sistema operativo e dal disco dei file di registro di database SQL.</span><span class="sxs-lookup"><span data-stu-id="41a14-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="41a14-167">Si noti che, poiché i nomi dei file vengono corretti nell'installazione, per evitare potenziali conflitti, è consigliabile utilizzare una directory vuota senza file.</span><span class="sxs-lookup"><span data-stu-id="41a14-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="41a14-168">Nome utente del **&amp; processo agente SQL Password:** nome dell'account del servizio di dominio e password (mascherata) che verrà utilizzata per eseguire il passaggio "dati di archiviazione QoE" del processo di SQL Server Agent (che eseguirà la stored procedure per recuperare i dati dal database delle metriche QoE in archivio DB, in questo modo questo account deve disporre dell'accesso in lettura al database delle metriche QoE, come indicato nella sezione account.</span><span class="sxs-lookup"><span data-stu-id="41a14-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="41a14-169">Questo account deve inoltre disporre di un accesso nell'istanza di SQL Server di archiviazione QoE.</span><span class="sxs-lookup"><span data-stu-id="41a14-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="41a14-170">L'account su cui è in esecuzione l'istanza di SQL Server, ad esempio NT SERVICE\MSSQLSERVER, deve disporre di accesso/autorizzazione alle directory indicate in alto perché l'installazione abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="41a14-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="41a14-171">Per informazioni dettagliate, vedere [Configure file System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="41a14-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="41a14-172">Dopo aver fatto clic su Avanti, il programma di installazione eseguirà i controlli prerequisiti e riferirà se vengono rilevati problemi.</span><span class="sxs-lookup"><span data-stu-id="41a14-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="41a14-173">Quando tutti i controlli prerequisiti passano, il programma di installazione passerà alla pagina di configurazione del cubo.</span><span class="sxs-lookup"><span data-stu-id="41a14-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="41a14-174">Se il programma di installazione visualizza un messaggio di avviso in cui il servizio SQL Server Agent per l'istanza di SQL Server di archiviazione QoE non è in esecuzione, l'installazione può procedere, ma dopo l'installazione accertarsi che il servizio agente SQL sia in esecuzione e impostare il tipo di avvio su automatico in modo che venga eseguito il processo pianificato.</span><span class="sxs-lookup"><span data-stu-id="41a14-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="41a14-175">Nella pagina Configurazione cubo fornire le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41a14-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="41a14-176">**Nome SQL Server di archiviazione QoE:** Si tratta di un campo di sola lettura e viene fissato al nome di dominio completo del computer locale.</span><span class="sxs-lookup"><span data-stu-id="41a14-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="41a14-177">Il cubo può essere installato solo dal computer in cui è presente il database di archiviazione QoE (nota.</span><span class="sxs-lookup"><span data-stu-id="41a14-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="41a14-178">Il cubo stesso può essere installato in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="41a14-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="41a14-179">Vedere di seguito)</span><span class="sxs-lookup"><span data-stu-id="41a14-179">See below)</span></span>
    
   - <span data-ttu-id="41a14-180">**Istanza di SQL Server di archiviazione QoE:** Nome dell'istanza di SQL Server per la posizione in cui si trova il database di archiviazione QoE.</span><span class="sxs-lookup"><span data-stu-id="41a14-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="41a14-181">Per specificare un'istanza di SQL Server predefinita, lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="41a14-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="41a14-182">Per specificare un'istanza di SQL Server denominata, immettere il nome dell'istanza (ad esempio il nome dopo la " \" ).</span><span class="sxs-lookup"><span data-stu-id="41a14-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="41a14-183">Se il componente archivio QoE è stato selezionato per l'installazione, questo campo verrà prepopolato con il valore specificato nella pagina di configurazione dell'archivio QoE.</span><span class="sxs-lookup"><span data-stu-id="41a14-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="41a14-184">**Server di analisi del cubo:** Nome dell'istanza del servizio di analisi SQL Server per la posizione in cui deve essere creato il cubo.</span><span class="sxs-lookup"><span data-stu-id="41a14-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="41a14-185">Può trattarsi di un computer diverso, ma l'utente che esegue l'installazione deve essere membro degli amministratori del server dell'istanza del servizio di analisi di SQL Server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="41a14-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="41a14-186">Per ulteriori informazioni sulla configurazione delle autorizzazioni di amministratore del server di Analysis Services, vedere [Grant Server Administrator permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="41a14-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="41a14-187">**Utilizzo di più partizioni:** Il valore predefinito è "multiple Partition", che richiede Business Intelligence Edition o Enterprise Edition di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="41a14-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="41a14-188">Per Standard Edition selezionare l'opzione "partizione singola".</span><span class="sxs-lookup"><span data-stu-id="41a14-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="41a14-189">Si noti che le prestazioni di elaborazione del cubo possono essere influenzate se si utilizza una singola partizione.</span><span class="sxs-lookup"><span data-stu-id="41a14-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="41a14-190">L'opzione selezione per l'utilizzo di più partizioni non può essere modificata dopo il completamento dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="41a14-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="41a14-191">Per modificarlo, è necessario prima disinstallare la caratteristica cubo e quindi reinstallarla utilizzando l'opzione "cambia" nel pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="41a14-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="41a14-192">Nome utente del **&amp; cubo Password:** nome dell'account del servizio di dominio e password (mascherata) che attiverà l'elaborazione del cubo.</span><span class="sxs-lookup"><span data-stu-id="41a14-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="41a14-193">Se il componente archivio QoE è stato selezionato per l'installazione, questo campo verrà prepopolato con il valore specificato nella pagina Configurazione di archiviazione per l'utente del processo SQL Agent, ma è consigliabile specificare un account di servizio di dominio diverso in modo che il programma di installazione possa concedergli il privilegio meno richiesto.</span><span class="sxs-lookup"><span data-stu-id="41a14-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="41a14-194">Quando si fa clic su Avanti, verrà eseguito un altro round di convalida e verrà segnalato qualsiasi problema.</span><span class="sxs-lookup"><span data-stu-id="41a14-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="41a14-195">Dopo aver completato la convalida, il programma di installazione passerà alla pagina di configurazione del portale.</span><span class="sxs-lookup"><span data-stu-id="41a14-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="41a14-196">Nella pagina Configurazione portale, specificare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41a14-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="41a14-197">**Archivio QoE SQL Server:** Nome dell'istanza di SQL Server per la posizione in cui si trova il database di archiviazione QoE.</span><span class="sxs-lookup"><span data-stu-id="41a14-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="41a14-198">Si noti che, a differenza della pagina di configurazione dell'archivio QoE e della pagina di configurazione del cubo, il nome del computer non è corretto e deve essere fornito.</span><span class="sxs-lookup"><span data-stu-id="41a14-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="41a14-199">Se il componente archivio QoE è stato selezionato per l'installazione, questo campo verrà prepopolato con il valore specificato nella pagina di configurazione dell'archivio QoE.</span><span class="sxs-lookup"><span data-stu-id="41a14-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="41a14-200">**Server di analisi del cubo:** Nome dell'istanza del servizio di analisi SQL Server per la posizione in cui si trova il cubo.</span><span class="sxs-lookup"><span data-stu-id="41a14-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="41a14-201">Se è stato selezionato il componente cubo per l'installazione, questo campo verrà prepopolato con il valore specificato nella pagina Configurazione cubo.</span><span class="sxs-lookup"><span data-stu-id="41a14-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="41a14-202">**Archivio SQL Server:** Nome dell'istanza di SQL Server in cui deve essere creato il database dell'archivio.</span><span class="sxs-lookup"><span data-stu-id="41a14-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="41a14-203">Se il nome dell'istanza di SQL Server per la posizione in cui si trova il database di archiviazione QoE è stato specificato in precedenza nel programma di installazione (in altri componenti), questo campo verrà prepopolato con il nome dell'istanza di SQL Server di archiviazione QoE DB.</span><span class="sxs-lookup"><span data-stu-id="41a14-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="41a14-204">Può trattarsi di qualsiasi istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="41a14-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="41a14-205">**Database repository:** Per impostazione predefinita, l'opzione è impostata su "Crea nuovo database".</span><span class="sxs-lookup"><span data-stu-id="41a14-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="41a14-206">Dal momento che l'aggiornamento del repository DB non è supportato, l'unica circostanza in cui è possibile utilizzare l'opzione "Usa database esistente" è se il DB del repository esistente ha lo stesso schema della build da installare.</span><span class="sxs-lookup"><span data-stu-id="41a14-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="41a14-207">Nome utente del **&amp; pool di applicazioni IIS Password:** l'account in cui deve essere eseguito il pool di applicazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="41a14-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="41a14-208">I campi nome utente e password saranno disabilitati se sono selezionati account di sistema incorporati.</span><span class="sxs-lookup"><span data-stu-id="41a14-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="41a14-209">Questi campi verranno abilitati solo se è selezionata l'opzione "altro" nella casella a discesa in modo che l'utente possa immettere le informazioni sull'account del servizio del dominio.</span><span class="sxs-lookup"><span data-stu-id="41a14-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="41a14-210">Quando si fa clic su Avanti, verrà eseguito l'ultimo round di convalida per garantire che le istanze di SQL Server siano accessibili utilizzando le credenziali fornite e che IIS sia disponibile nel computer.</span><span class="sxs-lookup"><span data-stu-id="41a14-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="41a14-211">Dopo aver completato la convalida, il programma di installazione procederà con l'installazione.</span><span class="sxs-lookup"><span data-stu-id="41a14-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="41a14-212">Al termine del programma di installazione, è probabile che il processo di SQL Server Agent sia in corso, eseguendo il caricamento iniziale dei dati QoE e l'elaborazione del cubo.</span><span class="sxs-lookup"><span data-stu-id="41a14-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="41a14-213">A seconda della quantità di dati in QoE, il portale non avrà dati disponibili per la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="41a14-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="41a14-214">Per verificare lo stato del caricamento dei dati e dell'elaborazione del cubo, passare a  `http://<machinename>/CQD/#/Health` .</span><span class="sxs-lookup"><span data-stu-id="41a14-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="41a14-215">Si noti che l'URL per il controllo dello stato dell'elaborazione del cubo di download è distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="41a14-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="41a14-216">Se si immette "integrità", l'URL non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="41a14-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="41a14-217">È necessario immettere ' integrità' alla fine dell'URL con una maiuscola H.</span><span class="sxs-lookup"><span data-stu-id="41a14-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="41a14-218">I messaggi dettagliati verranno visualizzati se la modalità di debug è abilitata.</span><span class="sxs-lookup"><span data-stu-id="41a14-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="41a14-219">Per abilitare la modalità di debug, passare a **%SystemDrive%\Program Skype for Business 2015 CQD\QoEDataService\web.config** e aggiornare la riga seguente in modo che il valore sia impostato su **true**:</span><span class="sxs-lookup"><span data-stu-id="41a14-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="41a14-220">La pagina principale del portale è accessibile tramite  `http://<machinename>/CQD` .</span><span class="sxs-lookup"><span data-stu-id="41a14-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="41a14-221">Gestione dell'accesso degli utenti per il portale</span><span class="sxs-lookup"><span data-stu-id="41a14-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="41a14-222">Per la gestione dell'autorizzazione utente per il portale, è consigliabile utilizzare l'autorizzazione URL, introdotta in IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="41a14-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="41a14-223">Per ulteriori informazioni sulla sicurezza di IIS, vedere [Understanding iis 7,0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="41a14-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="41a14-224">Qualsiasi sito Web o applicazione Web eredita l'autorizzazione URL predefinita configurata per l'intera IIS, che in genere è "Consenti a tutti gli utenti".</span><span class="sxs-lookup"><span data-stu-id="41a14-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="41a14-225">Se l'accesso al portale deve essere più restrittivo, gli amministratori potranno concedere l'accesso solo a un gruppo specifico di utenti modificando le "regole di autorizzazione".</span><span class="sxs-lookup"><span data-stu-id="41a14-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Distribuire la qualità delle chiamate-regole di autorizzazione in IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="41a14-227">L'icona delle regole di autorizzazione non deve essere confusa con l'"autorizzazione .NET" nella sezione ASP.NET, che è un meccanismo di autorizzazione diverso.</span><span class="sxs-lookup"><span data-stu-id="41a14-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="41a14-228">Gli amministratori devono prima rimuovere la regola "Consenti a tutti gli utenti" ereditata.</span><span class="sxs-lookup"><span data-stu-id="41a14-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="41a14-229">In questo modo si evita che gli utenti non autorizzati accedano al portale.</span><span class="sxs-lookup"><span data-stu-id="41a14-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Distribuire CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="41a14-231">Successivamente, gli amministratori devono aggiungere nuove regole Allow e fornire agli utenti specifici l'autorizzazione per accedere al portale.</span><span class="sxs-lookup"><span data-stu-id="41a14-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="41a14-232">È consigliabile creare un gruppo locale denominato "CQDPortalUsers" per gestire gli utenti.</span><span class="sxs-lookup"><span data-stu-id="41a14-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Distribuire Dashboard Qualità della chiamata](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="41a14-234">I dettagli di configurazione sono archiviati nella web.config che si trova nella directory fisica del portale.</span><span class="sxs-lookup"><span data-stu-id="41a14-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="41a14-235">Il passaggio successivo consiste nel configurare il dashboard di CQD.</span><span class="sxs-lookup"><span data-stu-id="41a14-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="41a14-236">Dopo che gli utenti sono stati autenticati da IIS, dovranno disporre delle autorizzazioni per i file nella directory CQD per accedere al contenuto del portale Web.</span><span class="sxs-lookup"><span data-stu-id="41a14-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="41a14-237">È possibile modificare gli elenchi ACL tramite la scheda sicurezza delle proprietà della directory CQD per aggiungere singoli utenti o gruppi. Tuttavia, l'approccio consigliato consiste nel lasciare intatto il file Permissions.</span><span class="sxs-lookup"><span data-stu-id="41a14-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="41a14-238">Modificare invece l'impostazione di IIS in modo da utilizzare il processo di lavoro IIS per accedere alla directory CQD indipendentemente dall'autenticazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="41a14-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="41a14-239">È importante modificare solo questa impostazione per l'applicazione CQD e non per le due applicazioni API: QoEDataService e QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="41a14-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="41a14-240">Configurazione dell'accesso ai file per il CQD (Dashboard)</span><span class="sxs-lookup"><span data-stu-id="41a14-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="41a14-241">Aprire l'editor di configurazione per CQD.</span><span class="sxs-lookup"><span data-stu-id="41a14-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Distribuire Dashboard Qualità della chiamata](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="41a14-243">In sezione scegliere **System. webserver/ServerRunTime**.</span><span class="sxs-lookup"><span data-stu-id="41a14-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Distribuire Dashboard Qualità della chiamata](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="41a14-245">Modificare authenticatedUserOverride in **UseWorkerProcessUser**.</span><span class="sxs-lookup"><span data-stu-id="41a14-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Distribuire dashboard qualità chiamata-editor di configurazione](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="41a14-247">Fare clic su **applica** sul lato destro della pagina.</span><span class="sxs-lookup"><span data-stu-id="41a14-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="41a14-248">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="41a14-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="41a14-249">Il CQD non Visualizza dati dopo la distribuzione</span><span class="sxs-lookup"><span data-stu-id="41a14-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="41a14-250">È possibile che venga visualizzato il messaggio di errore seguente:</span><span class="sxs-lookup"><span data-stu-id="41a14-250">You may receive the following error:</span></span>

<span data-ttu-id="41a14-251">*Non è stato possibile eseguire la query durante l'esecuzione del cubo. Utilizzare l'editor di query per modificare la query e risolvere eventuali problemi. Verificare inoltre che il cubo sia accessibile.*</span><span class="sxs-lookup"><span data-stu-id="41a14-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="41a14-252">Questo significa che il cubo deve essere elaborato in SQL Server Analysis Services prima di essere utilizzato in CQD.</span><span class="sxs-lookup"><span data-stu-id="41a14-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="41a14-253">È possibile risolverlo attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="41a14-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="41a14-254">Aprire SQL Management Studio e selezionare **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="41a14-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="41a14-255">Espandere l'oggetto **QoECube** , selezionare **metriche QoE**, fare clic con il pulsante destro del mouse e scegliere **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="41a14-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="41a14-256">Se viene restituito il browser vuoto, il cubo non è stato ancora proceduto.</span><span class="sxs-lookup"><span data-stu-id="41a14-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="41a14-257">Fare clic con il pulsante destro del mouse su angain **metriche QoE** e scegliere **processo**.</span><span class="sxs-lookup"><span data-stu-id="41a14-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="41a14-258">Al termine dell'elaborazione, fare di nuovo clic con il pulsante destro del mouse sull'oggetto e scegliere **Sfoglia** per confermare che la pagina del browser visualizzi ora i dati.</span><span class="sxs-lookup"><span data-stu-id="41a14-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="41a14-259">Gli utenti hanno problemi di accesso perché il programma di installazione non riesce a creare le impostazioni corrette in IIS</span><span class="sxs-lookup"><span data-stu-id="41a14-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="41a14-260">In rari casi, il programma di installazione non è in grado di creare le impostazioni corrette in IIS.</span><span class="sxs-lookup"><span data-stu-id="41a14-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="41a14-261">La modifica manuale è necessaria per consentire agli utenti di accedere a CQD.</span><span class="sxs-lookup"><span data-stu-id="41a14-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="41a14-262">Se si verificano problemi di accesso per gli utenti, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="41a14-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="41a14-263">Aprire Gestione IIS e passare al sito Web predefinito.</span><span class="sxs-lookup"><span data-stu-id="41a14-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Distribuire Dashboard Qualità della chiamata](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="41a14-265">Fare clic su "autenticazione".</span><span class="sxs-lookup"><span data-stu-id="41a14-265">Click on "Authentication".</span></span> <span data-ttu-id="41a14-266">Se l'autenticazione anonima, la rappresentazione di ASP.NET, l'autenticazione basata su form e l'autenticazione di Windows non corrispondono alle impostazioni riportate di seguito, modificarle manualmente in modo che corrispondano alle impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="41a14-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="41a14-267">Tutti gli altri meccanismi di autenticazione devono essere disattivati.</span><span class="sxs-lookup"><span data-stu-id="41a14-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![Distribuire Dashboard Qualità della chiamata](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="41a14-269">Per "autenticazione di Windows", fare clic su Impostazioni avanzate sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="41a14-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Distribuire Dashboard Qualità della chiamata](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="41a14-271">Impostare "Extended Protection" per accettare e selezionare la casella di controllo Abilita autenticazione in modalità kernel.</span><span class="sxs-lookup"><span data-stu-id="41a14-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Distribuire Dashboard Qualità della chiamata](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="41a14-273">Ripetere i passaggi precedenti per ognuna delle voci "CQD", "QoEDataService" e "QoERepositoryService" sotto "sito Web predefinito".</span><span class="sxs-lookup"><span data-stu-id="41a14-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="41a14-274">Per i binding delle porte HTTP e HTTPS, il programma di installazione creerà i binding delle porte sui numeri di porta predefiniti (porta 80 per HTTP e la porta 443 per HTTPS).</span><span class="sxs-lookup"><span data-stu-id="41a14-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="41a14-275">Se nel computer è presente un altro sito Web che utilizza questi binding, si verificherà un conflitto e non sarà possibile prevedere il comportamento IIS.</span><span class="sxs-lookup"><span data-stu-id="41a14-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="41a14-276">Il modo migliore per evitare questo problema consiste nel verificare che non vengano mappati altri siti Web alle porte 80 e 443 prima di installare CQD.</span><span class="sxs-lookup"><span data-stu-id="41a14-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="41a14-277">Per abilitare SSL/TLS in IIS e imporre agli utenti di connettersi tramite HTTPS sicuro anziché HTTP:</span><span class="sxs-lookup"><span data-stu-id="41a14-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="41a14-278">Configure Secure Sockets Layer in IIS, vedere [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="41a14-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="41a14-279">Una volta fatto, Sostituisci  `http` con `https` .</span><span class="sxs-lookup"><span data-stu-id="41a14-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="41a14-280">Per istruzioni sull'abilitazione di TLS nelle connessioni a SQL Server, vedere [How to Enable SSL Encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span><span class="sxs-lookup"><span data-stu-id="41a14-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="41a14-281">Errore di sincronizzazione del cubo</span><span class="sxs-lookup"><span data-stu-id="41a14-281">Cube Sync Fails</span></span>

<span data-ttu-id="41a14-282">QoEMetrics potrebbe contenere alcuni record non validi basati su Clock degli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="41a14-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="41a14-283">Se l'inclinazione temporale è maggiore di 60 anni, l'importazione del cubo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="41a14-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="41a14-284">Controllare le opzioni di min e Max StartTime/EndTime utilizzando le selezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="41a14-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="41a14-285">Cercare ed eliminare i record in un futuro molto passato e molto lontano, possono essere ignorati e suddividere i processi di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="41a14-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="41a14-286">Selezionare MIN (StartTime) da CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="41a14-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="41a14-287">Seleziona massimo (StartTime) da CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="41a14-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="41a14-288">Selezionare MIN (EndTime) da CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="41a14-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="41a14-289">Seleziona massimo (EndTime) da CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="41a14-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="41a14-290">Attività successive all'installazione</span><span class="sxs-lookup"><span data-stu-id="41a14-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="41a14-291">Importazione di edifici e reti</span><span class="sxs-lookup"><span data-stu-id="41a14-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="41a14-292">Dopo l'installazione di CQD, eseguire le attività di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="41a14-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="41a14-293">Definire i tipi di edifici (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="41a14-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="41a14-294">Definire i tipi di proprietà degli edifici (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="41a14-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="41a14-295">Definire i tipi di rete (altamente consigliato)</span><span class="sxs-lookup"><span data-stu-id="41a14-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="41a14-296">Importare edifici (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="41a14-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="41a14-297">Importare le subnet (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="41a14-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="41a14-298">Definire i tipi di edifici</span><span class="sxs-lookup"><span data-stu-id="41a14-298">Define Building Types</span></span>

<span data-ttu-id="41a14-299">I tipi di compilazione vengono utilizzati per descrivere le diverse definizioni o tipi di edifici all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="41a14-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="41a14-300">Questo passaggio è facoltativo, ma è consigliato.</span><span class="sxs-lookup"><span data-stu-id="41a14-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="41a14-301">Esempi</span><span class="sxs-lookup"><span data-stu-id="41a14-301">Examples</span></span>
  
- <span data-ttu-id="41a14-302">Headquarters</span><span class="sxs-lookup"><span data-stu-id="41a14-302">Headquarters</span></span>
    
- <span data-ttu-id="41a14-303">Office remoto</span><span class="sxs-lookup"><span data-stu-id="41a14-303">Remote Office</span></span>
    
- <span data-ttu-id="41a14-304">Percorso joint-venture</span><span class="sxs-lookup"><span data-stu-id="41a14-304">Joint-venture location</span></span>
    
  <span data-ttu-id="41a14-305">**Sintassi SQL di esempio**</span><span class="sxs-lookup"><span data-stu-id="41a14-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="41a14-306">I parametri BuildingTypeId e BuildingTypeDesc sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="41a14-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="41a14-307">Definire i tipi di proprietà dell'edificio</span><span class="sxs-lookup"><span data-stu-id="41a14-307">Define Building Ownership Types</span></span>

<span data-ttu-id="41a14-308">I tipi di proprietà vengono utilizzati per distinguere le risorse possedute e quelle affittate.</span><span class="sxs-lookup"><span data-stu-id="41a14-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="41a14-309">Questo passaggio è facoltativo, ma è consigliato.</span><span class="sxs-lookup"><span data-stu-id="41a14-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="41a14-310">Esempi</span><span class="sxs-lookup"><span data-stu-id="41a14-310">Examples</span></span>
  
- <span data-ttu-id="41a14-311">Contoso leased non RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="41a14-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="41a14-312">Contoso leased RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="41a14-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="41a14-313">Contoso posseduto</span><span class="sxs-lookup"><span data-stu-id="41a14-313">Contoso Owned</span></span>
    
- <span data-ttu-id="41a14-314">Filiale affittata</span><span class="sxs-lookup"><span data-stu-id="41a14-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="41a14-315">**Sintassi SQL di esempio**</span><span class="sxs-lookup"><span data-stu-id="41a14-315">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

<span data-ttu-id="41a14-316">I parametri OwnershipTypeId e OwnershipTypeDesc sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="41a14-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="41a14-317">Definire i nomi di rete</span><span class="sxs-lookup"><span data-stu-id="41a14-317">Define Network Names</span></span>

<span data-ttu-id="41a14-318">I tipi di rete vengono utilizzati per descrivere diversi tipi di reti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="41a14-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="41a14-319">In questo modo è possibile filtrare (o escludere) tipi di rete specifici.</span><span class="sxs-lookup"><span data-stu-id="41a14-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="41a14-320">È consigliabile definire i nomi di rete, ma è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="41a14-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="41a14-321">Se si decide di non definire i nomi di rete, assicurarsi che ogni voce di CqdNetwork abbia un BuildingId pari a 0.</span><span class="sxs-lookup"><span data-stu-id="41a14-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="41a14-322">Esempi</span><span class="sxs-lookup"><span data-stu-id="41a14-322">Examples</span></span>
  
- <span data-ttu-id="41a14-323">VPN</span><span class="sxs-lookup"><span data-stu-id="41a14-323">VPN</span></span>
    
- <span data-ttu-id="41a14-324">DEL laboratorio</span><span class="sxs-lookup"><span data-stu-id="41a14-324">LAB</span></span>
    
  <span data-ttu-id="41a14-325">**Sintassi SQL di esempio**</span><span class="sxs-lookup"><span data-stu-id="41a14-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="41a14-326">I parametri NetworkNameID e NetworkName sono obbligatori, il parametro NetworkType è facoltativo ma consigliato.</span><span class="sxs-lookup"><span data-stu-id="41a14-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="41a14-327">Importare edifici</span><span class="sxs-lookup"><span data-stu-id="41a14-327">Import Buildings</span></span>

<span data-ttu-id="41a14-328">L'importazione di edifici offre la possibilità di ottenere informazioni specifiche sull'edificio (chiamate insufficienti per ogni edificio su WiFi/Wired, ecc.).</span><span class="sxs-lookup"><span data-stu-id="41a14-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="41a14-329">Questo passaggio è facoltativo, ma è consigliato.</span><span class="sxs-lookup"><span data-stu-id="41a14-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="41a14-330">Prima di importare un nuovo edificio, è necessario che sia già stato identificato un BuildingKey predefinito.</span><span class="sxs-lookup"><span data-stu-id="41a14-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="41a14-331">A tale scopo, eseguire il comando SQL "SELECT MAX (BuildingKey) FROM CqdBuilding" per identificare il valore corrente e aggiungere 1 al risultato.</span><span class="sxs-lookup"><span data-stu-id="41a14-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="41a14-332">**Sintassi SQL di esempio**</span><span class="sxs-lookup"><span data-stu-id="41a14-332">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

<span data-ttu-id="41a14-333">I parametri BuildingKey, Buildingname, BuildingShortName, OwnershipTypeId, BuildingTypeId sono obbligatori, mentre gli altri parametri sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="41a14-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="41a14-334">Importare le subnet</span><span class="sxs-lookup"><span data-stu-id="41a14-334">Import Subnets</span></span>

<span data-ttu-id="41a14-335">L'importazione di edifici offre la possibilità di ottenere informazioni specifiche sull'edificio (chiamate insufficienti per ogni edificio su WiFi/Wired, ecc.).</span><span class="sxs-lookup"><span data-stu-id="41a14-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="41a14-336">Questo passaggio è facoltativo, ma è consigliato.</span><span class="sxs-lookup"><span data-stu-id="41a14-336">This step is optional, but recommended.</span></span>
  
<span data-ttu-id="41a14-337">Importare le subnet e mapparle agli edifici importati nell'ultimo passaggio.</span><span class="sxs-lookup"><span data-stu-id="41a14-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="41a14-338">Se si è deciso di non popolare NetworkName, assicurarsi che ogni voce della tabella utilizzi un NetworkNameID di 0.</span><span class="sxs-lookup"><span data-stu-id="41a14-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span> <span data-ttu-id="41a14-339">Per ulteriori informazioni sulla sintassi e sui parametri SQL per il dashboard qualità chiamata, vedere [Use Call Quality dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use).</span><span class="sxs-lookup"><span data-stu-id="41a14-339">For more information on SQL syntax and parameters for the Call Quality Dashboard, see [Use Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use).</span></span>
  
 <span data-ttu-id="41a14-340">**Sintassi SQL di esempio**</span><span class="sxs-lookup"><span data-stu-id="41a14-340">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkRange]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',32,0,1,'2015-11-11')
```

<span data-ttu-id="41a14-341">I parametri Network e UpdatedDate sono obbligatori, mentre gli altri parametri sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="41a14-341">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="41a14-342">Facoltativo: BSSID</span><span class="sxs-lookup"><span data-stu-id="41a14-342">Optional: BSSID</span></span>

<span data-ttu-id="41a14-343">La compilazione delle informazioni di BSSID offre una correlazione di flusso WiFi supplementare tramite controller o radio.</span><span class="sxs-lookup"><span data-stu-id="41a14-343">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="41a14-344">Questo è oltre a filtrare in base all'edificio o alla subnet.</span><span class="sxs-lookup"><span data-stu-id="41a14-344">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="41a14-345">**Sintassi SQL di esempio**</span><span class="sxs-lookup"><span data-stu-id="41a14-345">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

<span data-ttu-id="41a14-346">**Dettagli CqdBssidTable**</span><span class="sxs-lookup"><span data-stu-id="41a14-346">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="41a14-347">**Come illustrato in CQD**</span><span class="sxs-lookup"><span data-stu-id="41a14-347">**As shown in CQD**</span></span>|<span data-ttu-id="41a14-348">**Tabella CQDBssid**</span><span class="sxs-lookup"><span data-stu-id="41a14-348">**CQDBssid Table**</span></span>|<span data-ttu-id="41a14-349">**Input di esempio**</span><span class="sxs-lookup"><span data-stu-id="41a14-349">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41a14-350">AP NName</span><span class="sxs-lookup"><span data-stu-id="41a14-350">Ap NName</span></span>  <br/> |<span data-ttu-id="41a14-351">AP</span><span class="sxs-lookup"><span data-stu-id="41a14-351">AP</span></span>  <br/> |<span data-ttu-id="41a14-352">AP1</span><span class="sxs-lookup"><span data-stu-id="41a14-352">AP1</span></span>  <br/> |
|<span data-ttu-id="41a14-353">BBssid</span><span class="sxs-lookup"><span data-stu-id="41a14-353">BBssid</span></span>  <br/> |<span data-ttu-id="41a14-354">BSS</span><span class="sxs-lookup"><span data-stu-id="41a14-354">BSS</span></span>  <br/> |<span data-ttu-id="41a14-355">00-00-00-00-00-00 (è necessario utilizzare il utilizzare delimitato)</span><span class="sxs-lookup"><span data-stu-id="41a14-355">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="41a14-356">Controller</span><span class="sxs-lookup"><span data-stu-id="41a14-356">Controller</span></span>  <br/> |<span data-ttu-id="41a14-357">Creazione</span><span class="sxs-lookup"><span data-stu-id="41a14-357">Building</span></span>  <br/> |<span data-ttu-id="41a14-358">Aruba AP 7</span><span class="sxs-lookup"><span data-stu-id="41a14-358">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="41a14-359">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="41a14-359">Device</span></span>  <br/> |<span data-ttu-id="41a14-360">ESS</span><span class="sxs-lookup"><span data-stu-id="41a14-360">ess</span></span>  <br/> |<span data-ttu-id="41a14-361">Controller1</span><span class="sxs-lookup"><span data-stu-id="41a14-361">Controller1</span></span>  <br/> |
|<span data-ttu-id="41a14-362">Radio</span><span class="sxs-lookup"><span data-stu-id="41a14-362">Radio</span></span>  <br/> |<span data-ttu-id="41a14-363">PHY</span><span class="sxs-lookup"><span data-stu-id="41a14-363">phy</span></span>  <br/> |<span data-ttu-id="41a14-364">BGN</span><span class="sxs-lookup"><span data-stu-id="41a14-364">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="41a14-365">Elaborazione dei dati importati</span><span class="sxs-lookup"><span data-stu-id="41a14-365">Processing the imported data</span></span>

<span data-ttu-id="41a14-366">Per impostazione predefinita, dopo aver importato i dati di compilazione o di rete, l'applicazione verrà applicata solo ai record generati dopo quel momento.</span><span class="sxs-lookup"><span data-stu-id="41a14-366">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="41a14-367">Per contrassegnare tutti i record precedenti con i nuovi dati, sarà necessario eseguire la stored procedure CqdUpdateBuilding come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="41a14-367">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="41a14-368">Assegnare la data del primo record (identificare l'utilizzo del comando Seleziona MIN (StartTime) da CqdPartitionedStreamView SQL), una EndDate di domani, quindi NULL per gli ultimi due valori.</span><span class="sxs-lookup"><span data-stu-id="41a14-368">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="41a14-369">Dopo che i dati sono associati ai dati del flusso, è necessario che il cubo di SSIS rielabori tutti i record.</span><span class="sxs-lookup"><span data-stu-id="41a14-369">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="41a14-370">Questo vale anche per l'aggiunta di massa dei dati di BSSID/ISP.</span><span class="sxs-lookup"><span data-stu-id="41a14-370">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="41a14-371">Verificare che sia selezionata l'opzione "elaborazione completa".</span><span class="sxs-lookup"><span data-stu-id="41a14-371">Ensure that "Process Full" is selected.</span></span>
  

