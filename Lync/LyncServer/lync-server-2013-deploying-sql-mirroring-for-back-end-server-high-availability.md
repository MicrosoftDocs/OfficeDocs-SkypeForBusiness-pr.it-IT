---
title: Distribuzione del mirroring di SQL per la disponibilità elevata del server back-end
description: Distribuzione del mirroring di SQL per la disponibilità elevata del server back-end.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a2ab2d598249c12231668a888b442f830c5d65f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566002"
---
# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="8f30e-103">Distribuzione del mirroring di SQL per la disponibilità elevata del server back-end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f30e-103">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f30e-104">_**Ultimo argomento modificato:** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="8f30e-104">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="8f30e-105">Per distribuire il mirroring SQL, i server devono eseguire almeno SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="8f30e-105">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="8f30e-106">Questa versione deve essere eseguita da tutti i server coinvolti: il server primario, mirror, e di controllo.</span><span class="sxs-lookup"><span data-stu-id="8f30e-106">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="8f30e-107">Per informazioni dettagliate, vedere [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921) .</span><span class="sxs-lookup"><span data-stu-id="8f30e-107">For details, see [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="8f30e-108">In generale, la configurazione del mirroring SQL tra due server di back-end con un server di controllo richiede che:</span><span class="sxs-lookup"><span data-stu-id="8f30e-108">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="8f30e-109">La versione di SQL Server del server primario supporti il mirroring SQL.</span><span class="sxs-lookup"><span data-stu-id="8f30e-109">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="8f30e-110">I server primario, mirror e di controllo (se distribuito) abbiano la stessa versione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8f30e-110">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="8f30e-p102">Il server primario e mirror abbiano la stessa edizione di SQL Server. Il server di controllo può avere un'edizione diversa.</span><span class="sxs-lookup"><span data-stu-id="8f30e-p102">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="8f30e-113">Per le procedure consigliate SQL in termini di supporto per le versioni di SQL per un ruolo di controllo, vedere "database mirroring witness" in MSDN Library all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345) .</span><span class="sxs-lookup"><span data-stu-id="8f30e-113">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="8f30e-114">È possibile utilizzare Generatore di topologie per distribuire il mirroring SQL.</span><span class="sxs-lookup"><span data-stu-id="8f30e-114">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="8f30e-115">È possibile selezionare un'opzione in Generatore di topologie per il mirroring dei database e il generatore di topologie configura il mirroring, inclusa la configurazione di un controllo, se si desidera, quando si pubblica la topologia.</span><span class="sxs-lookup"><span data-stu-id="8f30e-115">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="8f30e-116">Il server di controllo viene rimosso o configurato contemporaneamente alla rimozione o configurazione del mirror.</span><span class="sxs-lookup"><span data-stu-id="8f30e-116">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="8f30e-117">Non esiste un comando separato che consente di distribuire o rimuovere unicamente un server di controllo.</span><span class="sxs-lookup"><span data-stu-id="8f30e-117">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="8f30e-118">Per configurare il mirroring del server, è prima necessario configurare correttamente le autorizzazioni del database SQL.</span><span class="sxs-lookup"><span data-stu-id="8f30e-118">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="8f30e-119">Per informazioni dettagliate, vedere "configurare gli account di accesso per il mirroring del database o i gruppi di disponibilità AlwaysOn (SQL Server)" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454) .</span><span class="sxs-lookup"><span data-stu-id="8f30e-119">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="8f30e-p105">Con il mirroring SQL, la modalità di recupero del database è impostata sempre su **Completa**. Ciò significa che è necessario monitorare le dimensioni del log delle transizioni ed eseguire regolarmente il backup dei log più grandi, per evitare che la memoria del disco dei server di back-end si riempia. La frequenza dei backup dei log delle transizioni dipende dal tasso di crescita dei log, che a sua volta dipende dalle transazioni del database relative alle attività degli utenti nel pool Front End. Per pianificare correttamente, è consigliabile determinare il tasso di crescita stimato del log delle transazioni per il carico di lavoro della distribuzione di Lync. I seguenti articoli contengono informazioni aggiuntive sul backup SQL e la gestione dei log:</span><span class="sxs-lookup"><span data-stu-id="8f30e-p105">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="8f30e-124">Modelli di ripristino di database: "modelli di ripristino (SQL Server)" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="8f30e-124">Database recovery models: "Recovery Models (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="8f30e-125">Panoramica del backup: "Panoramica del backup (SQL Server)" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="8f30e-125">Backup overview: "Backup Overview (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="8f30e-126">Log delle transazioni di backup: "eseguire il backup di un log delle transazioni (SQL Server)" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="8f30e-126">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="8f30e-127">Nel mirroring SQL è possibile configurare la topologia per il mirroring al momento della creazione dei pool, o in seguito.</span><span class="sxs-lookup"><span data-stu-id="8f30e-127">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="8f30e-128">L'utilizzo di generatore di topologie o cmdlet per configurare e rimuovere il mirroring SQL è supportato solo quando i server primari, mirror e Witness (se necessario) appartengono tutti allo stesso dominio.</span><span class="sxs-lookup"><span data-stu-id="8f30e-128">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="8f30e-129">Per configurare il mirroring SQL tra server su domini diversi, vedere la documentazione relativa a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8f30e-129">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="8f30e-130">Quando si apportano modifiche a una relazione di mirroring di un database di back end, è necessario riavviare tutti i Front End Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="8f30e-130">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="8f30e-131">Per una modifica del mirroring, ad esempio la modifica del percorso di un mirror, è necessario utilizzare Generatore di topologie per eseguire questi tre passaggi:</span><span class="sxs-lookup"><span data-stu-id="8f30e-131">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="8f30e-132">Rimuovere il mirroring dal server mirror meno recente.</span><span class="sxs-lookup"><span data-stu-id="8f30e-132">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="8f30e-133">Aggiungere il mirroring al nuovo server mirror.</span><span class="sxs-lookup"><span data-stu-id="8f30e-133">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="8f30e-134">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="8f30e-134">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="8f30e-135">È necessario creare una condivisione file per la scrittura dei file mirror e il servizio in cui SQL Server e SQL Agent sono in esecuzione in accesso in lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="8f30e-135">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="8f30e-136">Se il servizio SQL Server è in esecuzione nel contesto di servizio di rete, è possibile aggiungere il &lt; dominio &gt;&#92;&lt; sqlservername &gt; $ dei server SQL Principal e mirror alle autorizzazioni di condivisione.</span><span class="sxs-lookup"><span data-stu-id="8f30e-136">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="8f30e-137">$ È importante per identificare che si tratta di un account computer.</span><span class="sxs-lookup"><span data-stu-id="8f30e-137">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="8f30e-138">Per configurare il mirroring SQL durante la creazione di un pool in Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="8f30e-138">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="8f30e-139">Nella pagina **Definisci archivio SQL**, fare clic su **Nuovo** accanto alla casella **Archivio SQL**.</span><span class="sxs-lookup"><span data-stu-id="8f30e-139">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="8f30e-140">Nella pagina **Definisci nuovo archivio SQL**, specificare l'archivio primario, selezionare **L'istanza SQL è in relazione di mirroring**, specificare il numero di porta del mirroring SQL (il valore predefinito è 5022), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f30e-140">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="8f30e-141">Nella pagina **Definisci archivio SQL**, selezionare **Abilita archivio mirroring SQL**.</span><span class="sxs-lookup"><span data-stu-id="8f30e-141">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="8f30e-p108">Nella pagina **Definisci nuovo archivio SQL**, specificare l'archivio SQL da utilizzare come mirror. Selezionare **L'istanza SQL è in relazione di mirroring**, specificare il numero di porta (il valore predefinito è 5022), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f30e-p108">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="8f30e-144">Se si desidera un'istanza di controllo per il mirror, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f30e-144">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="8f30e-145">Selezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico**.</span><span class="sxs-lookup"><span data-stu-id="8f30e-145">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="8f30e-146">Nella pagina **Definisci archivio SQL**, selezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** e specificare l'archivio SQL da utilizzare per il controllo.</span><span class="sxs-lookup"><span data-stu-id="8f30e-146">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="8f30e-147">Specificare il numero di porta (il valore predefinito è 7022) e fare clic su **OK**</span><span class="sxs-lookup"><span data-stu-id="8f30e-147">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="8f30e-148">Dopo aver completato la definizione del pool Front end e di tutti gli altri ruoli nella topologia, utilizzare Generatore di topologie per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="8f30e-148">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="8f30e-149">Quando la topologia viene pubblicata, se il pool Front end che ospita l'archivio di gestione centrale dispone del mirroring SQL abilitato, verrà visualizzata un'opzione per creare i database dell'archivio SQL primario e del mirror.</span><span class="sxs-lookup"><span data-stu-id="8f30e-149">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="8f30e-150">Fare clic su **Impostazioni** e digitare il percorso da utilizzare come condivisione file per il backup del mirroring.</span><span class="sxs-lookup"><span data-stu-id="8f30e-150">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="8f30e-p110">Fare clic su **OK** e **Avanti** per creare i database e pubblicare la topologia. I server di mirroring e di controllo (se specificato) saranno così distribuiti.</span><span class="sxs-lookup"><span data-stu-id="8f30e-p110">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="8f30e-153">È possibile utilizzare Generatore di topologie per modificare le proprietà di un pool già esistente per abilitare il mirroring SQL.</span><span class="sxs-lookup"><span data-stu-id="8f30e-153">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="8f30e-154">Per aggiungere il mirroring SQL a un pool Front end esistente in Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="8f30e-154">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="8f30e-155">In Generatore di topologie fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8f30e-155">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="8f30e-156">Selezionare **Abilita mirroring dell'archivio SQL**, quindi fare clic su **Nuovo** accanto a **Mirroring dell'archivio SQL**.</span><span class="sxs-lookup"><span data-stu-id="8f30e-156">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="8f30e-157">Specificare l'archivio SQL che si desidera utilizzare come mirror.</span><span class="sxs-lookup"><span data-stu-id="8f30e-157">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="8f30e-158">Selezionare **L'istanza SQL è in relazione di mirroring**, specificare il numero di porta per il mirroring SQL (il valore predefinito è 5022), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f30e-158">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="8f30e-159">Per configurare un'istanza di controllo, selezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** e fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8f30e-159">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="8f30e-160">Specificare l'archivio SQL che si desidera utilizzare come istanza di controllo.</span><span class="sxs-lookup"><span data-stu-id="8f30e-160">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="8f30e-161">Selezionare **L'istanza SQL è in relazione di mirroring**, specificare il numero di porta per il mirroring SQL (il valore predefinito è 7022), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f30e-161">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="8f30e-162">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f30e-162">Click **OK**.</span></span>

9.  <span data-ttu-id="8f30e-p111">Pubblicare la topologia. Verrà richiesto di installare il database.</span><span class="sxs-lookup"><span data-stu-id="8f30e-p111">Publish the topology. When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="8f30e-165">Durante il processo di pubblicazione della topologia verrà richiesto di definire un percorso di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="8f30e-165">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="8f30e-166">I server SQL che partecipano al mirroring devono disporre dell'accesso in lettura/scrittura alla condivisione file per il mirror da stabilire.</span><span class="sxs-lookup"><span data-stu-id="8f30e-166">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="8f30e-167">A questo punto è necessario installare il database prima di passare alla procedura successiva.</span><span class="sxs-lookup"><span data-stu-id="8f30e-167">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="8f30e-168">Quando si configura il mirroring SQL, è necessario tenere a mente alcuni punti:</span><span class="sxs-lookup"><span data-stu-id="8f30e-168">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="8f30e-169">Se esiste già un endpoint del mirroring, sarà riutilizzato insieme alle porte definite qui, e saranno ignorate quelle specificate nella topologia.</span><span class="sxs-lookup"><span data-stu-id="8f30e-169">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="8f30e-p113">Le porte già allocate ad altre applicazioni sullo stesso server, comprese quelle allocate ad altre istanze di SQL, non devono essere utilizzate per le nuove istanze di SQL installate. Pertanto, se si ha più di una istanza SQL installata sullo stesso server, queste devono utilizzare porte differenti per il mirroring. Per ulteriori dettagli, vedere:</span><span class="sxs-lookup"><span data-stu-id="8f30e-p113">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>
    
      - <span data-ttu-id="8f30e-173">"Specificare un indirizzo di rete del server (mirroring del database)" in MSDN Library all' [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="8f30e-173">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="8f30e-174">"Endpoint del mirroring del database (SQL Server)" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="8f30e-174">"The Database Mirroring Endpoint (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="8f30e-175">Utilizzo dei cmdlet di Lync Server Management Shell per configurare il mirroring SQL</span><span class="sxs-lookup"><span data-stu-id="8f30e-175">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="8f30e-176">Il modo più semplice per configurare il mirroring consiste nell'utilizzo di generatore di topologie, ma è possibile farlo anche utilizzando i cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8f30e-176">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="8f30e-177">Aprire una finestra di Lync Server Management Shell ed eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8f30e-177">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="8f30e-178">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8f30e-178">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="8f30e-179">Verrà visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8f30e-179">You will see the following:</span></span>
    
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

2.  <span data-ttu-id="8f30e-180">Verificare che:</span><span class="sxs-lookup"><span data-stu-id="8f30e-180">Verify the following:</span></span>
    
      - <span data-ttu-id="8f30e-181">La porta 5022 è accessibile tramite il firewall se Windows Firewall è abilitato nell'RTC SQL Server E04-OCS. Los \_ a. OCS. local primario \\ .</span><span class="sxs-lookup"><span data-stu-id="8f30e-181">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="8f30e-182">La porta 5022 è accessibile tramite il firewall se Windows Firewall è abilitato nell'RTC SQL Server K16-OCS. Los \_ a. OCS. local del mirror \\ .</span><span class="sxs-lookup"><span data-stu-id="8f30e-182">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="8f30e-183">La porta 7022 è accessibile tramite il firewall se Windows Firewall è abilitato nell'RTC SQL Server AB14-lct. Los \_ a. OCS. local di controllo \\ .</span><span class="sxs-lookup"><span data-stu-id="8f30e-183">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="8f30e-184">Gli account che eseguono i server SQL su tutti i server SQL primario e mirror dispongono dell'autorizzazione di lettura/scrittura per la condivisione file \\ \\ E04-OCS \\ csdatabackup</span><span class="sxs-lookup"><span data-stu-id="8f30e-184">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="8f30e-p114">Verificare che il provider della Strumentazione gestione Windows (WMI) sia eseguito su tutti questi server. Il cmdlet si serve di questo provider per trovare le informazioni sull'account relative ai servizi di SQL Server eseguiti su tutti i server primari, mirror e di controllo.</span><span class="sxs-lookup"><span data-stu-id="8f30e-p114">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="8f30e-187">Verificare che l'account sul quale è eseguito il cmdlet abbia le autorizzazioni necessarie per creare le cartelle per i dati e i file dei log per tutti i server mirror.</span><span class="sxs-lookup"><span data-stu-id="8f30e-187">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="8f30e-p115">Si noti che l'account utente utilizzato dall'istanza SQL per la propria esecuzione deve essere dotato di autorizzazioni di lettura e scrittura per la condivisione file. Se la condivisione file si trova su un server diverso e l'istanza SQL esegue un account di sistema locale, è necessario concedere autorizzazioni per la condivisione file al server che ospita l'istanza SQL.</span><span class="sxs-lookup"><span data-stu-id="8f30e-p115">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="8f30e-190">Digitare A e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="8f30e-190">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="8f30e-191">Sarà configurato il mirroring.</span><span class="sxs-lookup"><span data-stu-id="8f30e-191">The mirroring will be configured.</span></span>

<span data-ttu-id="8f30e-192">**Install-CsMirrorDatabase** installa il mirror e configura il mirroring per tutti i database presenti nell'archivio SQL primario.</span><span class="sxs-lookup"><span data-stu-id="8f30e-192">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="8f30e-193">Se si desidera configurare il mirroring solo per database specifici, è possibile utilizzare l'opzione – DatabaseType oppure se si desidera configurare il mirroring per tutti i database ad eccezione di alcuni, è possibile utilizzare l'opzione-ExcludeDatabaseList, insieme a un elenco separato da virgole di nomi di database da escludere.</span><span class="sxs-lookup"><span data-stu-id="8f30e-193">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="8f30e-194">Ad esempio, se si aggiunge l'opzione seguente a **Install-CsMirrorDatabase**, si eseguirà il mirroring per tutti i database ad eccezione di rtcab e rtcxds.</span><span class="sxs-lookup"><span data-stu-id="8f30e-194">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="8f30e-195">Ad esempio, se si aggiunge l'opzione seguente a **Install-CsMirrorDatabase**, si eseguirà il mirroring unicamente per i database rtcab e rtcxds.</span><span class="sxs-lookup"><span data-stu-id="8f30e-195">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="8f30e-196">Rimozione o modifica del mirroring SQL</span><span class="sxs-lookup"><span data-stu-id="8f30e-196">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="8f30e-p117">Per rimuovere il mirroring SQL da un pool in Generatore di topologie, è prima necessario utilizzare un cmdlet per la rimozione del mirror in SQL Server. È quindi possibile utilizzare Generatore di topologie per rimuovere il mirror dalla topologia. Per rimuovere il mirror in SQL Server, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8f30e-p117">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="8f30e-200">Ad esempio, per rimuovere il mirroring ed eliminare i database degli utenti, digitare:</span><span class="sxs-lookup"><span data-stu-id="8f30e-200">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="8f30e-201">L' `-DropExistingDatabasesOnMirror` opzione fa in modo che i database danneggiati vengano eliminati dal mirror.</span><span class="sxs-lookup"><span data-stu-id="8f30e-201">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="8f30e-202">Per rimuovere il mirror dalla topology, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f30e-202">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="8f30e-203">In Generatore di topologie, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8f30e-203">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="8f30e-204">Deselezionare **Abilita archivio mirroring SQL** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f30e-204">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="8f30e-205">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="8f30e-205">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="8f30e-206">Rimozione di un Server di controllo del mirroring</span><span class="sxs-lookup"><span data-stu-id="8f30e-206">Removing a Mirroring Witness</span></span>

<span data-ttu-id="8f30e-207">Utilizzare questa procedura se è necessario rimuovere il controllo da una configurazione del mirroring del server back-end.</span><span class="sxs-lookup"><span data-stu-id="8f30e-207">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="8f30e-208">In Generatore di topologie, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8f30e-208">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="8f30e-209">Deselezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f30e-209">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="8f30e-210">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="8f30e-210">Publish the topology.</span></span>
    
    <span data-ttu-id="8f30e-211">Dopo aver pubblicato la topologia, generatore di topologie verrà visualizzato un messaggio che include gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f30e-211">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="8f30e-212">Tuttavia, non seguire questo passaggio e non digitare `Uninstall-CsMirrorDatabase` come che disinstalli l'intera configurazione del mirroring.</span><span class="sxs-lookup"><span data-stu-id="8f30e-212">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="8f30e-213">Per rimuovere solo il controllo dalla configurazione di SQL Server, seguire le istruzioni riportate in "rimuovere il controllo da una sessione di mirroring del database (SQL Server)" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456) .</span><span class="sxs-lookup"><span data-stu-id="8f30e-213">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

