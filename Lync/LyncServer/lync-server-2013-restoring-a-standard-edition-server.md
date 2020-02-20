---
title: 'Lync Server 2013: ripristino di un server Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bffde0a5b6047aeb2eabe38ee10c6b313ff1f01
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="fbe48-102">Ripristino di un server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbe48-102">Restoring a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbe48-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="fbe48-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="fbe48-104">Se si verifica un errore in un server Standard Edition che non ospita l'archivio di gestione centrale, seguire le procedure illustrate in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="fbe48-104">If a Standard Edition server that does not host the Central Management store fails, follow the procedures in this section.</span></span> <span data-ttu-id="fbe48-105">Se l'archivio di gestione centrale ha esito negativo, vedere [ripristino del server che ospita l'archivio di gestione centrale in Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="fbe48-105">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="fbe48-106">Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema.</span><span class="sxs-lookup"><span data-stu-id="fbe48-106">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="fbe48-107">È possibile utilizzare questa immagine come punto di rollback, in caso di problemi durante il ripristino.</span><span class="sxs-lookup"><span data-stu-id="fbe48-107">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="fbe48-108">È possibile acquisire la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare di nuovo i certificati.</span><span class="sxs-lookup"><span data-stu-id="fbe48-108">You might want to take the image copy after you install the operating system and SQL Server, and restore or re-enroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a><span data-ttu-id="fbe48-109">Per ripristinare un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="fbe48-109">To restore a Standard Edition server</span></span>

1.  <span data-ttu-id="fbe48-110">Iniziare con un server pulito o nuovo che abbia lo stesso nome di dominio completo (FQDN) del computer in cui si è verificato l'errore, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.</span><span class="sxs-lookup"><span data-stu-id="fbe48-110">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fbe48-111">Seguire le procedure di distribuzione dei server dell'organizzazione per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="fbe48-111">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="fbe48-112">Da un account utente membro del gruppo RTCUniversalServerAdmins e del gruppo Administrators locale, accedere al server che si sta ripristinando.</span><span class="sxs-lookup"><span data-stu-id="fbe48-112">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="fbe48-113">Ripristinare l'archivio file copiando l'archivio file appropriato da $Backup al percorso dell'archivio file nel server e condividere la cartella.</span><span class="sxs-lookup"><span data-stu-id="fbe48-113">Restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server and share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fbe48-114">Il percorso e il nome del file dell'archivio file ripristinato devono essere identici a quelli dell'archivio file di cui è stato eseguito il backup in modo che i componenti che utilizzano i file possano accedervi.</span><span class="sxs-lookup"><span data-stu-id="fbe48-114">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="fbe48-115">Eseguire Generatore di topologie:</span><span class="sxs-lookup"><span data-stu-id="fbe48-115">Run Topology Builder:</span></span>
    
    1.  <span data-ttu-id="fbe48-116">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="fbe48-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="fbe48-117">Fare clic su **Scarica topologia dalla distribuzione esistente** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fbe48-117">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="fbe48-p103">Selezionare la topologia e quindi fare clic su **Salva**. Fare clic su **Sì** per confermare la selezione.</span><span class="sxs-lookup"><span data-stu-id="fbe48-p103">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>

5.  <span data-ttu-id="fbe48-120">Passare alla cartella o al supporto di installazione di Lync Server e quindi avviare la distribuzione guidata di Lync Server \\in\\Setup\\amd64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="fbe48-120">Browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="fbe48-121">Utilizzare la distribuzione guidata di Lync Server per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbe48-121">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="fbe48-122">Eseguire **Passaggio 1: Installazione dell'archivio di configurazione locale** per installare i file della configurazione locale.</span><span class="sxs-lookup"><span data-stu-id="fbe48-122">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="fbe48-123">Eseguire il **passaggio 2: installazione o rimozione dei componenti di Lync Server** per installare i ruoli del server Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fbe48-123">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="fbe48-124">Eseguire **Passaggio 3: Richiesta, installazione o assegnazione dei certificati** per assegnare i certificati.</span><span class="sxs-lookup"><span data-stu-id="fbe48-124">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="fbe48-125">Eseguire **Passaggio 4: Avvio servizi** per avviare i servizi nel server.</span><span class="sxs-lookup"><span data-stu-id="fbe48-125">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="fbe48-126">Per informazioni dettagliate sull'esecuzione della Distribuzione guidata, vedere nella documentazione relativa alla distribuzione le informazioni sul ruolo del server che si desidera ripristinare.</span><span class="sxs-lookup"><span data-stu-id="fbe48-126">For details about running the Deployment Wizard, see the Deployment documentation for the server role you are restoring.</span></span>

6.  <span data-ttu-id="fbe48-127">Ripristinare i dati utente eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbe48-127">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="fbe48-128">Copiare ExportedUserData. zip da $Backup\\ in una directory locale.</span><span class="sxs-lookup"><span data-stu-id="fbe48-128">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="fbe48-129">Prima di ripristinare i dati degli utenti, è necessario arrestare i servizi Lync.</span><span class="sxs-lookup"><span data-stu-id="fbe48-129">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="fbe48-130">A tale scopo, digitare:</span><span class="sxs-lookup"><span data-stu-id="fbe48-130">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="fbe48-131">Per ripristinare i dati utente, nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="fbe48-131">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="fbe48-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fbe48-132">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="fbe48-133">Riavviare i servizi di Lync digitando:</span><span class="sxs-lookup"><span data-stu-id="fbe48-133">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

7.  <span data-ttu-id="fbe48-134">Se è stato distribuito Response Group su questo server Standard Edition, ripristinare i dati di configurazione di Response Group.</span><span class="sxs-lookup"><span data-stu-id="fbe48-134">If you deployed Response Group on this Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="fbe48-135">Per informazioni dettagliate, vedere [Restoring Response Group Settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="fbe48-135">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

8.  <span data-ttu-id="fbe48-136">Se è stata distribuita la chat persistente in questo server Standard Edition, ripristinare il database di Persistent Chat (MGC. MDF).</span><span class="sxs-lookup"><span data-stu-id="fbe48-136">If you deployed Persistent Chat on this Standard Edition server, restore the Persistent Chat database (mgc.mdf).</span></span>
    
    <span data-ttu-id="fbe48-137">Se è stato utilizzato SQL Server backup per eseguire il backup del database di chat persistente, utilizzare le procedure di ripristino di SQL Server per ripristinarlo.</span><span class="sxs-lookup"><span data-stu-id="fbe48-137">If you used SQL Server Backup to back up the Persistent Chat database, use SQL Server restore procedures to restore it.</span></span>
    
    <span data-ttu-id="fbe48-138">Se è stato utilizzato il cmdlet Export-CsPersistentChatData per eseguirne il backup, utilizzare Import-CsPersistentChatData per ripristinarlo.</span><span class="sxs-lookup"><span data-stu-id="fbe48-138">If you used the Export-CsPersistentChatData cmdlet to back it up, use the Import-CsPersistentChatData to restore it.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

