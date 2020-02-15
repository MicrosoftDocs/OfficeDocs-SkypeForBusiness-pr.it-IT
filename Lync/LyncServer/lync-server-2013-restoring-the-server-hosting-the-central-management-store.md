---
title: "Lync Server 2013: ripristino del server che ospita l'archivio di gestione centrale"
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
ms.openlocfilehash: 2af346baefbbf1084debed4e7f8fd98eada4a34e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a><span data-ttu-id="5159f-102">Ripristino del server che ospita l'archivio di gestione centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5159f-102">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5159f-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5159f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5159f-104">Una distribuzione di Lync Server dispone di un unico archivio di gestione centrale, una copia di cui viene replicata in ogni server che esegue un ruolo del server Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5159f-104">A Lync Server deployment has a single Central Management store, a copy of which is replicated to each server running a Lync Server server role.</span></span> <span data-ttu-id="5159f-105">In questo argomento viene descritto come ripristinare un server back-end o uno Standard Edition che ospita l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="5159f-105">This topic describes how to restore a Back End Server or Standard Edition server that hosts the Central Management store.</span></span>

<span data-ttu-id="5159f-106">Per individuare il pool in cui si trova il server di gestione centrale, aprire Generatore di topologie, fare clic su **Lync Server**e quindi cercare nel riquadro destro in **server di gestione centrale**.</span><span class="sxs-lookup"><span data-stu-id="5159f-106">To find the pool where the Central Management Server is located, open Topology Builder, click **Lync Server**, and look in the right pane under **Central Management Server**.</span></span>

<span data-ttu-id="5159f-107">Se il server back-end che ospita l'archivio di gestione centrale si trova in una configurazione con mirroring e il database mirror è ancora funzionante, è consigliabile eseguire un backup di questo mirror ancora funzionante e quindi effettuare un ripristino completo sia sul database primario che sul database mirror, utilizzando questo backup, seguendo la procedura di ripristino seguente.</span><span class="sxs-lookup"><span data-stu-id="5159f-107">If the Back End Server that hosts the Central Management store is in a mirrored setup and the mirror database is still functional, we recommend that you make a backup of this still-functioning mirror, and then perform a full restore on both the primary database and the mirror database, using this backup, by following the restoration procedure below.</span></span> <span data-ttu-id="5159f-108">Questa operazione è necessaria perché il ripristino di back-end richiede la modifica e la pubblicazione della topologia e questo può essere eseguito solo se il database primario che ospita il CMS è operativo.</span><span class="sxs-lookup"><span data-stu-id="5159f-108">This is necessary because Back End restore requires modifying and publishing the topology, and this can be done only if the primary database hosting CMS is operational.</span></span> <span data-ttu-id="5159f-109">Si noti inoltre che i ruoli del database primario e mirror non possono essere intercambiati se non è possibile pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="5159f-109">Also note that the primary and mirror database roles cannot be interchanged if the topology cannot be published.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5159f-110">Se un server back-end o un server Standard Edition che non ospita l'archivio di gestione centrale non ha avuto esito negativo, vedere <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition back end server in Lync server 2013</A> o <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a server Standard Edition in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5159f-110">If a Back End Server or Standard Edition server that does not host the Central Management store failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</A> or <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</A>.</span></span> <span data-ttu-id="5159f-111">Se un server back-end che ospita l'archivio di gestione centrale è in una configurazione con mirroring e solo il mirror ha esito negativo, vedere <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirroring Enterprise Edition back end server in Lync server 2013-mirror</A>.</span><span class="sxs-lookup"><span data-stu-id="5159f-111">If a Back End Server that hosts the Central Management store is in a mirrored configuration and only the mirror failed, see <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</A>.</span></span> <span data-ttu-id="5159f-112">Se si è verificato un errore in un altro server, vedere <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5159f-112">If any other server failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="5159f-113">Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema.</span><span class="sxs-lookup"><span data-stu-id="5159f-113">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="5159f-114">È possibile utilizzare questa immagine come punto di rollback, in caso di problemi durante il ripristino.</span><span class="sxs-lookup"><span data-stu-id="5159f-114">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="5159f-115">È possibile che si desideri prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare nuovamente i certificati.</span><span class="sxs-lookup"><span data-stu-id="5159f-115">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-the-central-management-store"></a><span data-ttu-id="5159f-116">Per ripristinare l'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="5159f-116">To restore the Central Management store</span></span>

1.  <span data-ttu-id="5159f-117">Iniziare con un server pulito o nuovo che abbia lo stesso nome di dominio completo (FQDN) del computer in cui si è verificato l'errore, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.</span><span class="sxs-lookup"><span data-stu-id="5159f-117">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5159f-118">Seguire le procedure di distribuzione dei server dell'organizzazione per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="5159f-118">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="5159f-119">Da un account utente membro del gruppo RTCUniversalServerAdmins e del gruppo Administrators locale, accedere al server che si sta ripristinando.</span><span class="sxs-lookup"><span data-stu-id="5159f-119">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="5159f-120">Se si esegue il ripristino di un server Standard Edition, ripristinare l'archivio file copiando l'archivio file appropriato da $Backup al percorso dell'archivio file nel server e quindi condividere la cartella.</span><span class="sxs-lookup"><span data-stu-id="5159f-120">If you are restoring a Standard Edition server, restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5159f-121">Il percorso e il nome del file dell'archivio file ripristinato devono essere identici a quelli dell'archivio file di cui è stato eseguito il backup in modo che i componenti che utilizzano i file possano accedervi.</span><span class="sxs-lookup"><span data-stu-id="5159f-121">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="5159f-122">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5159f-122">Do one of the following:</span></span>
    
      - <span data-ttu-id="5159f-123">Se si sta installando un server Standard Edition, passare alla cartella o al supporto di installazione di Lync Server e quindi avviare la distribuzione guidata di Lync \\server\\in\\Setup amd64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="5159f-123">If you are installing a Standard Edition server, browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="5159f-124">Nella distribuzione guidata fare clic su **prepara primo server Standard Edition** e seguire la procedura guidata per installare l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="5159f-124">In the Deployment Wizard, click **Prepare first Standard Edition server** and follow the wizard to install the Central Management store.</span></span>
    
      - <span data-ttu-id="5159f-125">Se si sta installando un server back-end Enterprise, installare SQL Server 2012 o SQL Server 2008 R2, mantenendo i nomi delle istanze uguali a quelli precedenti all'errore.</span><span class="sxs-lookup"><span data-stu-id="5159f-125">If you are installing an Enterprise Back End Server, install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5159f-126">A seconda del server che si sta ripristinando e della distribuzione, è possibile che il server includa più database collocati o separati.</span><span class="sxs-lookup"><span data-stu-id="5159f-126">Depending on the server that you are restoring and on your deployment, the server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="5159f-127">Seguire la stessa procedura di installazione di SQL Server utilizzata in origine per la distribuzione del server, inclusi le autorizzazioni e gli account di accesso di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5159f-127">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

        
        </div>

5.  <span data-ttu-id="5159f-128">Da un front end server, avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5159f-128">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

6.  <span data-ttu-id="5159f-129">Ricreare l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="5159f-129">Re-create the Central Management store.</span></span> <span data-ttu-id="5159f-130">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5159f-130">At the command line, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="5159f-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5159f-131">For example:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  <span data-ttu-id="5159f-132">Impostare il punto di controllo dei servizi di dominio Active Directory per l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="5159f-132">Set the Active Directory Domain Services control point for the Central Management store.</span></span> <span data-ttu-id="5159f-133">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5159f-133">At the command line, type:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="5159f-134">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5159f-134">For example:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5159f-135">Se si perde il punto di connessione, è possibile eseguire di nuovo questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5159f-135">If you lose the connection point, you can rerun this cmdlet.</span></span>

    
    </div>

8.  <span data-ttu-id="5159f-136">Importare i dati dell'archivio di gestione centrale da $Backup.</span><span class="sxs-lookup"><span data-stu-id="5159f-136">Import the Central Management store data from $Backup.</span></span> <span data-ttu-id="5159f-137">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5159f-137">At the command line, type:</span></span>
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    <span data-ttu-id="5159f-138">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5159f-138">For example:</span></span>
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  <span data-ttu-id="5159f-p110">Abilitare le modifiche che sono state apportate. Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="5159f-p110">Enable the changes you have just made. At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5159f-141">Dopo aver abilitato la topologia, è possibile trovare il relativo documento nel database.</span><span class="sxs-lookup"><span data-stu-id="5159f-141">After you enable the topology, you can find the topology document in the database.</span></span>

    
    </div>

10. <span data-ttu-id="5159f-142">Se si esegue il ripristino di un server back-end Enterprise Edition che ha ospitato anche il CMS o se è necessario ricreare un mirror del CMS, seguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="5159f-142">If you are restoring an Enterprise Edition Back End Server that also hosted the CMS, or if you need to re-create a mirror of the CMS, then follow this step.</span></span> <span data-ttu-id="5159f-143">In caso contrario, passare al passaggio 11.</span><span class="sxs-lookup"><span data-stu-id="5159f-143">Otherwise, skip to step 11.</span></span>
    
    <span data-ttu-id="5159f-144">Installare i database autonomi eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5159f-144">Install the stand-alone databases by doing the following:</span></span>
    
    1.  <span data-ttu-id="5159f-145">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="5159f-145">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="5159f-146">Fare clic su **Scarica topologia dalla distribuzione esistente** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5159f-146">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="5159f-p112">Selezionare la topologia e quindi fare clic su **Salva**. Fare clic su **Sì** per confermare la selezione.</span><span class="sxs-lookup"><span data-stu-id="5159f-p112">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="5159f-149">Fare clic con il pulsante destro del mouse sul nodo **Lync Server 2013** e quindi scegliere **Installa database**.</span><span class="sxs-lookup"><span data-stu-id="5159f-149">Right-click the **Lync Server 2013** node, and then click **Install Database**.</span></span>
    
    5.  <span data-ttu-id="5159f-150">Seguire la procedura guidata di **installazione del database** .</span><span class="sxs-lookup"><span data-stu-id="5159f-150">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="5159f-151">Se si esegue il ripristino di un database diverso da quello dell'archivio di gestione centrale nel server, nella pagina **Crea database** selezionare i database che si desidera ricreare.</span><span class="sxs-lookup"><span data-stu-id="5159f-151">If you are restoring a database other than the Central Management store on this server, on the **Create databases** page, select the databases you want to recreate.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5159f-152">Nella pagina <STRONG>Creare database</STRONG> verranno visualizzati solo i database autonomi.</span><span class="sxs-lookup"><span data-stu-id="5159f-152">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span> <span data-ttu-id="5159f-153">I database collocati vengono creati durante l'esecuzione della distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5159f-153">Collocated databases are created when you run the Lync Server Deployment Wizard.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="5159f-154">Se si esegue il ripristino di un server back-end con mirroring, continuare a seguire il resto della procedura guidata fino a quando non si giunge a una richiesta di creazione di un database mirror.</span><span class="sxs-lookup"><span data-stu-id="5159f-154">If you are restoring a mirrored Back End Server, continue to follow the rest of the wizard until you come to a prompt of Create Mirror Database.</span></span> <span data-ttu-id="5159f-155">Selezionare il database che si desidera installare e completare il processo.</span><span class="sxs-lookup"><span data-stu-id="5159f-155">Select the database you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="5159f-156">Seguire il resto della procedura guidata e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="5159f-156">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="5159f-157">Anziché eseguire Generatore di topologie, è possibile utilizzare il cmdlet <STRONG>Install-CsDatabase</STRONG> per creare ogni database e il cmdlet <STRONG>Install-CsMirrorDatabase</STRONG> per configurare il mirroring.</span><span class="sxs-lookup"><span data-stu-id="5159f-157">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="5159f-158">Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span><span class="sxs-lookup"><span data-stu-id="5159f-158">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span></span>

    
    </div>

11. <span data-ttu-id="5159f-159">Se si esegue il ripristino di un server Standard Edition, passare alla cartella o al supporto di installazione di Lync Server e avviare la distribuzione guidata di \\Lync\\server\\in Setup amd64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="5159f-159">If you are restoring a Standard Edition server, browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="5159f-160">Utilizzare la distribuzione guidata di Lync Server per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5159f-160">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="5159f-161">Eseguire **Passaggio 1: Installazione dell'archivio di configurazione locale** per installare i file della configurazione locale.</span><span class="sxs-lookup"><span data-stu-id="5159f-161">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="5159f-162">Eseguire il **passaggio 2: installazione o rimozione dei componenti di Lync Server** per installare i ruoli del server Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5159f-162">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="5159f-163">Eseguire **Passaggio 3: Richiesta, installazione o assegnazione dei certificati** per assegnare i certificati.</span><span class="sxs-lookup"><span data-stu-id="5159f-163">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="5159f-164">Eseguire **Passaggio 4: Avvio servizi** per avviare i servizi nel server.</span><span class="sxs-lookup"><span data-stu-id="5159f-164">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="5159f-165">Per informazioni dettagliate sull'esecuzione della distribuzione guidata, vedere la documentazione relativa alla distribuzione per il ruolo del server che si sta ripristinando.</span><span class="sxs-lookup"><span data-stu-id="5159f-165">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

12. <span data-ttu-id="5159f-166">Ripristinare i dati utente eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5159f-166">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="5159f-167">Copiare ExportedUserData. zip da $Backup\\ in una directory locale.</span><span class="sxs-lookup"><span data-stu-id="5159f-167">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="5159f-168">Prima di ripristinare i dati degli utenti, è necessario arrestare i servizi Lync.</span><span class="sxs-lookup"><span data-stu-id="5159f-168">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="5159f-169">A tale scopo, digitare:</span><span class="sxs-lookup"><span data-stu-id="5159f-169">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="5159f-170">Per ripristinare i dati utente, nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="5159f-170">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="5159f-171">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5159f-171">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="5159f-172">Riavviare i servizi di Lync digitando:</span><span class="sxs-lookup"><span data-stu-id="5159f-172">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

13. <span data-ttu-id="5159f-173">Ripristinare i dati delle informazioni sulla posizione nell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="5159f-173">Restore Location Information data to the Central Management store.</span></span> <span data-ttu-id="5159f-174">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5159f-174">At the command line, type:</span></span>
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    <span data-ttu-id="5159f-175">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5159f-175">For example:</span></span>
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. <span data-ttu-id="5159f-176">Se è stato distribuito Response Group nel pool o nel server Standard Edition, ripristinare i dati di configurazione di Response Group.</span><span class="sxs-lookup"><span data-stu-id="5159f-176">If you deployed Response Group on this pool or Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="5159f-177">Per informazioni dettagliate, vedere [Restoring Response Group Settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="5159f-177">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

15. <span data-ttu-id="5159f-178">Se si esegue il ripristino di un server back-end che include database di archiviazione o di monitoraggio, ripristinare i dati di archiviazione o di monitoraggio utilizzando uno strumento di gestione di SQL Server, ad esempio SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="5159f-178">If you are restoring a Back End Server that includes Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server management tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="5159f-179">Per informazioni dettagliate, vedere [Restoring monitoring or Archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="5159f-179">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

