---
title: 'Lync Server 2013: Aggiungere il server Chat persistente alla topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8985ee2fd28a81f3630e4f80c0ac4dd5a23d4475
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="f757d-102">Aggiungere il server Chat persistente alla topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f757d-102">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f757d-103">_**Argomento Ultima modifica:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="f757d-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="f757d-104">È necessario incorporare Lync Server 2013, il supporto del server di chat persistente nella topologia prima di poter configurare la distribuzione per supportare il server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f757d-104">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="f757d-105">Le informazioni contenute in questo argomento illustrano come usare generatore di topologia per aggiungere il supporto del server di chat persistente alla topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="f757d-105">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="f757d-106">Per aggiungere un server di chat persistente a una topologia</span><span class="sxs-lookup"><span data-stu-id="f757d-106">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="f757d-107">Eseguire la procedura seguente per installare un singolo pool di server di chat persistente senza una configurazione di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="f757d-107">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="f757d-108">Per configurare un pool di server di chat persistente esteso per l'elevata disponibilità e il ripristino di emergenza, vedere [configurazione del server di chat persistente per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f757d-108">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f757d-109">Per distribuire più pool di server di chat persistenti, ripetere lo stesso processo per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="f757d-109">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="f757d-110">In un computer che esegue Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, accedere con un account membro del gruppo utenti locali o un account con diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="f757d-110">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f757d-111">Puoi definire una topologia usando un account che è un membro del gruppo utenti locali, ma per pubblicare una topologia, necessaria per installare un Server 2013 di Lync Server, è necessario usare un account che sia un membro del gruppo <STRONG>Domain Admins</STRONG> e del gruppo <STRONG>RTCUniversalServerAdmins</STRONG> e che disponga delle autorizzazioni di controllo completo (ovvero, lettura, scrittura e modifica) nell'archivio di file che si vuole usare per il file Store del server di chat persistente, in modo che il generatore di topologia possa configurare gli elenchi DACL necessari. o un account con diritti equivalenti.</span><span class="sxs-lookup"><span data-stu-id="f757d-111">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="f757d-112">Avviare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="f757d-112">Start Topology Builder.</span></span>

3.  <span data-ttu-id="f757d-113">Nell'albero della console passare al nodo **pool di chat persistente** ed espanderlo per selezionare un pool di server di chat persistente oppure fare clic con il pulsante destro del mouse sul nodo e scegliere **nuovo pool di chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="f757d-113">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="f757d-114">È necessario definire il nome di dominio completo (FQDN) del pool e indicare se il pool sarà un pool a server singolo o un pool di distribuzione a più server.</span><span class="sxs-lookup"><span data-stu-id="f757d-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="f757d-115">È possibile scegliere un **pool di computer multipli** o un **singolo pool di computer**.</span><span class="sxs-lookup"><span data-stu-id="f757d-115">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="f757d-116">Scegliere il primo se si prevede di avere più di un server front end server di chat persistente nel pool del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f757d-116">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="f757d-117">Fare questa scelta ora o in un secondo momento, perché dopo aver creato un singolo pool di computer non è possibile aggiungervi altri server in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="f757d-117">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="f757d-118">Se si sceglie un pool di computer multipli, immettere i nomi dei singoli server front-end del server di chat persistente che costituiscono il pool.</span><span class="sxs-lookup"><span data-stu-id="f757d-118">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f757d-119">Se il ruolo del server di chat persistente viene installato in un server&nbsp;Lync Server 2013 Standard Edition, l'FQDN deve corrispondere al nome di dominio completo del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f757d-119">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="f757d-120">Definire un **nome visualizzato** semplice per il pool di server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f757d-120">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="f757d-121">Il nome visualizzato può essere usato dai client personalizzati, in particolare quando sono presenti più pool di server di chat persistenti per distinguere le sale.</span><span class="sxs-lookup"><span data-stu-id="f757d-121">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="f757d-122">Definire la porta utilizzata dal server di chat persistente per comunicare con i server front-end di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f757d-122">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="f757d-123">La porta predefinita è 5041.</span><span class="sxs-lookup"><span data-stu-id="f757d-123">The default port is 5041.</span></span>

6.  <span data-ttu-id="f757d-124">Se l'organizzazione richiede il supporto della conformità, selezionare la casella di controllo **Abilita conformità** .</span><span class="sxs-lookup"><span data-stu-id="f757d-124">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="f757d-125">Se scelto, il servizio di conformità del server di chat persistente viene installato nello stesso computer del server front end del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f757d-125">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="f757d-126">Viene richiesto di selezionare un server di SQL Server back-end per la conformità del server di chat persistente in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="f757d-126">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="f757d-127">Assegnare l'affinità del sito per il pool del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f757d-127">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="f757d-128">Selezionare la casella di controllo **Usa il pool come \<predefinito\> per il sito SiteName** o **usare questo pool come predefinito per tutti i siti** per designare questo pool di server di chat persistente come pool predefinito per il sito corrente o per tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="f757d-128">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="f757d-129">Quando il client Lync 2013 viene usato per creare e gestire le sale, il pool predefinito associato al sito dell'utente viene usato dall'esperienza di creazione e gestione della sala in modo che possa instradare le operazioni di creazione e gestione della sala in tale pool.</span><span class="sxs-lookup"><span data-stu-id="f757d-129">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="f757d-130">Questo problema si applica solo quando sono distribuiti più pool di server di chat persistenti e si vogliono usare le caratteristiche di creazione e gestione della sala del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f757d-130">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f757d-131">È possibile personalizzare le caratteristiche di creazione e gestione della sala usando il Software Development Kit (SDK) di Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="f757d-131">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="f757d-132">Per informazioni dettagliate su come configurare i database di backup di SQL Server per il ripristino di emergenza, vedere <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">configurazione del server di chat persistente per l'elevata disponibilità e ripristino di emergenza in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f757d-132">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="f757d-133">Definire l' **Archivio SQL per il back-end del server di chat persistente (in cui è archiviato il contenuto della chat room)** eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f757d-133">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="f757d-134">Per usare un database di SQL Server esistente, nell'elenco a discesa fare clic sul nome del database di SQL Server che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="f757d-134">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="f757d-135">Per specificare un nuovo database di SQL Server, fare clic su **nuovo**e quindi, in **Definisci nuovo archivio SQL**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f757d-135">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="f757d-136">In **FQDN di SQL Server**specificare il nome di dominio completo di SQL Server in cui si vuole creare il nuovo database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f757d-136">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="f757d-137">Selezionare l'istanza **predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, selezionare **istanza denominata**e specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="f757d-137">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="f757d-138">Definire il database di conformità di SQL Server se è stata abilitata la conformità.</span><span class="sxs-lookup"><span data-stu-id="f757d-138">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f757d-139">Per informazioni dettagliate su come configurare i mirror di SQL Server per una disponibilità elevata per il database del server di chat persistente e per il database di conformità persistente per il server di chat, vedere <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">configurazione del server di chat persistente per l'elevata disponibilità e ripristino di emergenza in Lync server 2013</A> nella documentazione sulla distribuzione</span><span class="sxs-lookup"><span data-stu-id="f757d-139">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="f757d-140">Definire l'archivio di file.</span><span class="sxs-lookup"><span data-stu-id="f757d-140">Define the file store.</span></span> <span data-ttu-id="f757d-141">Un archivio file è una cartella in cui è archiviata una copia di un file caricato nel repository del file, ad esempio l'archiviazione di file allegati inviati in una chat room.</span><span class="sxs-lookup"><span data-stu-id="f757d-141">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="f757d-142">Nel caso di una topologia del server di chat persistente a più server, questo deve essere un percorso UNC (Universal Naming Convention). e per una topologia del server di chat persistente a singolo server, può essere un percorso di file locale.</span><span class="sxs-lookup"><span data-stu-id="f757d-142">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="f757d-143">Per usare un archivio file esistente, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="f757d-143">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="f757d-144">In **FQDN file server**specificare il nome di dominio completo dell'archivio di file in cui si vuole creare il nuovo archivio di file.</span><span class="sxs-lookup"><span data-stu-id="f757d-144">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="f757d-145">In **condivisione file**specificare l'archivio di file che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="f757d-145">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f757d-146">È possibile definire l'archivio di file in Generatore di topologie prima di creare l'archivio di file, ma è necessario creare l'archivio file nella posizione definita che si definisce prima di pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="f757d-146">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="f757d-147">Selezionare il pool del server front-end da usare come hop successivo per il pool di server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f757d-147">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="f757d-148">Si tratta del pool Front-End Server che sarà in grado di instradare le richieste del server di chat persistente al pool.</span><span class="sxs-lookup"><span data-stu-id="f757d-148">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="f757d-149">Per salvare la configurazione, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="f757d-149">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="f757d-150">Il pool di server di chat persistente viene visualizzato in Generatore di topologia accompagnato dalle impostazioni specifiche del pool.</span><span class="sxs-lookup"><span data-stu-id="f757d-150">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="f757d-151">Per pubblicare ora la topologia aggiornata in cui si è installato il server di chat persistente, vedere [pubblicare la topologia aggiornata in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f757d-151">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f757d-152">Con generatore di topologia già aperto, è possibile procedere con il passaggio 3 della <A href="lync-server-2013-publish-the-updated-topology.md">pubblicazione della topologia aggiornata in Lync Server 2013</A> per iniziare a pubblicare la topologia aggiornata.</span><span class="sxs-lookup"><span data-stu-id="f757d-152">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

