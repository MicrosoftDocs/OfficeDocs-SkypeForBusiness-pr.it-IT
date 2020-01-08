---
title: 'Lync Server 2013: modificare le opzioni di archiviazione del database'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a98c2efc0dc956a6b8c33f2fcf065f629e5e57d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="89080-102">Modifica delle opzioni di archiviazione del database in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89080-102">Changing Archiving database options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89080-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="89080-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="89080-104">Se si distribuisce l'archiviazione con l'archiviazione di SQL Server per l'archiviazione dello spazio di archiviazione per tutti gli utenti, è possibile apportare le modifiche seguenti dello spazio di archiviazione del database:</span><span class="sxs-lookup"><span data-stu-id="89080-104">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="89080-105">Usare un database SQL Server diverso per l'archiviazione dello spazio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="89080-105">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="89080-106">Questo include il database di archiviazione principale e qualsiasi database usato per il mirroring di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="89080-106">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="89080-107">Passare all'integrazione di Microsoft Exchange per archiviare i dati e i file di archiviazione nei server di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="89080-107">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="89080-108">Se tutti gli utenti sono ospitati nei server di Exchange 2013 e si vuole usare lo spazio di archiviazione di Microsoft Exchange per tutti gli utenti della distribuzione, è consigliabile rimuovere i database di SQL Server Store dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="89080-108">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="89080-109">Per apportare una di queste modifiche, è necessario eseguire Generatore di topologie, apportare le modifiche e quindi pubblicare di nuovo la topologia.</span><span class="sxs-lookup"><span data-stu-id="89080-109">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="89080-110">Per eseguire questa operazione, è possibile usare generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="89080-110">You can use Topology Builder to do this.</span></span> <span data-ttu-id="89080-111">Non specificare l' **archiviazione di SQL Server Store** o abilitare le informazioni di **mirroring di SQL Server Store** , a meno che non siano presenti utenti di Lync non residenti nei server di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="89080-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="89080-112">Per cambiare l'opzione del database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="89080-112">To change your archiving database option</span></span>

1.  <span data-ttu-id="89080-113">In un computer che esegue Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, accedere utilizzando un account membro del gruppo utenti locali o un account con diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="89080-113">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="89080-114">Puoi definire una topologia usando un account che è un membro del gruppo utenti locali, ma per pubblicare una topologia, necessaria per aggiungere un componente alla topologia. è necessario usare un account che sia un membro del gruppo <STRONG>Domain Admins</STRONG> e del gruppo <STRONG>RTCUniversalServerAdmins</STRONG> e che disponga delle autorizzazioni di controllo completo (ovvero, lettura, scrittura e modifica) nella condivisione di file in uso per l'archivio di file di Lync Server 2013, in modo che il generatore di topologia possa configurare gli elenchi di controllo di accesso discrezionale necessari ( DACL) o un account con diritti equivalenti.</span><span class="sxs-lookup"><span data-stu-id="89080-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="89080-115">Avviare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="89080-115">Start Topology Builder.</span></span>

3.  <span data-ttu-id="89080-116">Nell'albero della console passare al pool Front-end in cui è stata distribuita l'archiviazione e quindi fare clic sul nome del pool Front-end in cui si vogliono modificare le opzioni del database.</span><span class="sxs-lookup"><span data-stu-id="89080-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="89080-117">Nel menu **azione** fare clic su **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="89080-117">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="89080-118">Nella finestra di dialogo **modifica proprietà** fare clic su **generale**.</span><span class="sxs-lookup"><span data-stu-id="89080-118">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="89080-119">Scorrere verso il basso fino all' **archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="89080-119">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="89080-120">In **archiviazione**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="89080-120">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="89080-121">Per passare a un altro archivio di SQL Server esistente, nella casella di riepilogo a discesa, in **archiviazione SQL Server Store**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="89080-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="89080-122">Per usare un archivio di SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio di SQL Server che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="89080-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="89080-123">Per specificare un nuovo archivio di SQL Server, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="89080-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="89080-124">Per usare un archivio di SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio di SQL Server che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="89080-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="89080-125">Per specificare un nuovo archivio di SQL Server, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="89080-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="89080-126">In **FQDN di SQL Server**specificare il nome di dominio completo del server in cui si vuole creare il nuovo archivio di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="89080-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="89080-127">Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="89080-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="89080-128">Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="89080-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="89080-129">Per aggiungere SQL Server Store per il mirroring o passare a un altro archivio di SQL Server esistente per il mirroring di SQL Server Store, selezionare **Abilita mirroring di SQL Server Store**e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="89080-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="89080-130">Per usare un archivio di SQL Server esistente per il mirroring, nella casella di riepilogo a discesa **archiviazione di SQL Server dell'archivio** , fare clic sul nome dell'archivio di SQL Server che si vuole usare per il mirroring.</span><span class="sxs-lookup"><span data-stu-id="89080-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="89080-131">Per specificare un nuovo archivio di SQL Server per il mirroring, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio di SQL Server** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="89080-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="89080-132">In **FQDN di SQL Server**specificare il nome di dominio completo di SQL Server in cui si vuole creare il nuovo archivio di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="89080-132">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="89080-133">Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="89080-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="89080-134">Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="89080-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="89080-135">Se si Abilita il mirroring di SQL Server e si vuole aggiungere o modificare un witness di mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare l'integrità delle istanze di SQL Server e mirror principali), selezionare la casella di controllo **USA mirroring di SQL Server per abilitare il failover automatico** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="89080-135">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="89080-136">In **FQDN di SQL Server**specificare il nome di dominio completo del server in cui si vuole creare il nuovo witness di mirroring di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="89080-136">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="89080-137">Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare per il witness di mirroring.</span><span class="sxs-lookup"><span data-stu-id="89080-137">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="89080-138">Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="89080-138">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="89080-139">Per passare all'integrazione di Microsoft Exchange per archiviare i dati e i file di archiviazione nei server di Exchange 2013 (se tutti gli utenti della distribuzione sono ospitati nei server di Exchange 2013), eliminare tutte le informazioni per l'archiviazione dei database.</span><span class="sxs-lookup"><span data-stu-id="89080-139">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="89080-140">Se gli utenti di Lync non sono ospitati nei server di Exchange 2013, non eliminare le informazioni di SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="89080-140">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="89080-141">Per salvare la configurazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="89080-141">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="89080-142">Le modifiche apportate in Generatore di topologie non hanno effetto finché non viene pubblicata la nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="89080-142">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="89080-143">Per informazioni dettagliate, vedere <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">pubblicazione della topologia aggiornata per l'aggiunta di database di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="89080-143">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

