---
title: 'Lync Server 2013: modifica delle opzioni del database di archiviazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a820ca891ceb8196f8b4e0d2e023799f36e9e9ca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="f4dec-102">Modifica delle opzioni del database di archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4dec-102">Changing Archiving database options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4dec-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f4dec-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f4dec-104">Se si distribuisce l'archiviazione utilizzando l'archiviazione di SQL Server per l'archiviazione di un utente, è possibile apportare le modifiche apportate ai database seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4dec-104">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="f4dec-105">Utilizzare un database di SQL Server diverso per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f4dec-105">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="f4dec-106">Sono inclusi il database di archiviazione principale e qualsiasi database utilizzato per il mirroring di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f4dec-106">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="f4dec-107">Passare all'integrazione di Microsoft Exchange per archiviare i dati di archiviazione e i file sui server Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f4dec-107">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="f4dec-108">Se tutti gli utenti sono ospitati nei server Exchange 2013 e si desidera utilizzare lo spazio di archiviazione di Microsoft Exchange per tutti gli utenti nella distribuzione, è necessario rimuovere i database dell'archivio SQL Server dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="f4dec-108">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="f4dec-109">Per apportare una o più di queste modifiche, è necessario eseguire Generatore di topologie, apportare le modifiche e quindi ripubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="f4dec-109">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="f4dec-110">Per eseguire questa operazione, è possibile utilizzare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="f4dec-110">You can use Topology Builder to do this.</span></span> <span data-ttu-id="f4dec-111">Non specificare l' **Archivio SQL Server di archiviazione** o abilitare le informazioni sul **mirroring dell'archivio SQL Server** , a meno che non siano presenti utenti di Lync che non sono ospitati nei server Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f4dec-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="f4dec-112">Per modificare l'opzione del database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="f4dec-112">To change your archiving database option</span></span>

1.  <span data-ttu-id="f4dec-113">In un computer in cui è in esecuzione Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, eseguire l'accesso utilizzando un account membro del gruppo utenti locali (o un account con diritti utente equivalenti).</span><span class="sxs-lookup"><span data-stu-id="f4dec-113">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4dec-114">È possibile definire una topologia utilizzando un account membro del gruppo Users locale, ma per pubblicare una topologia, che è necessaria per aggiungere un componente alla topologia, è necessario utilizzare un account che sia membro del gruppo <STRONG>Domain Admins</STRONG> e del gruppo <STRONG>RTCUniversalServerAdmins</STRONG> e che disponga di autorizzazioni di controllo completo (ovvero lettura, scrittura e modifica) nella condivisione file utilizzata per l'archivio file di Lync Server 2013 (ovvero in modo che il generatore di topologie possa configurare gli elenchi di controllo di accesso discrezionale necessari ( DACL) oppure un account con diritti equivalenti.</span><span class="sxs-lookup"><span data-stu-id="f4dec-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="f4dec-115">Avviare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="f4dec-115">Start Topology Builder.</span></span>

3.  <span data-ttu-id="f4dec-116">Nell'albero della console accedere al pool Front End in cui è stata distribuita Archiviazione e fare clic sul nome del pool Front End in cui si vuole modificare le opzioni di database.</span><span class="sxs-lookup"><span data-stu-id="f4dec-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="f4dec-117">Nel menu **Azione** fare clic su **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f4dec-117">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="f4dec-118">Nella finestra di dialogo **Modifica proprietà** fare clic su **Generale**.</span><span class="sxs-lookup"><span data-stu-id="f4dec-118">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="f4dec-119">Scorrere verso il basso fino ad **Archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="f4dec-119">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="f4dec-120">In **Archiviazione** seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="f4dec-120">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="f4dec-121">Per passare a un archivio SQL Server esistente diverso, nella casella di riepilogo a discesa in **Archivio SQL Server archiviazione** seguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="f4dec-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="f4dec-122">Per usare un archivio SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio SQL Server che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="f4dec-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="f4dec-123">Per specificare un nuovo archivio SQL Server, fare clic su **Nuovo**, quindi nella finestra di dialogo **Definire un nuovo archivio SQL Server** seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="f4dec-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="f4dec-124">Per usare un archivio SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio SQL Server che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="f4dec-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="f4dec-125">Per specificare un nuovo archivio SQL Server, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4dec-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="f4dec-126">In **FQDN SQL Server**specificare il nome di dominio completo del server in cui si desidera creare il nuovo archivio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f4dec-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="f4dec-127">Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="f4dec-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="f4dec-128">Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="f4dec-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="f4dec-129">Per aggiungere l'archivio SQL Server per il mirroring o passare a un archivio SQL Server esistente diverso per il mirroring dell'archivio SQL Server, selezionare **Abilita mirroring dell'archivio SQL Server**, quindi procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="f4dec-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="f4dec-130">Per utilizzare un archivio SQL Server esistente per il mirroring, nella casella di riepilogo a discesa **mirror archivio SQL Server archiviazione** fare clic sul nome dell'archivio SQL Server che si desidera utilizzare per il mirroring.</span><span class="sxs-lookup"><span data-stu-id="f4dec-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="f4dec-131">Per specificare un nuovo archivio SQL Server per il mirroring, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4dec-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="f4dec-132">In **FQDN SQL Server**specificare il nome di dominio completo di SQL Server in cui si desidera creare il nuovo archivio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f4dec-132">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="f4dec-133">Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="f4dec-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="f4dec-134">Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="f4dec-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="f4dec-135">Se si Abilita il mirroring di SQL Server e si desidera aggiungere o modificare un controllo del mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare l'integrità del server SQL Server primario e delle istanze di mirroring), selezionare la casella utilizza verifica del **mirroring di SQL Server per abilitare il failover automatico** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4dec-135">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="f4dec-136">In **FQDN SQL Server**specificare il nome di dominio completo del server in cui si desidera creare il nuovo controllo del mirroring di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f4dec-136">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="f4dec-137">Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare per il controllo di mirroring.</span><span class="sxs-lookup"><span data-stu-id="f4dec-137">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="f4dec-138">Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="f4dec-138">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="f4dec-139">Per passare all'integrazione di Microsoft Exchange per archiviare i dati di archiviazione e i file sui server Exchange 2013 (se tutti gli utenti della distribuzione sono ospitati nei server Exchange 2013), eliminare tutte le informazioni per i database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f4dec-139">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f4dec-140">Se si dispone di utenti Lync che non sono ospitati nei server Exchange 2013, non eliminare le informazioni sull'archivio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f4dec-140">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="f4dec-141">Per salvare la configurazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4dec-141">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f4dec-142">Le modifiche apportate in Generatore di topologie non sono effettive finché non si pubblica la nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="f4dec-142">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="f4dec-143">Per ulteriori informazioni, vedere <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topologie to Add Archiving Databases in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f4dec-143">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

