---
title: 'Lync Server 2013: aggiunta di database di archiviazione alla topologia di Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe77c57050d6d6c70d5818405fd657d5a8fd3f0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a><span data-ttu-id="a82ae-102">Aggiunta di database di archiviazione alla topologia di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a82ae-102">Adding Archiving databases to the Lync Server 2013 topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a82ae-103">_**Argomento Ultima modifica:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="a82ae-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="a82ae-104">È necessario incorporare l'archiviazione nella topologia prima di poter configurare la distribuzione per supportare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="a82ae-104">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="a82ae-105">Le informazioni contenute in questo argomento spiegano come usare generatore di topologia per aggiungere l'archiviazione alla topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="a82ae-105">The information in this topic explains how to use Topology Builder to add archiving to your existing topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a82ae-106">Se si vuole usare l'integrazione di Microsoft Exchange per archiviare i dati e i file di archiviazione nei server di Exchange 2013 per tutti gli utenti della distribuzione, non specificare l' <STRONG>archiviazione di SQL Server Store</STRONG> o usare le informazioni di <STRONG>mirroring di SQL Server Store</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="a82ae-106">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers for all your users in your deployment, do not specify <STRONG>Archiving SQL Server store</STRONG> or <STRONG>Use SQL Server Store mirroring</STRONG> information.</span></span>



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a><span data-ttu-id="a82ae-107">Per aggiungere il supporto di archiviazione del database alla topologia</span><span class="sxs-lookup"><span data-stu-id="a82ae-107">To add Archiving database support to your topology</span></span>

1.  <span data-ttu-id="a82ae-108">In un computer che esegue Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, accedere utilizzando un account membro del gruppo utenti locali o un account con diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="a82ae-108">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a82ae-109">Puoi definire una topologia usando un account che è un membro del gruppo utenti locali, ma per pubblicare una topologia, necessaria per aggiungere un server alla topologia. è necessario usare un account che sia un membro del gruppo <STRONG>Domain Admins</STRONG> e del gruppo <STRONG>RTCUniversalServerAdmins</STRONG> e che disponga delle autorizzazioni di controllo completo (ovvero, lettura, scrittura e modifica) nella condivisione di file in uso per l'archivio di file di Lync Server 2013, in modo che il generatore di topologia possa configurare l'elenco di controllo di accesso discrezionale richiesto (DACL). o un account con diritti equivalenti.</span><span class="sxs-lookup"><span data-stu-id="a82ae-109">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="a82ae-110">Avviare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="a82ae-110">Start Topology Builder.</span></span>

3.  <span data-ttu-id="a82ae-111">Nell'albero della console passare al pool Front-end in cui si vuole distribuire l'archiviazione e quindi fare clic sul nome del pool Front end in cui si vuole distribuire l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="a82ae-111">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy Archiving.</span></span>

4.  <span data-ttu-id="a82ae-112">Nel menu **azione** fare clic su **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-112">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="a82ae-113">Nella finestra di dialogo **modifica proprietà** fare clic su **generale**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-113">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="a82ae-114">Scorrere verso il basso fino all' **archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-114">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="a82ae-115">Selezionare la casella di controllo **archiviazione** .</span><span class="sxs-lookup"><span data-stu-id="a82ae-115">Select the **Archiving** check box.</span></span>

8.  <span data-ttu-id="a82ae-116">In **archiviazione SQL Server Store** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a82ae-116">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
      - <span data-ttu-id="a82ae-117">Per usare un archivio di SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio di SQL Server che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="a82ae-117">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="a82ae-118">Se tutti gli utenti sono ospitati in Microsoft Exchange Server 2013 o versioni successive, è possibile archiviare le comunicazioni di Lync per tutti gli utenti in Exchange.</span><span class="sxs-lookup"><span data-stu-id="a82ae-118">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Lync communications for all your users in Exchange.</span></span> <span data-ttu-id="a82ae-119">In questo caso, non è necessario configurare l'archivio di archiviazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a82ae-119">In this case, you don’t need to configure SQL Server Archiving store.</span></span>
    
      - <span data-ttu-id="a82ae-120">Per specificare un nuovo archivio di SQL Server, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a82ae-120">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
        
          - <span data-ttu-id="a82ae-121">In **FQDN di SQL Server**specificare il nome di dominio completo del server in cui si vuole creare il nuovo archivio di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a82ae-121">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
        
          - <span data-ttu-id="a82ae-122">Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="a82ae-122">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
        
          - <span data-ttu-id="a82ae-123">Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="a82ae-123">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

9.  <span data-ttu-id="a82ae-124">Se si vuole usare il mirroring di SQL Server Store, selezionare **Abilita mirroring di SQL Server Store**e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a82ae-124">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
      - <span data-ttu-id="a82ae-125">Per usare un archivio di SQL Server esistente per il mirroring, nella casella di riepilogo a discesa **archiviazione di SQL Server dell'archivio** , fare clic sul nome dell'archivio di SQL Server che si vuole usare per il mirroring.</span><span class="sxs-lookup"><span data-stu-id="a82ae-125">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
      - <span data-ttu-id="a82ae-126">Per specificare un nuovo archivio di SQL Server per il mirroring, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio di SQL Server** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a82ae-126">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
        
        1.  <span data-ttu-id="a82ae-127">In **FQDN di SQL Server**specificare il nome di dominio completo di SQL Server in cui si vuole creare il nuovo archivio di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a82ae-127">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
        
        2.  <span data-ttu-id="a82ae-128">Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="a82ae-128">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
        
        3.  <span data-ttu-id="a82ae-129">Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="a82ae-129">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="a82ae-130">Se si Abilita il mirroring di SQL Server e si vuole includere un witness di mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare l'integrità delle istanze di SQL Server e mirror principali), selezionare la casella di controllo **USA mirroring di SQL Server per abilitare il failover automatico** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a82ae-130">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
        
        1.  <span data-ttu-id="a82ae-131">In **FQDN di SQL Server**specificare il nome di dominio completo del server in cui si vuole creare il nuovo witness di mirroring di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a82ae-131">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
        
        2.  <span data-ttu-id="a82ae-132">Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare per il witness di mirroring.</span><span class="sxs-lookup"><span data-stu-id="a82ae-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
        
        3.  <span data-ttu-id="a82ae-133">Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="a82ae-133">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

10. <span data-ttu-id="a82ae-134">Per salvare la configurazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-134">To save the configuration, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

