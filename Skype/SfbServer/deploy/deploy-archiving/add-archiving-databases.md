---
title: Aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Riepilogo: leggere questo argomento per informazioni su come aggiungere database di archiviazione alla distribuzione di Skype for Business Server.'
ms.openlocfilehash: f7642cb79f73ab519938ddcb680f8450347b943d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820676"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a><span data-ttu-id="51ef8-103">Aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="51ef8-103">Add archiving databases to an existing deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="51ef8-104">**Riepilogo:** Leggere questo argomento per informazioni su come aggiungere database di archiviazione alla distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="51ef8-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="51ef8-105">È necessario includere l'archiviazione nella topologia prima di poter configurare la distribuzione in modo che supporti l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="51ef8-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="51ef8-106">Nelle informazioni contenute in questo argomento viene descritto come utilizzare il generatore di topologie per:</span><span class="sxs-lookup"><span data-stu-id="51ef8-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="51ef8-107">Aggiungere un database di archiviazione alla topologia.</span><span class="sxs-lookup"><span data-stu-id="51ef8-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="51ef8-108">Pubblicare la topologia aggiornata per aggiungere il database di archiviazione alla distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="51ef8-108">Publish the updated topology to add the archiving database to your Skype for Business Server deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="51ef8-109">Se si desidera utilizzare l'integrazione di Microsoft Exchange per archiviare i dati di archiviazione e i file nei server di Exchange per tutti gli utenti nella distribuzione, non specificare l' **Archivio SQL Server di archiviazione** o utilizzare le informazioni sul **mirroring dell'archivio SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="51ef8-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="51ef8-110">Aggiungere un database di archiviazione alla topologia</span><span class="sxs-lookup"><span data-stu-id="51ef8-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="51ef8-111">In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, eseguire l'accesso utilizzando un account membro del gruppo utenti locali (o un account con diritti utente equivalenti).</span><span class="sxs-lookup"><span data-stu-id="51ef8-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="51ef8-112">Avviare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="51ef8-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="51ef8-113">Nell'albero della console, passare al pool Front end in cui si desidera distribuire l'archiviazione, quindi fare clic sul nome del pool Front end in cui si desidera distribuire l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="51ef8-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="51ef8-114">Nel menu **Azione** fare clic su **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="51ef8-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="51ef8-115">Nella finestra di dialogo **Modifica proprietà** fare clic su **Generale**.</span><span class="sxs-lookup"><span data-stu-id="51ef8-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="51ef8-116">Scorrere verso il basso fino ad **Archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="51ef8-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="51ef8-117">Selezionare la casella di controllo **archiviazione** .</span><span class="sxs-lookup"><span data-stu-id="51ef8-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="51ef8-118">In **Archivio SQL Server di archiviazione** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ef8-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="51ef8-119">Per usare un archivio SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio SQL Server che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="51ef8-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="51ef8-120">Se tutti gli utenti sono ospitati in Microsoft Exchange Server 2013 o superiori, è possibile archiviare le comunicazioni Skype for business per tutti gli utenti in Exchange.</span><span class="sxs-lookup"><span data-stu-id="51ef8-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="51ef8-121">In questo caso, non è necessario configurare l'archivio di archiviazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="51ef8-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="51ef8-122">Per specificare un nuovo archivio SQL Server, fare clic su **nuovo** e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ef8-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="51ef8-123">In **FQDN SQL Server** specificare il nome di dominio completo del server in cui si desidera creare il nuovo archivio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="51ef8-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="51ef8-124">Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="51ef8-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="51ef8-125">Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="51ef8-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="51ef8-126">Se si desidera utilizzare il mirroring dell'archivio SQL Server, selezionare **Abilita mirroring dell'archivio SQL Server** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ef8-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="51ef8-127">Per utilizzare un archivio SQL Server esistente per il mirroring, nella casella di riepilogo a discesa **mirror archivio SQL Server archiviazione** fare clic sul nome dell'archivio SQL Server che si desidera utilizzare per il mirroring.</span><span class="sxs-lookup"><span data-stu-id="51ef8-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="51ef8-128">Per specificare un nuovo archivio SQL Server per il mirroring, fare clic su **nuovo** e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ef8-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
     <span data-ttu-id="51ef8-129">a.</span><span class="sxs-lookup"><span data-stu-id="51ef8-129">a.</span></span> <span data-ttu-id="51ef8-130">In **FQDN SQL Server** specificare il nome di dominio completo di SQL Server in cui si desidera creare il nuovo archivio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="51ef8-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
     <span data-ttu-id="51ef8-131">b.</span><span class="sxs-lookup"><span data-stu-id="51ef8-131">b.</span></span> <span data-ttu-id="51ef8-132">Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="51ef8-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
     <span data-ttu-id="51ef8-133">c.</span><span class="sxs-lookup"><span data-stu-id="51ef8-133">c.</span></span> <span data-ttu-id="51ef8-134">Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="51ef8-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="51ef8-135">Se si Abilita il mirroring di SQL Server e si desidera includere un controllo del mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare l'integrità delle istanze di SQL Server e del mirror principale), selezionare la casella di testo **utilizza il server di verifica del mirroring di SQL per abilitare il failover automatico** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ef8-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
     <span data-ttu-id="51ef8-136">a.</span><span class="sxs-lookup"><span data-stu-id="51ef8-136">a.</span></span> <span data-ttu-id="51ef8-137">In **FQDN SQL Server** specificare il nome di dominio completo del server in cui si desidera creare il nuovo controllo del mirroring di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="51ef8-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
     <span data-ttu-id="51ef8-138">b.</span><span class="sxs-lookup"><span data-stu-id="51ef8-138">b.</span></span> <span data-ttu-id="51ef8-139">Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare per il controllo di mirroring.</span><span class="sxs-lookup"><span data-stu-id="51ef8-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
     <span data-ttu-id="51ef8-140">c.</span><span class="sxs-lookup"><span data-stu-id="51ef8-140">c.</span></span> <span data-ttu-id="51ef8-141">Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="51ef8-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="51ef8-142">Per salvare la configurazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="51ef8-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="51ef8-143">Pubblicare la topologia aggiornata per aggiungere un database di archiviazione alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="51ef8-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="51ef8-144">In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, eseguire l'accesso utilizzando un account membro del gruppo utenti locali (o un account con diritti utente equivalenti).</span><span class="sxs-lookup"><span data-stu-id="51ef8-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="51ef8-145">È possibile definire una topologia utilizzando un account membro del gruppo Users locale, ma per pubblicare una topologia, necessaria per aggiungere un server alla topologia. è necessario utilizzare un account che sia membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** e che disponga di autorizzazioni di controllo completo (lettura, scrittura e modifica) sulla condivisione file utilizzata per l'archivio file di Skype for Business Server, in modo che generatore di topologie possa configurare l'elenco di controllo di accesso discrezionale necessario o un account con diritti equivalenti.</span><span class="sxs-lookup"><span data-stu-id="51ef8-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="51ef8-146">Aprire la topologia creata nella sezione precedente utilizzando Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="51ef8-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="51ef8-147">Nell'albero della console fare clic con il pulsante destro del mouse su **Skype for Business Server** e quindi scegliere **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="51ef8-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="51ef8-148">Nella pagina **Pubblicare la topologia** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="51ef8-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="51ef8-149">Nella pagina **Crea altri database** verificare che il database sia selezionato e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="51ef8-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="51ef8-150">Se non si dispone delle autorizzazioni appropriate per la creazione di database, è possibile annullare la selezione del database e un utente con le autorizzazioni appropriate può creare il database.</span><span class="sxs-lookup"><span data-stu-id="51ef8-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="51ef8-151">> solo i database di SQL Server dedicati possono essere installati tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="51ef8-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="51ef8-152">I database in computer SQL Server collocati con altri componenti server devono essere installati eseguendo il programma di installazione locale nel computer in questione.</span><span class="sxs-lookup"><span data-stu-id="51ef8-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="51ef8-153">Nella pagina **Pubblicazione guidata completata** verificare che la topologia sia stata pubblicata correttamente e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="51ef8-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="51ef8-154">Dopo aver pubblicato la topologia, è necessario configurare le opzioni e i criteri per l'archiviazione, prima che sia possibile archiviare qualsiasi contenuto.</span><span class="sxs-lookup"><span data-stu-id="51ef8-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="51ef8-155">Per ulteriori informazioni, vedere [configurare le opzioni di archiviazione per Skype for Business Server](configure-archiving-options.md) e [configurare i criteri di archiviazione per Skype for Business Server](configure-archiving-policies.md).</span><span class="sxs-lookup"><span data-stu-id="51ef8-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span></span> 
  

