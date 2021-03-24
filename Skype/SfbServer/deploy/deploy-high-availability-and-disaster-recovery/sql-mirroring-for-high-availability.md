---
title: Distribuire SQL mirroring per la disponibilità elevata del server back-end in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Per distribuire il mirroring SQL, i server devono eseguire almeno SQL Server 2008 R2. Questa versione deve essere eseguita da tutti i server coinvolti: il server primario, mirror, e di controllo. Per informazioni dettagliate, vedere Cumulative update package 9 for SQL Server 2008 Service Pack 1 .'
ms.openlocfilehash: 38c3e749b39cd510623232e9f29ace03a1c19f6c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100722"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="4701c-105">Distribuire SQL mirroring per la disponibilità elevata del server back-end in Skype for Business server 2015</span><span class="sxs-lookup"><span data-stu-id="4701c-105">Deploy SQL mirroring for Back End Server high availability in Skype for Business server 2015</span></span>


<span data-ttu-id="4701c-106">Per distribuire il mirroring SQL, i server devono eseguire almeno SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="4701c-106">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="4701c-107">Questa versione deve essere eseguita da tutti i server coinvolti: il server primario, mirror, e di controllo.</span><span class="sxs-lookup"><span data-stu-id="4701c-107">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="4701c-108">Per informazioni dettagliate, vedere [Cumulative update package 9 for SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span><span class="sxs-lookup"><span data-stu-id="4701c-108">For details, see [Cumulative update package 9 for SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span></span>

<span data-ttu-id="4701c-109">In generale, la configurazione del mirroring SQL tra due server di back-end con un server di controllo richiede che:</span><span class="sxs-lookup"><span data-stu-id="4701c-109">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

- <span data-ttu-id="4701c-110">La versione del server primario di SQL Server deve supportare SQL mirroring.</span><span class="sxs-lookup"><span data-stu-id="4701c-110">The primary server's version of SQL Server must support SQL mirroring.</span></span>

- <span data-ttu-id="4701c-111">I server primario, mirror e di controllo (se distribuito) abbiano la stessa versione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4701c-111">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

- <span data-ttu-id="4701c-p103">Il server primario e mirror abbiano la stessa edizione di SQL Server. Il server di controllo può avere un'edizione diversa.</span><span class="sxs-lookup"><span data-stu-id="4701c-p103">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="4701c-114">Per SQL procedure consigliate in termini di versioni SQL supportate per un ruolo di controllo, vedere [Database Mirroring Witness](/sql/database-engine/database-mirroring/database-mirroring-witness).</span><span class="sxs-lookup"><span data-stu-id="4701c-114">For SQL best practices in terms of what SQL versions are supported for a Witness role, see [Database Mirroring Witness](/sql/database-engine/database-mirroring/database-mirroring-witness).</span></span>

<span data-ttu-id="4701c-115">È possibile utilizzare Generatore di topologie per distribuire SQL mirroring.</span><span class="sxs-lookup"><span data-stu-id="4701c-115">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="4701c-116">È possibile selezionare un'opzione in Generatore di topologie per eseguire il mirroring dei database e Generatore di topologie configura il mirroring (inclusa la configurazione di un server di controllo, se necessario) quando si pubblica la topologia.</span><span class="sxs-lookup"><span data-stu-id="4701c-116">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="4701c-117">Il server di controllo viene rimosso o configurato contemporaneamente alla rimozione o configurazione del mirror.</span><span class="sxs-lookup"><span data-stu-id="4701c-117">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="4701c-118">Non esiste un comando separato che consente di distribuire o rimuovere unicamente un server di controllo.</span><span class="sxs-lookup"><span data-stu-id="4701c-118">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="4701c-119">Per configurare il mirroring del server, è prima necessario configurare correttamente le autorizzazioni del database SQL.</span><span class="sxs-lookup"><span data-stu-id="4701c-119">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="4701c-120">Per informazioni dettagliate, [vedere Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability).</span><span class="sxs-lookup"><span data-stu-id="4701c-120">For details, see [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability).</span></span>

<span data-ttu-id="4701c-121">Con il mirroring di SQL, la modalità di ripristino del database è sempre impostata su **Completo,** il che significa che è necessario monitorare attentamente le dimensioni del registro delle transazioni ed eseguire regolarmente il backup dei registri delle transazioni per evitare che lo spazio su disco sia insufficiente nei server back-end.</span><span class="sxs-lookup"><span data-stu-id="4701c-121">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers.</span></span> <span data-ttu-id="4701c-122">La frequenza dei backup del log delle transazioni dipende dal tasso di crescita del registro, che a sua volta dipende dalle transazioni di database sostenute dalle attività degli utenti nel pool Front End.</span><span class="sxs-lookup"><span data-stu-id="4701c-122">The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool.</span></span> <span data-ttu-id="4701c-123">È consigliabile determinare la quantità prevista di crescita del log delle transazioni per il carico di lavoro di distribuzione, in modo da poter eseguire la pianificazione di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="4701c-123">We recommend that you determine how much transaction log growth is expected for your deployment workload so that you can do the planning accordingly.</span></span> <span data-ttu-id="4701c-124">Gli articoli seguenti forniscono ulteriori informazioni sulla gestione SQL backup e log:</span><span class="sxs-lookup"><span data-stu-id="4701c-124">The following articles provide additional information on SQL backup and log management:</span></span>

- [<span data-ttu-id="4701c-125">Modelli di recupero del database</span><span class="sxs-lookup"><span data-stu-id="4701c-125">Database recovery models</span></span>](/sql/relational-databases/backup-restore/recovery-models-sql-server)

- [<span data-ttu-id="4701c-126">Panoramica del backup</span><span class="sxs-lookup"><span data-stu-id="4701c-126">Backup overview</span></span>](/sql/relational-databases/backup-restore/backup-overview-sql-server)

- [<span data-ttu-id="4701c-127">Backup del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="4701c-127">Backup transaction log</span></span>](/sql/relational-databases/backup-restore/back-up-a-transaction-log-sql-server)

<span data-ttu-id="4701c-128">Nel mirroring SQL è possibile configurare la topologia per il mirroring al momento della creazione dei pool, o in seguito.</span><span class="sxs-lookup"><span data-stu-id="4701c-128">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4701c-129">L'utilizzo di Generatore di topologie o cmdlet per configurare e rimuovere il mirroring di SQL è supportato solo quando i server primari, mirror e di controllo (se desiderato) appartengono tutti allo stesso dominio.</span><span class="sxs-lookup"><span data-stu-id="4701c-129">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="4701c-130">Per configurare il mirroring SQL tra server su domini diversi, vedere la documentazione relativa a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4701c-130">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4701c-131">Quando si apportano modifiche a una relazione di mirroring di un database di back end, è necessario riavviare tutti i Front End Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="4701c-131">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span> <span data-ttu-id="4701c-132">> Per una modifica del mirroring, ad esempio la modifica della posizione di un mirror, è necessario utilizzare Generatore di topologie per eseguire questi tre passaggi:</span><span class="sxs-lookup"><span data-stu-id="4701c-132">> For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span>

1. <span data-ttu-id="4701c-133">Rimuovere il mirroring dal server mirror meno recente.</span><span class="sxs-lookup"><span data-stu-id="4701c-133">Remove mirroring from the old mirror server.</span></span>

2. <span data-ttu-id="4701c-134">Aggiungere il mirroring al nuovo server mirror.</span><span class="sxs-lookup"><span data-stu-id="4701c-134">Add mirroring to the new mirror server.</span></span>

3. <span data-ttu-id="4701c-135">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="4701c-135">Publish the topology.</span></span>

> [!NOTE]
> <span data-ttu-id="4701c-136">È necessario creare una condivisione file per i file mirror in cui scrivere e il servizio che SQL Server e SQL Agent sono in esecuzione richiede l'accesso in lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="4701c-136">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="4701c-137">Se il servizio SQL Server è in esecuzione nel contesto di Servizio di rete, è possibile aggiungere \<Domain\> \\<SQLSERVERNAME $ dei server SQL Principal e Mirror alle autorizzazioni di \> condivisione.</span><span class="sxs-lookup"><span data-stu-id="4701c-137">If the SQL Server service is running under the context of Network Service, you can add \<Domain\>\\<SQLSERVERNAME\>$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="4701c-138">$ è importante per identificare che si tratta di un account computer.</span><span class="sxs-lookup"><span data-stu-id="4701c-138">The $ is important to identify that this is a computer account.</span></span>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="4701c-139">Per configurare SQL mirroring durante la creazione di un pool in Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="4701c-139">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1. <span data-ttu-id="4701c-140">Nella pagina **Definisci archivio SQL**, fare clic su **Nuovo** accanto alla casella **Archivio SQL**.</span><span class="sxs-lookup"><span data-stu-id="4701c-140">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2. <span data-ttu-id="4701c-141">Nella pagina **Definisci nuovo archivio SQL**, specificare l'archivio primario, selezionare **L'istanza SQL è in relazione di mirroring**, specificare il numero di porta del mirroring SQL (il valore predefinito è 5022), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4701c-141">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3. <span data-ttu-id="4701c-142">Nella pagina **Definisci archivio SQL**, selezionare **Abilita archivio mirroring SQL**.</span><span class="sxs-lookup"><span data-stu-id="4701c-142">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4. <span data-ttu-id="4701c-p110">Nella pagina **Definisci nuovo archivio SQL**, specificare l'archivio SQL da utilizzare come mirror. Selezionare **L'istanza SQL è in relazione di mirroring**, specificare il numero di porta (il valore predefinito è 5022), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4701c-p110">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="4701c-145">Se si desidera un'istanza di controllo per il mirror, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4701c-145">If you want a witness for this mirror, do the following:</span></span>

    <span data-ttu-id="4701c-146">a.</span><span class="sxs-lookup"><span data-stu-id="4701c-146">a.</span></span> <span data-ttu-id="4701c-147">Selezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico**.</span><span class="sxs-lookup"><span data-stu-id="4701c-147">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>

    <span data-ttu-id="4701c-148">b.</span><span class="sxs-lookup"><span data-stu-id="4701c-148">b.</span></span> <span data-ttu-id="4701c-149">Nella pagina **Definisci archivio SQL**, selezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** e specificare l'archivio SQL da utilizzare per il controllo.</span><span class="sxs-lookup"><span data-stu-id="4701c-149">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>

    <span data-ttu-id="4701c-150">c.</span><span class="sxs-lookup"><span data-stu-id="4701c-150">c.</span></span> <span data-ttu-id="4701c-151">Specificare il numero di porta (il valore predefinito è 7022) e fare clic su **OK**</span><span class="sxs-lookup"><span data-stu-id="4701c-151">Specify the port number (the default is 7022) and click **OK**.</span></span>

6. <span data-ttu-id="4701c-152">Dopo aver definito il pool Front End e tutti gli altri ruoli della topologia, utilizzare Generatore di topologie per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="4701c-152">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="4701c-153">Quando la topologia viene pubblicata, se nel pool Front End che ospita l'archivio di gestione centrale è abilitato il mirroring SQL, verrà visualizzata un'opzione per creare sia database di archiviazione primari che SQL mirror.</span><span class="sxs-lookup"><span data-stu-id="4701c-153">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>

    <span data-ttu-id="4701c-154">Fare clic su **Impostazioni** e digitare il percorso da utilizzare come condivisione file per il backup del mirroring.</span><span class="sxs-lookup"><span data-stu-id="4701c-154">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>

    <span data-ttu-id="4701c-p115">Fare clic su **OK** e **Avanti** per creare i database e pubblicare la topologia. I server di mirroring e di controllo (se specificato) saranno così distribuiti.</span><span class="sxs-lookup"><span data-stu-id="4701c-p115">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="4701c-157">È possibile utilizzare Generatore di topologie per modificare le proprietà di un pool già esistente per abilitare SQL mirroring.</span><span class="sxs-lookup"><span data-stu-id="4701c-157">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="4701c-158">Per aggiungere SQL mirroring a un pool Front End esistente in Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="4701c-158">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1. <span data-ttu-id="4701c-159">In Generatore di topologie fare clic con il pulsante destro del mouse sul pool e **quindi scegliere Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4701c-159">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2. <span data-ttu-id="4701c-160">Selezionare **Abilita mirroring dell'archivio SQL**, quindi fare clic su **Nuovo** accanto a **Mirroring dell'archivio SQL**.</span><span class="sxs-lookup"><span data-stu-id="4701c-160">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3. <span data-ttu-id="4701c-161">Specificare l'archivio SQL che si desidera utilizzare come mirror.</span><span class="sxs-lookup"><span data-stu-id="4701c-161">Specify the SQL store that you want to use as the mirror.</span></span>

4. <span data-ttu-id="4701c-162">Selezionare **L'istanza SQL è in relazione di mirroring**, specificare il numero di porta per il mirroring SQL (il valore predefinito è 5022), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4701c-162">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="4701c-163">Per configurare un'istanza di controllo, selezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** e fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4701c-163">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6. <span data-ttu-id="4701c-164">Specificare l'archivio SQL che si desidera utilizzare come istanza di controllo.</span><span class="sxs-lookup"><span data-stu-id="4701c-164">Specify the SQL store that you want to use as the witness.</span></span>

7. <span data-ttu-id="4701c-165">Selezionare **L'istanza SQL è in relazione di mirroring**, specificare il numero di porta per il mirroring SQL (il valore predefinito è 7022), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4701c-165">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8. <span data-ttu-id="4701c-166">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4701c-166">Click **OK**.</span></span>

9. <span data-ttu-id="4701c-p116">Pubblicare la topologia. Verrà richiesto di installare il database.</span><span class="sxs-lookup"><span data-stu-id="4701c-p116">Publish the topology. When you do so, you will be prompted to install the database.</span></span>

    <span data-ttu-id="4701c-169">Durante il processo di pubblicazione della topologia verrà richiesto di definire un percorso di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="4701c-169">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="4701c-170">I SQL server che partecipano al mirroring devono disporre dell'accesso in lettura/scrittura a questa condivisione file per poter stabilire il mirror.</span><span class="sxs-lookup"><span data-stu-id="4701c-170">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="4701c-171">A questo punto è necessario installare il database prima di passare alla procedura successiva.</span><span class="sxs-lookup"><span data-stu-id="4701c-171">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="4701c-172">Quando si configura il mirroring SQL, è necessario tenere a mente alcuni punti:</span><span class="sxs-lookup"><span data-stu-id="4701c-172">You should keep the following in mind when setting up SQL mirroring:</span></span>

- <span data-ttu-id="4701c-173">Se esiste già un endpoint del mirroring, sarà riutilizzato insieme alle porte definite qui, e saranno ignorate quelle specificate nella topologia.</span><span class="sxs-lookup"><span data-stu-id="4701c-173">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

- <span data-ttu-id="4701c-p118">Le porte già allocate ad altre applicazioni sullo stesso server, comprese quelle allocate ad altre istanze di SQL, non devono essere utilizzate per le nuove istanze di SQL installate. Pertanto, se si ha più di una istanza SQL installata sullo stesso server, queste devono utilizzare porte differenti per il mirroring. Per ulteriori dettagli, vedere:</span><span class="sxs-lookup"><span data-stu-id="4701c-p118">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>

  - [<span data-ttu-id="4701c-177">Specificare un indirizzo di rete del server (mirroring del database)</span><span class="sxs-lookup"><span data-stu-id="4701c-177">Specify a Server Network Address (Database Mirroring)</span></span>](/sql/database-engine/database-mirroring/specify-a-server-network-address-database-mirroring)

  - [<span data-ttu-id="4701c-178">Endpoint del mirroring del database (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4701c-178">The Database Mirroring Endpoint (SQL Server)</span></span>](/sql/database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="4701c-179">Utilizzo dei cmdlet di Skype for Business Server 2015 Management Shell per configurare SQL mirroring</span><span class="sxs-lookup"><span data-stu-id="4701c-179">Using Skype for Business Server 2015 Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="4701c-180">Il modo più semplice per configurare il mirroring è utilizzare Generatore di topologie, ma è possibile farlo anche utilizzando i cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4701c-180">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1. <span data-ttu-id="4701c-181">Aprire una finestra di Skype for Business Server 2015 Management Shell ed eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="4701c-181">Open a Skype for Business Server 2015 Management Shell window and run the following cmdlet:</span></span>

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    <span data-ttu-id="4701c-182">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4701c-182">For example:</span></span>

   ```powershell
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    <span data-ttu-id="4701c-183">Verrà visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4701c-183">You will see the following:</span></span>

   <pre>
   Database Name:rtcxds
        Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf
         Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:rtcshared
        Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf
         Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:rtcab
        Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf
         Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:rgsconfig
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:rgsdyn
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:cpsdyn
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:xds
        Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf
         Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:lis
        Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf
         Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
   [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
   </pre>

2. <span data-ttu-id="4701c-184">Verificare che:</span><span class="sxs-lookup"><span data-stu-id="4701c-184">Verify the following:</span></span>

    - <span data-ttu-id="4701c-185">La Porta 5022 sia accessibile attraverso il firewall se Windows Firewall è abilitato sel server SQL primario e04-ocs.los_a.lsipt.local\rtc.</span><span class="sxs-lookup"><span data-stu-id="4701c-185">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="4701c-186">La Porta 5022 sia accessibile attraverso il firewall se Windows Firewall è abilitato sel server SQL mirror K16-ocs.los_a.lsipt.local\rtc.</span><span class="sxs-lookup"><span data-stu-id="4701c-186">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="4701c-187">La Porta 7022 sia accessibile attraverso il firewall se Windows Firewall è abilitato sel server SQL di controllo AB14-lct.los_a.lsipt.local\rtc.</span><span class="sxs-lookup"><span data-stu-id="4701c-187">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los_a.lsipt.local\rtc.</span></span>

   - <span data-ttu-id="4701c-188">Gli account che eseguono SQL Server in tutti i server SQL primario e mirror dispongono dell'autorizzazione di lettura/scrittura per la condivisione file \\ E04-OCS\csdatabackup</span><span class="sxs-lookup"><span data-stu-id="4701c-188">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\E04-OCS\csdatabackup</span></span>

   - <span data-ttu-id="4701c-p119">Verificare che il provider della Strumentazione gestione Windows (WMI) sia eseguito su tutti questi server. Il cmdlet si serve di questo provider per trovare le informazioni sull'account relative ai servizi di SQL Server eseguiti su tutti i server primari, mirror e di controllo.</span><span class="sxs-lookup"><span data-stu-id="4701c-p119">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>

   - <span data-ttu-id="4701c-191">Verificare che l'account sul quale è eseguito il cmdlet abbia le autorizzazioni necessarie per creare le cartelle per i dati e i file dei log per tutti i server mirror.</span><span class="sxs-lookup"><span data-stu-id="4701c-191">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>

   - <span data-ttu-id="4701c-p120">Si noti che l'account utente utilizzato dall'istanza SQL per la propria esecuzione deve essere dotato di autorizzazioni di lettura e scrittura per la condivisione file. Se la condivisione file si trova su un server diverso e l'istanza SQL esegue un account di sistema locale, è necessario concedere autorizzazioni per la condivisione file al server che ospita l'istanza SQL.</span><span class="sxs-lookup"><span data-stu-id="4701c-p120">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3. <span data-ttu-id="4701c-194">Digitare A e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="4701c-194">Type A and press ENTER.</span></span>

    <span data-ttu-id="4701c-195">Sarà configurato il mirroring.</span><span class="sxs-lookup"><span data-stu-id="4701c-195">The mirroring will be configured.</span></span>

    <span data-ttu-id="4701c-196">**Install-CsMirrorDatabase** installa il mirror e configura il mirroring per tutti i database presenti nell'archivio SQL principale.</span><span class="sxs-lookup"><span data-stu-id="4701c-196">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="4701c-197">Se si desidera configurare il mirroring solo per database specifici, è possibile utilizzare l'opzione -DatabaseType oppure, se si desidera configurare il mirroring per tutti i database ad eccezione di alcuni, è possibile utilizzare l'opzione -ExcludeDatabaseList, insieme a un elenco delimitato da virgole di nomi di database da escludere.</span><span class="sxs-lookup"><span data-stu-id="4701c-197">If you want to configure mirroring for only specific databases, you can use the -DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

    <span data-ttu-id="4701c-198">Ad esempio, se si aggiunge l'opzione seguente a **Install-CsMirrorDatabase**, si eseguirà il mirroring per tutti i database ad eccezione di rtcab e rtcxds.</span><span class="sxs-lookup"><span data-stu-id="4701c-198">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

    `-ExcludeDatabaseList rtcab,rtcxds`

   <span data-ttu-id="4701c-199">Ad esempio, se si aggiunge l'opzione seguente a **Install-CsMirrorDatabase**, si eseguirà il mirroring unicamente per i database rtcab e rtcxds.</span><span class="sxs-lookup"><span data-stu-id="4701c-199">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="4701c-200">Rimozione o modifica del mirroring SQL</span><span class="sxs-lookup"><span data-stu-id="4701c-200">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="4701c-p122">Per rimuovere il mirroring SQL da un pool in Generatore di topologie, è prima necessario utilizzare un cmdlet per la rimozione del mirror in SQL Server. È quindi possibile utilizzare Generatore di topologie per rimuovere il mirror dalla topologia. Per rimuovere il mirror in SQL Server, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="4701c-p122">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

<span data-ttu-id="4701c-204">Ad esempio, per rimuovere il mirroring ed eliminare i database degli utenti, digitare:</span><span class="sxs-lookup"><span data-stu-id="4701c-204">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

<span data-ttu-id="4701c-205">L'opzione determina l'eliminazione dei database  `-DropExistingDatabasesOnMirror` interessati dal mirror.</span><span class="sxs-lookup"><span data-stu-id="4701c-205">The  `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="4701c-206">Per rimuovere il mirror dalla topology, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4701c-206">Then, to remove the mirror from the topology, do the following:</span></span>

1. <span data-ttu-id="4701c-207">In Generatore di topologie, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4701c-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="4701c-208">Deselezionare **Abilita archivio mirroring SQL** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4701c-208">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3. <span data-ttu-id="4701c-209">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="4701c-209">Publish the topology.</span></span>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="4701c-210">Rimozione di un Server di controllo del mirroring</span><span class="sxs-lookup"><span data-stu-id="4701c-210">Removing a Mirroring Witness</span></span>

<span data-ttu-id="4701c-211">Utilizzare questa procedura se è necessario rimuovere il server di controllo da una configurazione di mirroring del server back-end.</span><span class="sxs-lookup"><span data-stu-id="4701c-211">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1. <span data-ttu-id="4701c-212">In Generatore di topologie, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4701c-212">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="4701c-213">Deselezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4701c-213">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3. <span data-ttu-id="4701c-214">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="4701c-214">Publish the topology.</span></span>

    <span data-ttu-id="4701c-215">Dopo aver pubblicato la topologia, in Generatore di topologie verrà visualizzato un messaggio che include quanto segue</span><span class="sxs-lookup"><span data-stu-id="4701c-215">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    <span data-ttu-id="4701c-216">Tuttavia, non seguire questo passaggio e non digitare in modo da disinstallare  `Uninstall-CsMirrorDatabase` l'intera configurazione del mirroring.</span><span class="sxs-lookup"><span data-stu-id="4701c-216">However, do not follow that step, and do not type  `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4. <span data-ttu-id="4701c-217">Per rimuovere solo il controllo dalla configurazione SQL Server, seguire le istruzioni in [Remove the Witness from a Database Mirroring Session (SQL Server)](/sql/database-engine/database-mirroring/remove-the-witness-from-a-database-mirroring-session-sql-server).</span><span class="sxs-lookup"><span data-stu-id="4701c-217">To remove just the witness from the SQL Server configuration, follow the instructions in [Remove the Witness from a Database Mirroring Session (SQL Server)](/sql/database-engine/database-mirroring/remove-the-witness-from-a-database-mirroring-session-sql-server).</span></span>