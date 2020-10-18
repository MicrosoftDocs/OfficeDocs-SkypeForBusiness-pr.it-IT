---
title: 'Lync Server 2013: aggiunta dei database di archiviazione alla topologia di Lync Server 2013'
description: 'Lync Server 2013: aggiunta dei database di archiviazione alla topologia di Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12387c06bc55775ef824c061228a68021046c113
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573042"
---
# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a><span data-ttu-id="98dbf-103">Aggiunta dei database di archiviazione alla topologia di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98dbf-103">Adding Archiving databases to the Lync Server 2013 topology</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98dbf-104">_**Ultimo argomento modificato:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="98dbf-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="98dbf-105">È necessario includere l'archiviazione nella topologia prima di poter configurare la distribuzione in modo che supporti l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="98dbf-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="98dbf-106">Nelle informazioni contenute in questo argomento viene descritto come utilizzare il generatore di topologie per aggiungere l'archiviazione alla topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="98dbf-106">The information in this topic explains how to use Topology Builder to add archiving to your existing topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98dbf-107">Se si desidera utilizzare l'integrazione di Microsoft Exchange per archiviare i dati di archiviazione e i file sui server Exchange 2013 per tutti gli utenti nella distribuzione, non specificare l' <STRONG>Archivio SQL Server di archiviazione</STRONG> o utilizzare le informazioni sul <STRONG>mirroring dell'archivio SQL Server</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="98dbf-107">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers for all your users in your deployment, do not specify <STRONG>Archiving SQL Server store</STRONG> or <STRONG>Use SQL Server Store mirroring</STRONG> information.</span></span>



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a><span data-ttu-id="98dbf-108">Per aggiungere il supporto del database di archiviazione alla topologia</span><span class="sxs-lookup"><span data-stu-id="98dbf-108">To add Archiving database support to your topology</span></span>

1.  <span data-ttu-id="98dbf-109">In un computer in cui è in esecuzione Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, eseguire l'accesso utilizzando un account membro del gruppo utenti locali (o un account con diritti utente equivalenti).</span><span class="sxs-lookup"><span data-stu-id="98dbf-109">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98dbf-110">È possibile definire una topologia utilizzando un account membro del gruppo utenti locali, ma per pubblicare una topologia, necessaria per aggiungere un server alla topologia, è necessario utilizzare un account membro del gruppo <STRONG>Domain Admins</STRONG> e del gruppo <STRONG>RTCUniversalServerAdmins</STRONG> . e che dispone di autorizzazioni di controllo completo (ovvero lettura, scrittura e modifica) sulla condivisione file utilizzata per l'archivio file di Lync Server 2013 (ovvero, in modo che generatore di topologie sia in grado di configurare l'elenco di controllo di accesso discrezionale necessario o un account con diritti equivalenti.</span><span class="sxs-lookup"><span data-stu-id="98dbf-110">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="98dbf-111">Avviare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="98dbf-111">Start Topology Builder.</span></span>

3.  <span data-ttu-id="98dbf-112">Nell'albero della console, passare al pool Front end in cui si desidera distribuire l'archiviazione, quindi fare clic sul nome del pool Front end in cui si desidera distribuire l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="98dbf-112">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy Archiving.</span></span>

4.  <span data-ttu-id="98dbf-113">Nel menu **Azione** fare clic su **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="98dbf-113">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="98dbf-114">Nella finestra di dialogo **Modifica proprietà** fare clic su **Generale**.</span><span class="sxs-lookup"><span data-stu-id="98dbf-114">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="98dbf-115">Scorrere verso il basso fino ad **Archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="98dbf-115">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="98dbf-116">Selezionare la casella di controllo **archiviazione** .</span><span class="sxs-lookup"><span data-stu-id="98dbf-116">Select the **Archiving** check box.</span></span>

8.  <span data-ttu-id="98dbf-117">In **Archivio SQL Server di archiviazione** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="98dbf-117">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
      - <span data-ttu-id="98dbf-118">Per usare un archivio SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio SQL Server che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="98dbf-118">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="98dbf-119">Se tutti gli utenti sono ospitati in Microsoft Exchange Server 2013 o superiori, è possibile archiviare le comunicazioni di Lync per tutti gli utenti in Exchange.</span><span class="sxs-lookup"><span data-stu-id="98dbf-119">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Lync communications for all your users in Exchange.</span></span> <span data-ttu-id="98dbf-120">In questo caso, non è necessario configurare l'archivio di archiviazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="98dbf-120">In this case, you don’t need to configure SQL Server Archiving store.</span></span>
    
      - <span data-ttu-id="98dbf-121">Per specificare un nuovo archivio SQL Server, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="98dbf-121">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
        
          - <span data-ttu-id="98dbf-122">In **FQDN SQL Server**specificare il nome di dominio completo del server in cui si desidera creare il nuovo archivio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="98dbf-122">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
        
          - <span data-ttu-id="98dbf-123">Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="98dbf-123">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
        
          - <span data-ttu-id="98dbf-124">Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="98dbf-124">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

9.  <span data-ttu-id="98dbf-125">Se si desidera utilizzare il mirroring dell'archivio SQL Server, selezionare **Abilita mirroring dell'archivio SQL Server**e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="98dbf-125">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
      - <span data-ttu-id="98dbf-126">Per utilizzare un archivio SQL Server esistente per il mirroring, nella casella di riepilogo a discesa **mirror archivio SQL Server archiviazione** fare clic sul nome dell'archivio SQL Server che si desidera utilizzare per il mirroring.</span><span class="sxs-lookup"><span data-stu-id="98dbf-126">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
      - <span data-ttu-id="98dbf-127">Per specificare un nuovo archivio SQL Server per il mirroring, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="98dbf-127">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
        
        1.  <span data-ttu-id="98dbf-128">In **FQDN SQL Server**specificare il nome di dominio completo di SQL Server in cui si desidera creare il nuovo archivio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="98dbf-128">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
        
        2.  <span data-ttu-id="98dbf-129">Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="98dbf-129">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
        
        3.  <span data-ttu-id="98dbf-130">Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="98dbf-130">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="98dbf-131">Se si Abilita il mirroring di SQL Server e si desidera includere un controllo del mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare l'integrità del server di SQL Server e delle istanze di mirror primario), selezionare la casella utilizza verifica del **mirroring di SQL Server per abilitare il failover automatico** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="98dbf-131">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
        
        1.  <span data-ttu-id="98dbf-132">In **FQDN SQL Server**specificare il nome di dominio completo del server in cui si desidera creare il nuovo controllo del mirroring di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="98dbf-132">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
        
        2.  <span data-ttu-id="98dbf-133">Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare per il controllo di mirroring.</span><span class="sxs-lookup"><span data-stu-id="98dbf-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
        
        3.  <span data-ttu-id="98dbf-134">Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="98dbf-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

10. <span data-ttu-id="98dbf-135">Per salvare la configurazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="98dbf-135">To save the configuration, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

