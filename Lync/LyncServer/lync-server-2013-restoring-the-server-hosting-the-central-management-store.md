---
title: "Lync Server 2013: ripristino del server che ospita l'Central Management store"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 976f486d096f7be59e2eef74eab7b03d6cc4bab0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a><span data-ttu-id="eee96-102">Ripristino del server che ospita l'archivio di gestione centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eee96-102">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eee96-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="eee96-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="eee96-104">Una distribuzione di Lync Server ha un unico Central Management store, una copia di cui viene replicata in ogni server che ha un ruolo di server Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eee96-104">A Lync Server deployment has a single Central Management store, a copy of which is replicated to each server running a Lync Server server role.</span></span> <span data-ttu-id="eee96-105">Questo argomento descrive come ripristinare un server di back-end o un server Standard Edition che ospita l'Central Management store.</span><span class="sxs-lookup"><span data-stu-id="eee96-105">This topic describes how to restore a Back End Server or Standard Edition server that hosts the Central Management store.</span></span>

<span data-ttu-id="eee96-106">Per trovare il pool in cui si trova il server di gestione centrale, aprire Generatore di topologie, fare clic su **Lync Server**e cercare nel riquadro destro in **Central Management Server**.</span><span class="sxs-lookup"><span data-stu-id="eee96-106">To find the pool where the Central Management Server is located, open Topology Builder, click **Lync Server**, and look in the right pane under **Central Management Server**.</span></span>

<span data-ttu-id="eee96-107">Se il server di back-end che ospita l'archivio di gestione centrale è in una configurazione con mirroring e il database mirror è ancora funzionante, è consigliabile eseguire un backup di questo mirror ancora funzionante e quindi effettuare un ripristino completo sia nel database principale che in quello database mirror, usando questo backup, seguendo la procedura di ripristino seguente.</span><span class="sxs-lookup"><span data-stu-id="eee96-107">If the Back End Server that hosts the Central Management store is in a mirrored setup and the mirror database is still functional, we recommend that you make a backup of this still-functioning mirror, and then perform a full restore on both the primary database and the mirror database, using this backup, by following the restoration procedure below.</span></span> <span data-ttu-id="eee96-108">Questa operazione è necessaria perché il ripristino di back-end richiede la modifica e la pubblicazione della topologia e questa operazione può essere eseguita solo se il database primario CMS ospitante è operativo.</span><span class="sxs-lookup"><span data-stu-id="eee96-108">This is necessary because Back End restore requires modifying and publishing the topology, and this can be done only if the primary database hosting CMS is operational.</span></span> <span data-ttu-id="eee96-109">Si noti inoltre che i ruoli del database primario e mirror non possono essere intercambiati se non è possibile pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="eee96-109">Also note that the primary and mirror database roles cannot be interchanged if the topology cannot be published.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eee96-110">Se un server back-end o un server Standard Edition che non ospita il Central Management store non è riuscito, vedere <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">ripristino di un server back-end Enterprise Edition in Lync server 2013</A> o <A href="lync-server-2013-restoring-a-standard-edition-server.md">ripristino di un server standard in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="eee96-110">If a Back End Server or Standard Edition server that does not host the Central Management store failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</A> or <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</A>.</span></span> <span data-ttu-id="eee96-111">Se un server back-end che ospita l'archivio di gestione centrale è in una configurazione speculare e solo lo specchio non riesce, vedere <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">ripristino di un server back-end Enterprise con mirroring in Lync server 2013-mirror</A>.</span><span class="sxs-lookup"><span data-stu-id="eee96-111">If a Back End Server that hosts the Central Management store is in a mirrored configuration and only the mirror failed, see <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</A>.</span></span> <span data-ttu-id="eee96-112">Se un altro server non è riuscito, vedere <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">ripristino di un server membro di Enterprise Edition in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="eee96-112">If any other server failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="eee96-113">Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema.</span><span class="sxs-lookup"><span data-stu-id="eee96-113">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="eee96-114">È possibile usare questa immagine come punto di rollback, in caso di problemi durante il ripristino.</span><span class="sxs-lookup"><span data-stu-id="eee96-114">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="eee96-115">Potrebbe essere necessario prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare di nuovo i certificati.</span><span class="sxs-lookup"><span data-stu-id="eee96-115">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-the-central-management-store"></a><span data-ttu-id="eee96-116">Per ripristinare il Central Management store</span><span class="sxs-lookup"><span data-stu-id="eee96-116">To restore the Central Management store</span></span>

1.  <span data-ttu-id="eee96-117">Iniziare con un nuovo server pulito o con lo stesso nome di dominio completo (FQDN) del computer non riuscito, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.</span><span class="sxs-lookup"><span data-stu-id="eee96-117">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eee96-118">Per eseguire questo passaggio, seguire le procedure di distribuzione del server dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="eee96-118">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="eee96-119">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins e del gruppo Administrators locale, accedere al server che si sta ripristinando.</span><span class="sxs-lookup"><span data-stu-id="eee96-119">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="eee96-120">Se si sta ripristinando un server Standard Edition, ripristinare l'archivio file copiando l'archivio file appropriato da $Backup nella posizione dell'archivio file nel server e quindi condividere la cartella.</span><span class="sxs-lookup"><span data-stu-id="eee96-120">If you are restoring a Standard Edition server, restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eee96-121">Il percorso e il nome file dell'archivio file ripristinato devono essere esattamente gli stessi dell'archivio di file di cui è stato eseguito il backup in modo che i componenti che usano i file possano accedervi.</span><span class="sxs-lookup"><span data-stu-id="eee96-121">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="eee96-122">Esegui una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eee96-122">Do one of the following:</span></span>
    
      - <span data-ttu-id="eee96-123">Se si sta installando un server Standard Edition, passare alla cartella di installazione o al supporto di Lync Server, quindi avviare la distribuzione guidata di Lync \\server\\in\\Setup amd64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="eee96-123">If you are installing a Standard Edition server, browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="eee96-124">Nella distribuzione guidata fare clic su **prepara primo server Standard Edition** e seguire la procedura guidata per installare Central Management store.</span><span class="sxs-lookup"><span data-stu-id="eee96-124">In the Deployment Wizard, click **Prepare first Standard Edition server** and follow the wizard to install the Central Management store.</span></span>
    
      - <span data-ttu-id="eee96-125">Se si sta installando un server back-end aziendale, installare SQL Server 2012 o SQL Server 2008 R2, mantenendo i nomi delle istanze come prima dell'errore.</span><span class="sxs-lookup"><span data-stu-id="eee96-125">If you are installing an Enterprise Back End Server, install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="eee96-126">A seconda del server che si sta ripristinando e della distribuzione, il server può includere più database collocati o separati.</span><span class="sxs-lookup"><span data-stu-id="eee96-126">Depending on the server that you are restoring and on your deployment, the server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="eee96-127">Seguire la stessa procedura per installare SQL Server usato in origine per distribuire il server, incluse le autorizzazioni di SQL Server e gli accessi.</span><span class="sxs-lookup"><span data-stu-id="eee96-127">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

        
        </div>

5.  <span data-ttu-id="eee96-128">Da un server front-end avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="eee96-128">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

6.  <span data-ttu-id="eee96-129">Ricreare l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="eee96-129">Re-create the Central Management store.</span></span> <span data-ttu-id="eee96-130">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="eee96-130">At the command line, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="eee96-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="eee96-131">For example:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  <span data-ttu-id="eee96-132">Impostare il punto di controllo Active Directory Domain Services per l'Central Management store.</span><span class="sxs-lookup"><span data-stu-id="eee96-132">Set the Active Directory Domain Services control point for the Central Management store.</span></span> <span data-ttu-id="eee96-133">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="eee96-133">At the command line, type:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="eee96-134">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="eee96-134">For example:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eee96-135">Se si perde il punto di connessione, è possibile rieseguire questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eee96-135">If you lose the connection point, you can rerun this cmdlet.</span></span>

    
    </div>

8.  <span data-ttu-id="eee96-136">Importare i dati di Central Management store da $Backup.</span><span class="sxs-lookup"><span data-stu-id="eee96-136">Import the Central Management store data from $Backup.</span></span> <span data-ttu-id="eee96-137">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="eee96-137">At the command line, type:</span></span>
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    <span data-ttu-id="eee96-138">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="eee96-138">For example:</span></span>
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  <span data-ttu-id="eee96-139">Abilitare le modifiche appena apportate.</span><span class="sxs-lookup"><span data-stu-id="eee96-139">Enable the changes you have just made.</span></span> <span data-ttu-id="eee96-140">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="eee96-140">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eee96-141">Dopo aver abilitato la topologia, è possibile trovare il documento di topologia nel database.</span><span class="sxs-lookup"><span data-stu-id="eee96-141">After you enable the topology, you can find the topology document in the database.</span></span>

    
    </div>

10. <span data-ttu-id="eee96-142">Se si esegue il ripristino di un server back-end Enterprise Edition che ospitava anche il CMS o se è necessario ricreare uno specchio del CMS, seguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="eee96-142">If you are restoring an Enterprise Edition Back End Server that also hosted the CMS, or if you need to re-create a mirror of the CMS, then follow this step.</span></span> <span data-ttu-id="eee96-143">In caso contrario, passare al passaggio 11.</span><span class="sxs-lookup"><span data-stu-id="eee96-143">Otherwise, skip to step 11.</span></span>
    
    <span data-ttu-id="eee96-144">Installare i database autonomi eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eee96-144">Install the stand-alone databases by doing the following:</span></span>
    
    1.  <span data-ttu-id="eee96-145">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="eee96-145">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="eee96-146">Fare clic su **Scarica topologia dalla distribuzione esistente**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="eee96-146">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="eee96-147">Selezionare la topologia e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="eee96-147">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="eee96-148">Fare clic su **Sì** per confermare la selezione.</span><span class="sxs-lookup"><span data-stu-id="eee96-148">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="eee96-149">Fare clic con il pulsante destro del mouse sul nodo **Lync Server 2013** e quindi scegliere **Installa database**.</span><span class="sxs-lookup"><span data-stu-id="eee96-149">Right-click the **Lync Server 2013** node, and then click **Install Database**.</span></span>
    
    5.  <span data-ttu-id="eee96-150">Seguire la procedura guidata **Installa database** .</span><span class="sxs-lookup"><span data-stu-id="eee96-150">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="eee96-151">Se si esegue il ripristino di un database diverso da Central Management store su questo server, nella pagina **Crea database** selezionare i database che si desidera ricreare.</span><span class="sxs-lookup"><span data-stu-id="eee96-151">If you are restoring a database other than the Central Management store on this server, on the **Create databases** page, select the databases you want to recreate.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="eee96-152">Nella pagina <STRONG>Crea database</STRONG> sono visualizzati solo database autonomi.</span><span class="sxs-lookup"><span data-stu-id="eee96-152">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span> <span data-ttu-id="eee96-153">I database collocati vengono creati quando si esegue la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eee96-153">Collocated databases are created when you run the Lync Server Deployment Wizard.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="eee96-154">Se si sta ripristinando un server back-end con mirroring, continuare a seguire il resto della procedura guidata finché non viene visualizzato un messaggio di creazione di database mirror.</span><span class="sxs-lookup"><span data-stu-id="eee96-154">If you are restoring a mirrored Back End Server, continue to follow the rest of the wizard until you come to a prompt of Create Mirror Database.</span></span> <span data-ttu-id="eee96-155">Selezionare il database che si vuole installare e completare il processo.</span><span class="sxs-lookup"><span data-stu-id="eee96-155">Select the database you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="eee96-156">Seguire il resto della procedura guidata e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="eee96-156">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="eee96-157">Invece di eseguire Generatore di topologie, è possibile usare il cmdlet <STRONG>Install-CsDatabase</STRONG> per creare ogni database e il cmdlet <STRONG>Install-CsMirrorDatabase</STRONG> per configurare il mirroring.</span><span class="sxs-lookup"><span data-stu-id="eee96-157">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="eee96-158">Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span><span class="sxs-lookup"><span data-stu-id="eee96-158">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span></span>

    
    </div>

11. <span data-ttu-id="eee96-159">Se si sta ripristinando un server Standard Edition, passare alla cartella di installazione o al supporto di Lync Server e avviare la distribuzione guidata di Lync \\server\\in\\Setup amd64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="eee96-159">If you are restoring a Standard Edition server, browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="eee96-160">Usare la distribuzione guidata di Lync Server per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eee96-160">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="eee96-161">Eseguire il **passaggio 1: installare l'archivio configurazione locale** per installare i file di configurazione locali.</span><span class="sxs-lookup"><span data-stu-id="eee96-161">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="eee96-162">Eseguire il **passaggio 2: configurare o rimuovere i componenti di Lync Server** per installare i ruoli di Lync Server Server.</span><span class="sxs-lookup"><span data-stu-id="eee96-162">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="eee96-163">Eseguire il **passaggio 3: richiedere, installare o assegnare certificati** per assegnare i certificati.</span><span class="sxs-lookup"><span data-stu-id="eee96-163">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="eee96-164">Eseguire il **passaggio 4: avviare i servizi** per avviare i servizi nel server.</span><span class="sxs-lookup"><span data-stu-id="eee96-164">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="eee96-165">Per informazioni dettagliate sull'eseguire la distribuzione guidata, vedere la documentazione relativa alla distribuzione per il ruolo del server che si sta ripristinando.</span><span class="sxs-lookup"><span data-stu-id="eee96-165">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

12. <span data-ttu-id="eee96-166">Ripristinare i dati degli utenti eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eee96-166">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="eee96-167">Copiare ExportedUserData. zip da $Backup\\ a una directory locale.</span><span class="sxs-lookup"><span data-stu-id="eee96-167">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="eee96-168">Prima di ripristinare i dati utente, è necessario arrestare i servizi Lync.</span><span class="sxs-lookup"><span data-stu-id="eee96-168">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="eee96-169">A tale scopo, digitare:</span><span class="sxs-lookup"><span data-stu-id="eee96-169">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="eee96-170">Per ripristinare i dati utente, nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="eee96-170">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="eee96-171">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="eee96-171">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="eee96-172">Riavviare i servizi Lync digitando:</span><span class="sxs-lookup"><span data-stu-id="eee96-172">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

13. <span data-ttu-id="eee96-173">Ripristinare i dati delle informazioni sulla posizione in Central Management store.</span><span class="sxs-lookup"><span data-stu-id="eee96-173">Restore Location Information data to the Central Management store.</span></span> <span data-ttu-id="eee96-174">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="eee96-174">At the command line, type:</span></span>
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    <span data-ttu-id="eee96-175">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="eee96-175">For example:</span></span>
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. <span data-ttu-id="eee96-176">Se il gruppo di risposte è stato distribuito in questo pool o in un server Standard Edition, ripristinare i dati di configurazione di Response Group.</span><span class="sxs-lookup"><span data-stu-id="eee96-176">If you deployed Response Group on this pool or Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="eee96-177">Per informazioni dettagliate, vedere [ripristino delle impostazioni dei gruppi di risposte in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="eee96-177">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

15. <span data-ttu-id="eee96-178">Se si ripristina un server back-end che include l'archiviazione o il monitoraggio dei database, ripristinare i dati di archiviazione o monitoraggio tramite uno strumento di gestione di SQL Server, ad esempio SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="eee96-178">If you are restoring a Back End Server that includes Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server management tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="eee96-179">Per informazioni dettagliate, vedere [ripristinare il monitoraggio o l'archiviazione dei dati in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="eee96-179">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

