---
title: Aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Riepilogo: leggere questo argomento per informazioni su come aggiungere database di archiviazione alla distribuzione di Skype for Business Server.'
ms.openlocfilehash: 26cdd1befb695fbaf0656611ed65c7afa778af6c
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769049"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a><span data-ttu-id="54d27-103">Aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="54d27-103">Add archiving databases to an existing deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="54d27-104">**Riepilogo:** Leggere questo argomento per informazioni su come aggiungere database di archiviazione alla distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="54d27-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="54d27-105">È necessario incorporare l'archiviazione nella topologia prima di poter configurare la distribuzione per supportare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="54d27-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="54d27-106">Le informazioni contenute in questo argomento spiegano come usare generatore di topologia per:</span><span class="sxs-lookup"><span data-stu-id="54d27-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="54d27-107">Aggiungere un database di archiviazione alla topologia.</span><span class="sxs-lookup"><span data-stu-id="54d27-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="54d27-108">Pubblicare la topologia aggiornata per aggiungere il database di archiviazione alla distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="54d27-108">Publish the updated topology to add the archiving database to your Skype for Business Server deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="54d27-109">Se si vuole usare l'integrazione di Microsoft Exchange per archiviare i dati e i file di archiviazione nei server di Exchange per tutti gli utenti della distribuzione, non specificare l' **archiviazione di SQL Server Store** o usare le informazioni di **mirroring di SQL Server Store** .</span><span class="sxs-lookup"><span data-stu-id="54d27-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="54d27-110">Aggiungere un database di archiviazione alla topologia</span><span class="sxs-lookup"><span data-stu-id="54d27-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="54d27-111">In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, accedere utilizzando un account membro del gruppo utenti locali o un account con diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="54d27-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="54d27-112">Avviare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="54d27-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="54d27-113">Nell'albero della console passare al pool Front-end in cui si vuole distribuire l'archiviazione e quindi fare clic sul nome del pool Front end in cui si vuole distribuire l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="54d27-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="54d27-114">Nel menu **azione** fare clic su **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="54d27-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="54d27-115">Nella finestra di dialogo **modifica proprietà** fare clic su **generale**.</span><span class="sxs-lookup"><span data-stu-id="54d27-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="54d27-116">Scorrere verso il basso fino all' **archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="54d27-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="54d27-117">Selezionare la casella di controllo **archiviazione** .</span><span class="sxs-lookup"><span data-stu-id="54d27-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="54d27-118">In **archiviazione SQL Server Store** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="54d27-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="54d27-119">Per usare un archivio di SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio di SQL Server che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="54d27-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="54d27-120">Se tutti gli utenti sono ospitati in Microsoft Exchange Server 2013 o versioni successive, è possibile archiviare le comunicazioni Skype for business per tutti gli utenti in Exchange.</span><span class="sxs-lookup"><span data-stu-id="54d27-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="54d27-121">In questo caso, non è necessario configurare l'archivio di archiviazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="54d27-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="54d27-122">Per specificare un nuovo archivio di SQL Server, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="54d27-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="54d27-123">In **FQDN di SQL Server**specificare il nome di dominio completo del server in cui si vuole creare il nuovo archivio di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="54d27-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="54d27-124">Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="54d27-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="54d27-125">Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="54d27-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="54d27-126">Se si vuole usare il mirroring di SQL Server Store, selezionare **Abilita mirroring di SQL Server Store**e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="54d27-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="54d27-127">Per usare un archivio di SQL Server esistente per il mirroring, nella casella di riepilogo a discesa **archiviazione di SQL Server dell'archivio** , fare clic sul nome dell'archivio di SQL Server che si vuole usare per il mirroring.</span><span class="sxs-lookup"><span data-stu-id="54d27-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="54d27-128">Per specificare un nuovo archivio di SQL Server per il mirroring, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio di SQL Server** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="54d27-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
     <span data-ttu-id="54d27-129">un.</span><span class="sxs-lookup"><span data-stu-id="54d27-129">a.</span></span> <span data-ttu-id="54d27-130">In **FQDN di SQL Server**specificare il nome di dominio completo di SQL Server in cui si vuole creare il nuovo archivio di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="54d27-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
     <span data-ttu-id="54d27-131">b.</span><span class="sxs-lookup"><span data-stu-id="54d27-131">b.</span></span> <span data-ttu-id="54d27-132">Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="54d27-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
     <span data-ttu-id="54d27-133">c.</span><span class="sxs-lookup"><span data-stu-id="54d27-133">c.</span></span> <span data-ttu-id="54d27-134">Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="54d27-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="54d27-135">Se si Abilita il mirroring di SQL Server e si vuole includere un witness di mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare lo stato delle istanze principali di SQL Server e mirror), selezionare la casella di controllo **USA mirroring di SQL Server per abilitare il failover automatico** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="54d27-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
     <span data-ttu-id="54d27-136">un.</span><span class="sxs-lookup"><span data-stu-id="54d27-136">a.</span></span> <span data-ttu-id="54d27-137">In **FQDN di SQL Server**specificare il nome di dominio completo del server in cui si vuole creare il nuovo witness di mirroring di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="54d27-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
     <span data-ttu-id="54d27-138">b.</span><span class="sxs-lookup"><span data-stu-id="54d27-138">b.</span></span> <span data-ttu-id="54d27-139">Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare per il witness di mirroring.</span><span class="sxs-lookup"><span data-stu-id="54d27-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
     <span data-ttu-id="54d27-140">c.</span><span class="sxs-lookup"><span data-stu-id="54d27-140">c.</span></span> <span data-ttu-id="54d27-141">Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="54d27-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="54d27-142">Per salvare la configurazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="54d27-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="54d27-143">Pubblicare la topologia aggiornata per aggiungere un database di archiviazione alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="54d27-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="54d27-144">In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, accedere usando un account membro del gruppo utenti locali o un account con diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="54d27-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="54d27-145">Puoi definire una topologia usando un account che è un membro del gruppo utenti locali, ma per pubblicare una topologia, necessaria per aggiungere un server alla topologia. è necessario usare un account che sia membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** e che disponga delle autorizzazioni di controllo completo (lettura, scrittura e modifica) nella condivisione file in uso per l'archivio file di Skype for Business Server (in modo che il generatore di topologia possa configurare l'elenco di controllo di accesso discrezionale richiesto o un account con diritti equivalenti.</span><span class="sxs-lookup"><span data-stu-id="54d27-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="54d27-146">Aprire la topologia creata nella sezione precedente usando generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="54d27-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="54d27-147">Nell'albero della console fare clic con il pulsante destro del mouse su **Skype for Business Server**e quindi scegliere **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="54d27-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="54d27-148">Nella pagina **pubblica la topologia** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="54d27-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="54d27-149">Nella pagina **Crea database** verificare che il database sia selezionato e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="54d27-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="54d27-150">Se non si dispone delle autorizzazioni appropriate per la creazione di database, è possibile annullare la selezione del database e un utente con le autorizzazioni appropriate può creare il database.</span><span class="sxs-lookup"><span data-stu-id="54d27-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="54d27-151">> solo i database di SQL Server dedicati possono essere installati tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="54d27-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="54d27-152">I database di SQL Server che sono collocati con altri componenti del server devono essere installati eseguendo la configurazione locale nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="54d27-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="54d27-153">Nella pagina **completamento pubblicazione guidata** verificare che la topologia sia stata pubblicata correttamente e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="54d27-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="54d27-154">Dopo aver pubblicato la topologia, è necessario configurare le opzioni e i criteri per l'archiviazione prima che sia possibile archiviare qualsiasi contenuto.</span><span class="sxs-lookup"><span data-stu-id="54d27-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="54d27-155">Per informazioni dettagliate, vedere [configurare le opzioni di archiviazione per Skype for Business Server](configure-archiving-options.md) e [configurare i criteri di archiviazione per Skype for Business Server](configure-archiving-policies.md).</span><span class="sxs-lookup"><span data-stu-id="54d27-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span></span> 
  

