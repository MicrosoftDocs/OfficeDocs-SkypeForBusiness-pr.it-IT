---
title: 'Lync Server 2013: ripristino di un server back-end Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bd57054505b3200f63bed8a60c47b400f7e7642
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a><span data-ttu-id="05cf5-102">Ripristino di un server back-end Enterprise Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05cf5-102">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05cf5-103">_**Argomento Ultima modifica:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="05cf5-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="05cf5-104">Usare la procedura descritta in questo argomento nei due casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="05cf5-104">Use the procedure described in this topic in the following two cases:</span></span>

  - <span data-ttu-id="05cf5-105">I database primari e mirror di un server back-end Enterprise Edition con mirroring non riescono.</span><span class="sxs-lookup"><span data-stu-id="05cf5-105">Both the primary and mirror databases of a mirrored Enterprise Edition Back End Server fail.</span></span>

  - <span data-ttu-id="05cf5-106">Un server back-end Enterprise Edition che non ha un mirroring non riesce.</span><span class="sxs-lookup"><span data-stu-id="05cf5-106">An Enterprise Edition Back End Server that is not mirrored fails.</span></span>

<span data-ttu-id="05cf5-107">Se si ha un back-end di Enterprise Edition con mirroring e il database mirror o PRIMARY non riesce, vedere [ripristino di un server back-end aziendale con mirroring in Lync server 2013-principale](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) per il ripristino del database primario e [ripristino di un server back-end di Enterprise Edition con mirroring in Lync Server 2013-mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) per il ripristino dello specchio.</span><span class="sxs-lookup"><span data-stu-id="05cf5-107">If you have a mirrored Enterprise Edition Back End and only the mirror or primary database fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) for restoring the primary database, and [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) for restoring the mirror.</span></span>

<span data-ttu-id="05cf5-108">Se l'archivio di gestione centrale non riesce, vedere [ripristino del server che ospita l'archivio di gestione centrale in Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="05cf5-108">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="05cf5-109">Se un server membro di Enterprise Edition che non è il server back-end non riesce, vedere [ripristino di un server membro di Enterprise Edition in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="05cf5-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="05cf5-110">Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema.</span><span class="sxs-lookup"><span data-stu-id="05cf5-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="05cf5-111">È possibile usare questa immagine come punto di rollback, in caso di problemi durante il ripristino.</span><span class="sxs-lookup"><span data-stu-id="05cf5-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="05cf5-112">Potrebbe essere necessario prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare di nuovo i certificati.</span><span class="sxs-lookup"><span data-stu-id="05cf5-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a><span data-ttu-id="05cf5-113">Per ripristinare un server back-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="05cf5-113">To restore an Enterprise Edition Back End Server</span></span>

1.  <span data-ttu-id="05cf5-114">Iniziare con un nuovo server pulito o con lo stesso nome di dominio completo (FQDN) del computer non riuscito, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.</span><span class="sxs-lookup"><span data-stu-id="05cf5-114">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="05cf5-115">Per eseguire questo passaggio, seguire le procedure di distribuzione del server dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="05cf5-115">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="05cf5-116">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere al server che si sta ripristinando.</span><span class="sxs-lookup"><span data-stu-id="05cf5-116">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="05cf5-117">Installare SQL Server 2012 o SQL Server 2008 R2, mantenendo i nomi delle istanze come prima dell'errore.</span><span class="sxs-lookup"><span data-stu-id="05cf5-117">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="05cf5-118">A seconda della distribuzione, il server back-end può includere più database collocati o separati.</span><span class="sxs-lookup"><span data-stu-id="05cf5-118">Depending on your deployment, the Back End Server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="05cf5-119">Seguire la stessa procedura per installare SQL Server usato in origine per distribuire il server, incluse le autorizzazioni di SQL Server e gli accessi.</span><span class="sxs-lookup"><span data-stu-id="05cf5-119">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

    
    </div>

4.  <span data-ttu-id="05cf5-120">Dopo l'installazione di SQL Server, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05cf5-120">After you install SQL Server, perform the following:</span></span>
    
    1.  <span data-ttu-id="05cf5-121">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="05cf5-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="05cf5-122">Fare clic su **Scarica topologia dalla distribuzione esistente**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="05cf5-122">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="05cf5-123">Selezionare la topologia e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="05cf5-123">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="05cf5-124">Fare clic su **Sì** per confermare la selezione.</span><span class="sxs-lookup"><span data-stu-id="05cf5-124">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="05cf5-125">Fare clic con il pulsante destro del mouse sul nodo **Lync Server 2013** e quindi scegliere **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="05cf5-125">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>
    
    5.  <span data-ttu-id="05cf5-126">Seguire la procedura guidata **pubblica la topologia** .</span><span class="sxs-lookup"><span data-stu-id="05cf5-126">Follow the **Publish the Topology** wizard.</span></span> <span data-ttu-id="05cf5-127">Nella pagina **Crea database** selezionare i database che si desidera ricreare.</span><span class="sxs-lookup"><span data-stu-id="05cf5-127">On the **Create databases** page, select the databases that you want to re-create.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="05cf5-128">Nella pagina <STRONG>Crea database</STRONG> sono visualizzati solo database autonomi.</span><span class="sxs-lookup"><span data-stu-id="05cf5-128">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="05cf5-129">Se si esegue il ripristino di un back-end con mirroring, continuare a seguire il resto della procedura guidata fino a quando non viene visualizzato il messaggio **Crea mirror database** .</span><span class="sxs-lookup"><span data-stu-id="05cf5-129">If you are restoring a Back End that was mirrored, continue to follow the rest of the wizard until the prompt **Create Mirror Database** appears.</span></span> <span data-ttu-id="05cf5-130">Selezionare il database che si vuole installare e completare il processo.</span><span class="sxs-lookup"><span data-stu-id="05cf5-130">Select the database that you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="05cf5-131">Seguire il resto della procedura guidata e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="05cf5-131">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="05cf5-132">Invece di eseguire Generatore di topologie, è possibile usare il cmdlet <STRONG>Install-CsDatabase</STRONG> per creare ogni database e il cmdlet <STRONG>Install-CsMirrorDatabase</STRONG> per configurare il mirroring.</span><span class="sxs-lookup"><span data-stu-id="05cf5-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="05cf5-133">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="05cf5-133">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

5.  <span data-ttu-id="05cf5-134">Ripristinare i dati degli utenti eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05cf5-134">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="05cf5-135">Copiare ExportedUserData. zip da $Backup\\ a una directory locale.</span><span class="sxs-lookup"><span data-stu-id="05cf5-135">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="05cf5-136">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="05cf5-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    3.  <span data-ttu-id="05cf5-137">Prima di ripristinare i dati utente, è necessario arrestare i servizi Lync.</span><span class="sxs-lookup"><span data-stu-id="05cf5-137">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="05cf5-138">A tale scopo, digitare:</span><span class="sxs-lookup"><span data-stu-id="05cf5-138">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    4.  <span data-ttu-id="05cf5-139">Per ripristinare i dati utente, nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="05cf5-139">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="05cf5-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="05cf5-140">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  <span data-ttu-id="05cf5-141">Riavviare i servizi Lync digitando:</span><span class="sxs-lookup"><span data-stu-id="05cf5-141">Restart Lync Services by typing:</span></span>
        
            Start-CsWindowsService

6.  <span data-ttu-id="05cf5-142">Se il gruppo di risposte è stato distribuito in questo pool, ripristinare i dati di configurazione del gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="05cf5-142">If you deployed Response Group on this pool, restore the Response Group configuration data.</span></span> <span data-ttu-id="05cf5-143">Per informazioni dettagliate, vedere [ripristino delle impostazioni dei gruppi di risposte in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="05cf5-143">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

7.  <span data-ttu-id="05cf5-144">Se si sta ripristinando un server di back-end che includeva l'archiviazione o il monitoraggio dei database, ripristinare i dati di archiviazione o monitoraggio tramite uno strumento di SQL Server, ad esempio SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="05cf5-144">If you are restoring a Back End Server that included Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="05cf5-145">Per informazioni dettagliate, vedere [ripristinare il monitoraggio o l'archiviazione dei dati in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="05cf5-145">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

