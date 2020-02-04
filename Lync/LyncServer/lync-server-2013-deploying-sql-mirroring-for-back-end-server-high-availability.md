---
title: Distribuzione del mirroring di SQL per la disponibilità elevata del server back-end
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
ms.openlocfilehash: 7a37c554faf81795363522378160abf5081084f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="9ebfd-102">Distribuzione del mirroring di SQL per la disponibilità elevata del server back-end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ebfd-102">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ebfd-103">_**Argomento Ultima modifica:** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="9ebfd-103">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="9ebfd-104">Per poter distribuire il mirroring SQL, è necessario che i server eseguano un minimo di SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-104">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="9ebfd-105">Questa versione deve essere eseguita su tutti i server coinvolti: il principale, il mirror e il witness.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-105">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="9ebfd-106">Per informazioni dettagliate, [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921)vedere.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-106">For details, see [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="9ebfd-107">In generale, la configurazione del mirroring SQL tra i due server back-end con un testimone richiede quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9ebfd-107">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="9ebfd-108">La versione del server primario di SQL Server deve supportare il mirroring SQL.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-108">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="9ebfd-109">Il principale, il mirror e il Witness (se distribuiti) devono avere la stessa versione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-109">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="9ebfd-110">Il principale e lo specchio devono avere la stessa edizione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-110">The primary and the mirror must have the same edition of SQL Server.</span></span> <span data-ttu-id="9ebfd-111">Il testimone può avere una versione diversa.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-111">The witness may have a different edition.</span></span>

<span data-ttu-id="9ebfd-112">Per le procedure consigliate SQL in termini di supporto delle versioni SQL per un ruolo di testimone, vedere "mirroring del database" in MSDN Library [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345)all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-112">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="9ebfd-113">Puoi usare generatore di topologia per distribuire il mirroring SQL.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-113">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="9ebfd-114">È possibile selezionare un'opzione in Generatore di topologia per eseguire il mirroring dei database e generatore di topologia configura il mirroring, inclusa la configurazione di un testimone, se si vuole, quando si pubblica la topologia.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-114">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="9ebfd-115">Tieni presente che hai configurato o rimosso il testimone contemporaneamente alla configurazione o alla rimozione dello specchio.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-115">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="9ebfd-116">Non esiste un comando separato per distribuire o rimuovere solo un testimone.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-116">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="9ebfd-117">Per configurare il mirroring del server, è prima necessario configurare le autorizzazioni di database SQL in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-117">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="9ebfd-118">Per informazioni dettagliate, vedere "configurare gli account di accesso per il mirroring del database o i gruppi di disponibilità AlwaysOn [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454)(SQL Server)" at.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-118">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="9ebfd-119">Con il mirroring SQL, la modalità di ripristino del database è sempre impostata su **completo**, pertanto è necessario monitorare in modo regolare le dimensioni del log delle transazioni e il backup dei log delle transazioni per evitare di esaurire lo spazio su disco nei server back-end.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-119">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers.</span></span> <span data-ttu-id="9ebfd-120">La frequenza dei backup del log delle transazioni dipende dalla velocità di crescita del log, che a sua volta dipende dalle transazioni di database sostenute dalle attività degli utenti nel pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-120">The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool.</span></span> <span data-ttu-id="9ebfd-121">È consigliabile determinare la quantità di crescita del log delle transazioni prevista per il carico di lavoro di distribuzione di Lync in modo da poter eseguire la pianificazione di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-121">We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly.</span></span> <span data-ttu-id="9ebfd-122">Gli articoli seguenti contengono informazioni aggiuntive su backup e gestione dei log di SQL:</span><span class="sxs-lookup"><span data-stu-id="9ebfd-122">The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="9ebfd-123">Modelli di ripristino di database: "modelli di ripristino (SQL Server)" in[http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="9ebfd-123">Database recovery models: "Recovery Models (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="9ebfd-124">Panoramica del backup: "Panoramica del backup (SQL Server)" all'indirizzo[http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="9ebfd-124">Backup overview: "Backup Overview (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="9ebfd-125">Log delle transazioni di backup: "eseguire il backup di un log delle transazioni (SQL Server)" in[http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="9ebfd-125">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="9ebfd-126">Con il mirroring SQL è possibile configurare la topologia per il mirroring quando si creano i pool o quando i pool sono già stati creati.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-126">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="9ebfd-127">L'uso di generatore di topologie o cmdlet per configurare e rimuovere il mirroring SQL è supportato solo quando i server primari, mirror e Witness (se necessario) appartengono tutti allo stesso dominio.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-127">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="9ebfd-128">Se si vuole configurare il mirroring SQL tra server in diversi domini, vedere la documentazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-128">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="9ebfd-129">Ogni volta che si apporta una modifica a una relazione di mirroring del database back-end, è necessario riavviare tutti i server front-end nel pool.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-129">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="9ebfd-130">Per una modifica del mirroring, ad esempio la modifica della posizione di un mirror, è necessario usare generatore di topologie per eseguire questi tre passaggi:</span><span class="sxs-lookup"><span data-stu-id="9ebfd-130">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="9ebfd-131">Rimuovere il mirroring dal server mirror precedente.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-131">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="9ebfd-132">Aggiungere il mirroring al nuovo server mirror.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-132">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="9ebfd-133">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-133">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="9ebfd-134">È necessario creare una condivisione file per la scrittura dei file mirror e il servizio di SQL Server e agente SQL in uso richiede l'accesso in lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-134">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="9ebfd-135">Se il servizio SQL Server è in uso nel contesto del servizio di rete, è possibile &lt;aggiungere&gt; il &lt;dominio&#92;SqlServerName&gt;$ sia del server principale che di quello mirror per le autorizzazioni di condivisione.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-135">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="9ebfd-136">Il $ è importante per identificare che si tratta di un account di computer.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-136">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="9ebfd-137">Per configurare il mirroring SQL durante la creazione di un pool in Generatore di topologia</span><span class="sxs-lookup"><span data-stu-id="9ebfd-137">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="9ebfd-138">Nella pagina **Definisci l'archivio SQL** fare clic su **nuovo** accanto alla casella **Archivio SQL** .</span><span class="sxs-lookup"><span data-stu-id="9ebfd-138">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="9ebfd-139">Nella pagina **Definisci nuovo archivio SQL** specificare l'archivio principale, selezionare **questa istanza SQL è in relazione speculare**, specificare il numero di porta di mirroring SQL (il valore predefinito è 5022) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-139">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="9ebfd-140">Nella pagina **Definisci l'archivio SQL** selezionare **Abilita mirroring di SQL Store**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-140">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="9ebfd-141">Nella pagina **Definisci nuovo archivio SQL** specificare l'archivio SQL da usare come mirror.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-141">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror.</span></span> <span data-ttu-id="9ebfd-142">Selezionare **questa istanza SQL in relazione speculare**, specificare il numero di porta (il valore predefinito è 5022) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-142">Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="9ebfd-143">Se si vuole un testimone per questo mirror, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ebfd-143">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="9ebfd-144">Selezionare **USA witness di mirroring SQL per abilitare il failover automatico**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-144">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="9ebfd-145">Nella pagina **Definisci l'archivio SQL** selezionare **USA mirroring di SQL per abilitare il failover automatico**e specificare l'SQL Store da usare come witness.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-145">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="9ebfd-146">Specificare il numero di porta (il valore predefinito è 7022) e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-146">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="9ebfd-147">Dopo aver definito il pool Front-end e tutti gli altri ruoli nella topologia, usare generatore di topologie per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-147">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="9ebfd-148">Quando la topologia viene pubblicata, se il pool Front-end che ospita Central Management store ha attivato il mirroring SQL, verrà visualizzata un'opzione per creare database di SQL Store primari e speculari.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-148">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="9ebfd-149">Fare clic su **Impostazioni**e digitare il percorso da usare come condivisione file per il backup del mirroring.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-149">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="9ebfd-150">Fare clic su **OK** e quindi su **Avanti** per creare i database e pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-150">Click **OK** and then **Next** to create the databases and publish the topology.</span></span> <span data-ttu-id="9ebfd-151">Il mirroring e il Witness (se specificato) verranno distribuiti.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-151">The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="9ebfd-152">Puoi usare generatore di topologie per modificare le proprietà di un pool già esistente per abilitare il mirroring SQL.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-152">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="9ebfd-153">Per aggiungere il mirroring SQL a un pool Front-end esistente in Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="9ebfd-153">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="9ebfd-154">In Generatore di topologie fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-154">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="9ebfd-155">Selezionare **Abilita mirroring di SQL Store**e quindi fare clic su **nuovo** accanto a **mirroring SQL Store**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-155">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="9ebfd-156">Specificare l'archivio SQL che si vuole usare come mirror.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-156">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="9ebfd-157">Selezionare **questa istanza SQL è in relazione speculare**, specificare il numero della porta di mirroring SQL la porta predefinita è 5022) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-157">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="9ebfd-158">Se si vuole configurare un testimone, selezionare **USA Witness mirroring SQL per abilitare il failover automatico**e fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-158">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="9ebfd-159">Specificare l'archivio SQL che si vuole usare come witness.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-159">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="9ebfd-160">Selezionare **questa istanza SQL è in relazione speculare**, specificare il numero di porta di mirroring SQL (la porta predefinita è 7022) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-160">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="9ebfd-161">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-161">Click **OK**.</span></span>

9.  <span data-ttu-id="9ebfd-162">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-162">Publish the topology.</span></span> <span data-ttu-id="9ebfd-163">Quando si esegue questa operazione, verrà richiesto di installare il database.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-163">When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="9ebfd-164">Durante il processo di pubblicazione della topologia verrà richiesto di definire un percorso di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-164">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="9ebfd-165">I server SQL che partecipano al mirroring devono avere accesso in lettura/scrittura alla condivisione file per il mirror da stabilire.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-165">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="9ebfd-166">Devi quindi installare il database prima di passare alla procedura successiva.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-166">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="9ebfd-167">Quando si configura il mirroring SQL, è consigliabile tenersi in considerazione quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9ebfd-167">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="9ebfd-168">Se un endpoint di mirroring esiste già, verrà riutilizzato con le porte definite in tale posizione e ignorerà quelle specificate nella topologia.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-168">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="9ebfd-169">Qualsiasi porta già allocata per altre applicazioni nello stesso server, inclusi quelli per altre istanze SQL, non deve essere usata per le istanze SQL installate a mano.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-169">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand.</span></span> <span data-ttu-id="9ebfd-170">Questo implica che se sono installate più istanze di SQL nello stesso server, non devono usare la stessa porta per il mirroring.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-170">This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring.</span></span> <span data-ttu-id="9ebfd-171">Per informazioni dettagliate, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ebfd-171">For details, see the following articles:</span></span>
    
      - <span data-ttu-id="9ebfd-172">"Specificare un indirizzo di rete del server (mirroring del database)" in MSDN Library all'[http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="9ebfd-172">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="9ebfd-173">"Endpoint del mirroring del database (SQL Server)" in[http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="9ebfd-173">"The Database Mirroring Endpoint (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="9ebfd-174">Uso dei cmdlet di Lync Server Management Shell per configurare il mirroring SQL</span><span class="sxs-lookup"><span data-stu-id="9ebfd-174">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="9ebfd-175">Il modo più semplice per configurare il mirroring consiste nell'usare generatore di topologia, ma è anche possibile usare i cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-175">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="9ebfd-176">Aprire una finestra di Lync Server Management Shell ed eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="9ebfd-176">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="9ebfd-177">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9ebfd-177">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="9ebfd-178">Verranno visualizzate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ebfd-178">You will see the following:</span></span>
    
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

2.  <span data-ttu-id="9ebfd-179">Verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9ebfd-179">Verify the following:</span></span>
    
      - <span data-ttu-id="9ebfd-180">La porta 5022 è accessibile tramite il firewall se Windows Firewall è abilitato nell'RTC principale di SQL Server E04-OCS\_. Los a. lsipt\\. local.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-180">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="9ebfd-181">La porta 5022 è accessibile tramite il firewall se Windows Firewall è abilitato nell'RTC di SQL Server K16-OCS.\_Los a. lsipt.\\local.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-181">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="9ebfd-182">La porta 7022 è accessibile tramite il firewall se Windows Firewall è abilitato nell'RTC di SQL Server AB14-lct.\_Los a. lsipt.\\local.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-182">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="9ebfd-183">Gli account che utilizzano i server SQL in tutti i server SQL primari e mirror hanno l'autorizzazione di lettura/ \\ \\scrittura per la\\condivisione file E04-OCS csdatabackup</span><span class="sxs-lookup"><span data-stu-id="9ebfd-183">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="9ebfd-184">Verificare che il provider di Strumentazione gestione Windows (WMI) sia in uso in tutti questi server.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-184">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers.</span></span> <span data-ttu-id="9ebfd-185">Il cmdlet usa questo provider per trovare le informazioni sull'account per i servizi SQL Server in uso in tutti i server primari, mirror e Witness.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-185">The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="9ebfd-186">Verificare che l'account che utilizza questo cmdlet disponga delle autorizzazioni necessarie per creare le cartelle per i dati e i file di log per tutti i server mirror.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-186">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="9ebfd-187">Tieni presente che l'account utente usato dall'istanza SQL per l'esecuzione deve avere l'autorizzazione di lettura/scrittura per la condivisione file.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-187">Note that the user account that the SQL instance uses to run must have read/write permission to the file share.</span></span> <span data-ttu-id="9ebfd-188">Se la condivisione file si trova in un server diverso e l'istanza SQL esegue un account di sistema locale, è necessario concedere le autorizzazioni di condivisione file al server che ospita l'istanza SQL.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-188">If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="9ebfd-189">Digitare A e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-189">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="9ebfd-190">Verrà configurato il mirroring.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-190">The mirroring will be configured.</span></span>

<span data-ttu-id="9ebfd-191">**Install-CsMirrorDatabase** installa il mirror e configura il mirroring per tutti i database presenti nell'archivio SQL principale.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-191">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="9ebfd-192">Se si vuole configurare il mirroring solo per database specifici, è possibile usare l'opzione – DatabaseType o se si vuole configurare il mirroring per tutti i database tranne che per pochi, è possibile usare l'opzione-ExcludeDatabaseList, insieme a un elenco di database delimitato da virgole nomi da escludere.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-192">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="9ebfd-193">Ad esempio, se si aggiunge l'opzione seguente a **Install-CsMirrorDatabase**, tutti i database eccetto RTCAb e rtcxds verranno speculati.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-193">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="9ebfd-194">Ad esempio, se si aggiunge l'opzione seguente a **Install-CsMirrorDatabase**, verranno rispecchiati solo i database RTCAb, rtcshared e rtcxds.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-194">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="9ebfd-195">Rimozione o modifica del mirroring SQL</span><span class="sxs-lookup"><span data-stu-id="9ebfd-195">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="9ebfd-196">Per rimuovere il mirroring SQL di un pool in Generatore di topologia, è necessario prima di tutto usare un cmdlet per rimuovere il mirror in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-196">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="9ebfd-197">Puoi quindi usare generatore di topologia per rimuovere il mirror dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-197">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="9ebfd-198">Per rimuovere il mirror in SQL Server, usare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="9ebfd-198">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="9ebfd-199">Ad esempio, per rimuovere il mirroring e rilasciare i database per i database degli utenti, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9ebfd-199">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="9ebfd-200">L' `-DropExistingDatabasesOnMirror` opzione fa sì che i database interessati vengano eliminati dallo specchio.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-200">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="9ebfd-201">Quindi, per rimuovere il mirror dalla topologia, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ebfd-201">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="9ebfd-202">In Generatore di topologie fare clic con il pulsante destro del mouse sul pool e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-202">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="9ebfd-203">Deselezionare **Abilita mirroring di SQL Store** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-203">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="9ebfd-204">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-204">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="9ebfd-205">Rimozione di un witness di mirroring</span><span class="sxs-lookup"><span data-stu-id="9ebfd-205">Removing a Mirroring Witness</span></span>

<span data-ttu-id="9ebfd-206">Usare questa procedura se si vuole rimuovere il testimone da una configurazione di mirroring del server back-end.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-206">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="9ebfd-207">In Generatore di topologie fare clic con il pulsante destro del mouse sul pool e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="9ebfd-208">Deselezionare **USA mirroring di SQL Server per abilitare il failover automatico** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-208">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="9ebfd-209">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-209">Publish the topology.</span></span>
    
    <span data-ttu-id="9ebfd-210">Dopo aver pubblicato la topologia, generatore di topologie verrà visualizzato un messaggio che include le operazioni seguenti</span><span class="sxs-lookup"><span data-stu-id="9ebfd-210">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="9ebfd-211">Tuttavia, non seguire questo passaggio e non digitare `Uninstall-CsMirrorDatabase` in modo da disinstallare l'intera configurazione di mirroring.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-211">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="9ebfd-212">Per rimuovere solo il testimone dalla configurazione di SQL Server, seguire le istruzioni in "rimuovere il testimone da una sessione di mirroring del database (SQL Server) [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456)" at.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-212">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

