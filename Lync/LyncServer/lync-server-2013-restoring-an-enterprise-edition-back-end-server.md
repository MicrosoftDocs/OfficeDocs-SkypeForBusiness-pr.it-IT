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
ms.openlocfilehash: 9780963614a1d0f5049fdc5226391e2ee2b6d59c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511543"
---
# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a><span data-ttu-id="637cd-102">Ripristino di un server back-end Enterprise Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="637cd-102">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="637cd-103">_**Ultimo argomento modificato:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="637cd-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="637cd-104">Utilizzare la procedura descritta in questo argomento nei due casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="637cd-104">Use the procedure described in this topic in the following two cases:</span></span>

  - <span data-ttu-id="637cd-105">I database primari e mirror di un server back-end Enterprise Edition con mirroring hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="637cd-105">Both the primary and mirror databases of a mirrored Enterprise Edition Back End Server fail.</span></span>

  - <span data-ttu-id="637cd-106">Un server back-end Enterprise Edition che non ha mirroring ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="637cd-106">An Enterprise Edition Back End Server that is not mirrored fails.</span></span>

<span data-ttu-id="637cd-107">Se si dispone di un back-end Enterprise Edition con mirroring e solo del database mirror o primario ha esito negativo, vedere [Restoring a mirroring Enterprise Edition back end server in Lync server 2013-Primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) per il ripristino del database primario e [ripristino di un server back-end con mirroring Enterprise Edition in Lync Server 2013-mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) per il ripristino del mirror.</span><span class="sxs-lookup"><span data-stu-id="637cd-107">If you have a mirrored Enterprise Edition Back End and only the mirror or primary database fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) for restoring the primary database, and [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) for restoring the mirror.</span></span>

<span data-ttu-id="637cd-108">Se l'archivio di gestione centrale ha esito negativo, vedere [ripristino del server che ospita l'archivio di gestione centrale in Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="637cd-108">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="637cd-109">Se si verifica un errore di un server membro Enterprise Edition che non è il server back-end, vedere [Restoring an Enterprise Edition member server in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="637cd-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="637cd-110">Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema.</span><span class="sxs-lookup"><span data-stu-id="637cd-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="637cd-111">È possibile utilizzare questa immagine come punto di rollback, in caso di problemi durante il ripristino.</span><span class="sxs-lookup"><span data-stu-id="637cd-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="637cd-112">È possibile che si desideri prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare nuovamente i certificati.</span><span class="sxs-lookup"><span data-stu-id="637cd-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a><span data-ttu-id="637cd-113">Per ripristinare un server back-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="637cd-113">To restore an Enterprise Edition Back End Server</span></span>

1.  <span data-ttu-id="637cd-114">Iniziare con un server pulito o nuovo che abbia lo stesso nome di dominio completo (FQDN) del computer in cui si è verificato l'errore, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.</span><span class="sxs-lookup"><span data-stu-id="637cd-114">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="637cd-115">Seguire le procedure di distribuzione dei server dell'organizzazione per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="637cd-115">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="637cd-116">Da un account utente membro del gruppo RTCUniversalServerAdmins, eseguire l'accesso al server che si sta ripristinando.</span><span class="sxs-lookup"><span data-stu-id="637cd-116">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="637cd-117">Installare SQL Server 2012 o SQL Server 2008 R2, mantenendo i nomi delle istanze identici a quelli precedenti all'errore.</span><span class="sxs-lookup"><span data-stu-id="637cd-117">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="637cd-p103">A seconda della distribuzione, il server back-end può includere più database collocati o separati. Per installare SQL Server, eseguire la stessa procedura utilizzata originariamente per distribuire il server, inclusi gli account di accesso e le autorizzazioni di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="637cd-p103">Depending on your deployment, the Back End Server might include multiple collocated or separate databases. Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

    
    </div>

4.  <span data-ttu-id="637cd-120">Dopo aver installato SQL Server, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="637cd-120">After you install SQL Server, perform the following:</span></span>
    
    1.  <span data-ttu-id="637cd-121">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="637cd-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="637cd-122">Fare clic su **Scarica topologia dalla distribuzione esistente** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="637cd-122">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="637cd-p104">Selezionare la topologia e quindi fare clic su **Salva**. Fare clic su **Sì** per confermare la selezione.</span><span class="sxs-lookup"><span data-stu-id="637cd-p104">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="637cd-125">Fare clic con il pulsante destro del mouse sul nodo **Lync Server 2013** e quindi scegliere **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="637cd-125">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>
    
    5.  <span data-ttu-id="637cd-126">Seguire le istruzioni della procedura guidata **Pubblicare la topologia**.</span><span class="sxs-lookup"><span data-stu-id="637cd-126">Follow the **Publish the Topology** wizard.</span></span> <span data-ttu-id="637cd-127">Nella pagina **Crea database** selezionare i database che si desidera ricreare.</span><span class="sxs-lookup"><span data-stu-id="637cd-127">On the **Create databases** page, select the databases that you want to re-create.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="637cd-128">Nella pagina <STRONG>Creare database</STRONG> verranno visualizzati solo i database autonomi.</span><span class="sxs-lookup"><span data-stu-id="637cd-128">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="637cd-129">Se si esegue il ripristino di un back-end con mirroring, continuare a seguire il resto della procedura guidata fino a quando non viene visualizzato il prompt di **creazione del database mirror** .</span><span class="sxs-lookup"><span data-stu-id="637cd-129">If you are restoring a Back End that was mirrored, continue to follow the rest of the wizard until the prompt **Create Mirror Database** appears.</span></span> <span data-ttu-id="637cd-130">Selezionare il database che si desidera installare e completare il processo.</span><span class="sxs-lookup"><span data-stu-id="637cd-130">Select the database that you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="637cd-131">Seguire il resto della procedura guidata e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="637cd-131">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="637cd-132">Anziché eseguire Generatore di topologie, è possibile utilizzare il cmdlet <STRONG>Install-CsDatabase</STRONG> per creare ogni database e il cmdlet <STRONG>Install-CsMirrorDatabase</STRONG> per configurare il mirroring.</span><span class="sxs-lookup"><span data-stu-id="637cd-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="637cd-133">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="637cd-133">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

5.  <span data-ttu-id="637cd-134">Ripristinare i dati degli utenti eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="637cd-134">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="637cd-135">Copiare ExportedUserData.zip da $Backup \\ in una directory locale.</span><span class="sxs-lookup"><span data-stu-id="637cd-135">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="637cd-136">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="637cd-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    3.  <span data-ttu-id="637cd-137">Prima di ripristinare i dati degli utenti, è necessario arrestare i servizi Lync.</span><span class="sxs-lookup"><span data-stu-id="637cd-137">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="637cd-138">A tale scopo, digitare:</span><span class="sxs-lookup"><span data-stu-id="637cd-138">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    4.  <span data-ttu-id="637cd-139">Per ripristinare i dati utente, nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="637cd-139">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="637cd-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="637cd-140">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  <span data-ttu-id="637cd-141">Riavviare i servizi di Lync digitando:</span><span class="sxs-lookup"><span data-stu-id="637cd-141">Restart Lync Services by typing:</span></span>
        
            Start-CsWindowsService

6.  <span data-ttu-id="637cd-142">Se è stato distribuito Response Group in questo pool, ripristinare i dati di configurazione di Response Group.</span><span class="sxs-lookup"><span data-stu-id="637cd-142">If you deployed Response Group on this pool, restore the Response Group configuration data.</span></span> <span data-ttu-id="637cd-143">Per informazioni dettagliate, vedere [Restoring Response Group Settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="637cd-143">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

7.  <span data-ttu-id="637cd-144">Se si sta ripristinando un server back-end che includeva il database di archiviazione o di monitoraggio, ripristinare i dati di archiviazione o monitoraggio mediante uno strumento di SQL Server, ad esempio SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="637cd-144">If you are restoring a Back End Server that included Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="637cd-145">Per informazioni dettagliate, vedere [Restoring monitoring or Archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="637cd-145">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

