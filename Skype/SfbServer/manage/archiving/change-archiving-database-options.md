---
title: Modificare le opzioni del database di archiviazione in Skype for Business Server
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
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Riepilogo: informazioni su come modificare le opzioni del database di archiviazione per Skype for Business Server.'
ms.openlocfilehash: 9a2b1056b6dd5d31c8b1dda658e219c345b28278
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817696"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="dd298-103">Modificare le opzioni del database di archiviazione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd298-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="dd298-104">**Riepilogo:** Informazioni su come modificare le opzioni del database di archiviazione per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dd298-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="dd298-105">Se si distribuisce l'archiviazione utilizzando l'archiviazione di SQL Server per l'archiviazione di un utente, è possibile apportare le modifiche apportate ai database seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd298-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="dd298-106">Utilizzare un database di SQL Server diverso per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="dd298-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="dd298-107">Sono inclusi il database di archiviazione principale e qualsiasi database utilizzato per il mirroring di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dd298-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="dd298-108">Passare all'integrazione di Microsoft Exchange per archiviare i dati di archiviazione e i file nei server di Exchange.</span><span class="sxs-lookup"><span data-stu-id="dd298-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="dd298-109">Se tutti gli utenti sono ospitati nei server Exchange e si desidera utilizzare lo spazio di archiviazione di Microsoft Exchange per tutti gli utenti nella distribuzione, è necessario rimuovere i database dell'archivio SQL Server dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="dd298-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="dd298-110">Per apportare una o più di queste modifiche, è necessario eseguire Generatore di topologie, apportare le modifiche e quindi ripubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="dd298-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="dd298-111">Non specificare l' **Archivio SQL Server di archiviazione** o abilitare le informazioni sul **mirroring dell'archivio SQL Server** , a meno che non si disponga di utenti Skype for business che non sono ospitati nei server Exchange.</span><span class="sxs-lookup"><span data-stu-id="dd298-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="dd298-112">Modificare le opzioni dei database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="dd298-112">Change Archiving database options</span></span>

1. <span data-ttu-id="dd298-113">In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, eseguire l'accesso utilizzando un account membro del gruppo utenti locali (o un account con diritti utente equivalenti).</span><span class="sxs-lookup"><span data-stu-id="dd298-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dd298-114">È possibile definire una topologia utilizzando un account membro del gruppo utenti locali, ma per pubblicare una topologia, necessaria per aggiungere un componente alla topologia, è necessario utilizzare un account membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** . e che dispone di autorizzazioni di controllo completo (ovvero, lettura, scrittura e modifica) sulla condivisione file utilizzata per l'archivio file di Skype for Business Server (ovvero, in modo che generatore di topologie possa configurare gli elenchi di controllo di accesso discrezionale necessari o un account con diritti equivalenti.</span><span class="sxs-lookup"><span data-stu-id="dd298-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="dd298-115">Avviare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="dd298-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="dd298-116">Nell'albero della console accedere al pool Front End in cui è stata distribuita Archiviazione e fare clic sul nome del pool Front End in cui si vuole modificare le opzioni di database.</span><span class="sxs-lookup"><span data-stu-id="dd298-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="dd298-117">Nel menu **Azione** fare clic su **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="dd298-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="dd298-118">Nella finestra di dialogo **Modifica proprietà** fare clic su **Generale**.</span><span class="sxs-lookup"><span data-stu-id="dd298-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="dd298-119">Scorrere verso il basso fino ad **Archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="dd298-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="dd298-120">In **Archiviazione** seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="dd298-120">In **Archiving**, do the following:</span></span>
    
   - <span data-ttu-id="dd298-121">Per passare a un archivio SQL Server esistente diverso, nella casella di riepilogo a discesa in **Archivio SQL Server archiviazione** seguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="dd298-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
   - <span data-ttu-id="dd298-122">Per usare un archivio SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio SQL Server che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="dd298-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="dd298-123">Per specificare un nuovo archivio SQL Server, fare clic su **Nuovo**, quindi nella finestra di dialogo **Definire un nuovo archivio SQL Server** seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="dd298-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
     - <span data-ttu-id="dd298-124">Per usare un archivio SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio SQL Server che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="dd298-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
     - <span data-ttu-id="dd298-125">Per specificare un nuovo archivio SQL Server, fare clic su **nuovo** e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd298-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
       - <span data-ttu-id="dd298-126">In **FQDN SQL Server** specificare il nome di dominio completo del server in cui si desidera creare il nuovo archivio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dd298-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
       - <span data-ttu-id="dd298-127">Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="dd298-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
       - <span data-ttu-id="dd298-128">Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="dd298-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="dd298-129">Per aggiungere l'archivio SQL Server per il mirroring o passare a un archivio SQL Server esistente diverso per il mirroring dell'archivio SQL Server, selezionare **Abilita mirroring dell'archivio SQL Server**, quindi procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="dd298-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
     - <span data-ttu-id="dd298-130">Per utilizzare un archivio SQL Server esistente per il mirroring, nella casella di riepilogo a discesa **mirror archivio SQL Server archiviazione** fare clic sul nome dell'archivio SQL Server che si desidera utilizzare per il mirroring.</span><span class="sxs-lookup"><span data-stu-id="dd298-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
     - <span data-ttu-id="dd298-131">Per specificare un nuovo archivio SQL Server per il mirroring, fare clic su **nuovo** e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd298-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
       <span data-ttu-id="dd298-132">a.</span><span class="sxs-lookup"><span data-stu-id="dd298-132">a.</span></span> <span data-ttu-id="dd298-133">In **FQDN SQL Server** specificare il nome di dominio completo di SQL Server in cui si desidera creare il nuovo archivio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dd298-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
       <span data-ttu-id="dd298-134">b.</span><span class="sxs-lookup"><span data-stu-id="dd298-134">b.</span></span> <span data-ttu-id="dd298-135">Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="dd298-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
       <span data-ttu-id="dd298-136">c.</span><span class="sxs-lookup"><span data-stu-id="dd298-136">c.</span></span> <span data-ttu-id="dd298-137">Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="dd298-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="dd298-138">Se si Abilita il mirroring di SQL Server e si desidera aggiungere o modificare un controllo del mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare l'integrità del server SQL Server primario e delle istanze di mirroring), selezionare la casella utilizza verifica del **mirroring di SQL Server per abilitare il failover automatico** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd298-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="dd298-139">a.</span><span class="sxs-lookup"><span data-stu-id="dd298-139">a.</span></span> <span data-ttu-id="dd298-140">In **FQDN SQL Server** specificare il nome di dominio completo del server in cui si desidera creare il nuovo controllo del mirroring di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dd298-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="dd298-141">b.</span><span class="sxs-lookup"><span data-stu-id="dd298-141">b.</span></span> <span data-ttu-id="dd298-142">Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare per il controllo di mirroring.</span><span class="sxs-lookup"><span data-stu-id="dd298-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="dd298-143">c.</span><span class="sxs-lookup"><span data-stu-id="dd298-143">c.</span></span> <span data-ttu-id="dd298-144">Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="dd298-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="dd298-145">Per passare all'integrazione di Microsoft Exchange per archiviare i dati di archiviazione e i file nei server di Exchange (se tutti gli utenti della distribuzione sono ospitati nei server Exchange), eliminare tutte le informazioni per i database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="dd298-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="dd298-146">Se gli utenti di Skype for business non sono ospitati nei server di Exchange, non eliminare le informazioni sull'archivio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dd298-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="dd298-147">Per salvare la configurazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd298-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="dd298-148">Le modifiche apportate in Generatore di topologie non sono effettive finché non si pubblica la nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="dd298-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="dd298-149">Per ulteriori informazioni, vedere [aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span><span class="sxs-lookup"><span data-stu-id="dd298-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="dd298-150">Modificare il percorso del database di archiviazione utilizzando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd298-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="dd298-151">Nella maggior parte dei casi, non è necessario modificare il percorso del database di archiviazione, che viene specificato durante l'installazione del server di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="dd298-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="dd298-152">Tuttavia, se si verifica un errore hardware o un altro problema, è possibile fare in modo che il server di archiviazione punti a un nuovo database utilizzando il cmdlet **Set-CsArchivingServer** .</span><span class="sxs-lookup"><span data-stu-id="dd298-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="dd298-153">Nell'esempio seguente viene modificata la posizione del database di archiviazione per il server di archiviazione ArchivingServer: atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="dd298-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="dd298-154">In questo esempio, il nuovo database si trova in ArchivingDatabase: ATL-SQL-001.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="dd298-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


