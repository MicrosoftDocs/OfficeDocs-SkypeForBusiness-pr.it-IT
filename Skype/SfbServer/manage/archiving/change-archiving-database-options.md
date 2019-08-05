---
title: Modificare le opzioni di archiviazione del database in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Riepilogo: informazioni su come modificare le opzioni di archiviazione del database per Skype for Business Server.'
ms.openlocfilehash: 56aa29ef185176ce3b080572723c566455731dc4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195115"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="0c58d-103">Modificare le opzioni di archiviazione del database in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0c58d-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="0c58d-104">**Riepilogo:** Informazioni su come modificare le opzioni di archiviazione del database per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0c58d-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="0c58d-105">Se si distribuisce l'archiviazione con l'archiviazione di SQL Server per l'archiviazione dello spazio di archiviazione per tutti gli utenti, è possibile apportare le modifiche seguenti dello spazio di archiviazione del database:</span><span class="sxs-lookup"><span data-stu-id="0c58d-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="0c58d-106">Usare un database SQL Server diverso per l'archiviazione dello spazio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="0c58d-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="0c58d-107">Questo include il database di archiviazione principale e qualsiasi database usato per il mirroring di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0c58d-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="0c58d-108">Passare all'integrazione di Microsoft Exchange per archiviare i dati e i file di archiviazione nei server di Exchange.</span><span class="sxs-lookup"><span data-stu-id="0c58d-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="0c58d-109">Se tutti gli utenti sono ospitati nei server Exchange e si vuole usare lo spazio di archiviazione di Microsoft Exchange per tutti gli utenti della distribuzione, è consigliabile rimuovere i database di SQL Server Store dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="0c58d-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="0c58d-110">Per apportare una di queste modifiche, è necessario eseguire Generatore di topologie, apportare le modifiche e quindi pubblicare di nuovo la topologia.</span><span class="sxs-lookup"><span data-stu-id="0c58d-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="0c58d-111">Non specificare l' **archiviazione di SQL Server Store** o abilitare le informazioni di mirroring di **SQL Server Store** , a meno che tu non abbia utenti di Skype for business non residenti nei server di Exchange.</span><span class="sxs-lookup"><span data-stu-id="0c58d-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="0c58d-112">Modificare le opzioni del database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="0c58d-112">Change Archiving database options</span></span>

1. <span data-ttu-id="0c58d-113">In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, accedere utilizzando un account membro del gruppo utenti locali o un account con diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="0c58d-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0c58d-114">Puoi definire una topologia usando un account che è un membro del gruppo utenti locali, ma per pubblicare una topologia, necessaria per aggiungere un componente alla topologia, devi usare un account membro del gruppo **Domain Admins** e **RTCUniversalSer gruppo verAdmins** , con autorizzazioni di controllo completo (ovvero, lettura, scrittura e modifica) nella condivisione file in uso per l'archivio file di Skype for Business Server, in modo che il generatore di topologia possa configurare il controllo di accesso discrezionale richiesto elenchi (DACL) o un account con diritti equivalenti.</span><span class="sxs-lookup"><span data-stu-id="0c58d-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="0c58d-115">Avviare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="0c58d-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="0c58d-116">Nell'albero della console passare al pool Front-end in cui è stata distribuita l'archiviazione e quindi fare clic sul nome del pool Front-end in cui si vogliono modificare le opzioni del database.</span><span class="sxs-lookup"><span data-stu-id="0c58d-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="0c58d-117">Nel menu **azione** fare clic su **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0c58d-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="0c58d-118">Nella finestra di dialogo **modifica proprietà** fare clic su **generale**.</span><span class="sxs-lookup"><span data-stu-id="0c58d-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="0c58d-119">Scorrere verso il basso fino all' **archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="0c58d-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="0c58d-120">In **archiviazione**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c58d-120">In **Archiving**, do the following:</span></span>
    
   - <span data-ttu-id="0c58d-121">Per passare a un altro archivio di SQL Server esistente, nella casella di riepilogo a discesa, in **archiviazione SQL Server Store**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c58d-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
   - <span data-ttu-id="0c58d-122">Per usare un archivio di SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio di SQL Server che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="0c58d-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="0c58d-123">Per specificare un nuovo archivio di SQL Server, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c58d-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
     - <span data-ttu-id="0c58d-124">Per usare un archivio di SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio di SQL Server che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="0c58d-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
     - <span data-ttu-id="0c58d-125">Per specificare un nuovo archivio di SQL Server, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c58d-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
       - <span data-ttu-id="0c58d-126">In **FQDN di SQL Server**specificare il nome di dominio completo del server in cui si vuole creare il nuovo archivio di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0c58d-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
       - <span data-ttu-id="0c58d-127">Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="0c58d-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
       - <span data-ttu-id="0c58d-128">Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="0c58d-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="0c58d-129">Per aggiungere SQL Server Store per il mirroring o passare a un altro archivio di SQL Server esistente per il mirroring di SQL Server Store, selezionare **Abilita mirroring di SQL Server Store**e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c58d-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
     - <span data-ttu-id="0c58d-130">Per usare un archivio di SQL Server esistente per il mirroring, nella casella di riepilogo a discesa **archiviazione di SQL Server dell'archivio** , fare clic sul nome dell'archivio di SQL Server che si vuole usare per il mirroring.</span><span class="sxs-lookup"><span data-stu-id="0c58d-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
     - <span data-ttu-id="0c58d-131">Per specificare un nuovo archivio di SQL Server per il mirroring, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio di SQL Server** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c58d-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
       <span data-ttu-id="0c58d-132">un.</span><span class="sxs-lookup"><span data-stu-id="0c58d-132">a.</span></span> <span data-ttu-id="0c58d-133">In **FQDN di SQL Server**specificare il nome di dominio completo di SQL Server in cui si vuole creare il nuovo archivio di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0c58d-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
       <span data-ttu-id="0c58d-134">b.</span><span class="sxs-lookup"><span data-stu-id="0c58d-134">b.</span></span> <span data-ttu-id="0c58d-135">Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="0c58d-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
       <span data-ttu-id="0c58d-136">c.</span><span class="sxs-lookup"><span data-stu-id="0c58d-136">c.</span></span> <span data-ttu-id="0c58d-137">Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="0c58d-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="0c58d-138">Se si Abilita il mirroring di SQL Server e si vuole aggiungere o modificare un witness di mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare l'integrità delle istanze di SQL Server e mirror principali), selezionare l' **uso del witness di SQL Server mirroring per abilitare** la casella di controllo failover automatico e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c58d-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="0c58d-139">un.</span><span class="sxs-lookup"><span data-stu-id="0c58d-139">a.</span></span> <span data-ttu-id="0c58d-140">In **FQDN di SQL Server**specificare il nome di dominio completo del server in cui si vuole creare il nuovo witness di mirroring di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0c58d-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="0c58d-141">b.</span><span class="sxs-lookup"><span data-stu-id="0c58d-141">b.</span></span> <span data-ttu-id="0c58d-142">Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare per il witness di mirroring.</span><span class="sxs-lookup"><span data-stu-id="0c58d-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="0c58d-143">c.</span><span class="sxs-lookup"><span data-stu-id="0c58d-143">c.</span></span> <span data-ttu-id="0c58d-144">Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="0c58d-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="0c58d-145">Per passare all'integrazione di Microsoft Exchange per archiviare dati e file di archiviazione nei server di Exchange (se tutti gli utenti della distribuzione sono ospitati nei server Exchange), eliminare tutte le informazioni per l'archiviazione dei database.</span><span class="sxs-lookup"><span data-stu-id="0c58d-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="0c58d-146">Se gli utenti di Skype for business non sono residenti nei server di Exchange, non eliminare le informazioni di SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="0c58d-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="0c58d-147">Per salvare la configurazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c58d-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0c58d-148">Le modifiche apportate in Generatore di topologie non hanno effetto finché non viene pubblicata la nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="0c58d-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="0c58d-149">Per informazioni dettagliate, vedere [aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span><span class="sxs-lookup"><span data-stu-id="0c58d-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="0c58d-150">Modificare la posizione del database di archiviazione tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c58d-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="0c58d-151">Nella maggior parte dei casi non è necessario modificare la posizione del database di archiviazione, che viene specificato durante l'installazione del server di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="0c58d-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="0c58d-152">Tuttavia, se si verifica un errore hardware o un altro problema, è possibile puntare il server di archiviazione in un nuovo database usando il cmdlet **Set-CsArchivingServer** .</span><span class="sxs-lookup"><span data-stu-id="0c58d-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="0c58d-153">Nell'esempio seguente viene modificata la posizione del database di archiviazione per il server di archiviazione ArchivingServer: atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0c58d-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="0c58d-154">In questo esempio il nuovo database si trova in ArchivingDatabase: ATL-SQL-001.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="0c58d-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


