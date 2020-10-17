---
title: 'Lync Server 2013: ripristino di un server Standard Edition'
description: 'Lync Server 2013: ripristino di un server Standard Edition.'
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
ms.openlocfilehash: 1d2cd6976324492e0539c47999f78434e1a82706
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542392"
---
# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="659e2-103">Ripristino di un server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="659e2-103">Restoring a Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="659e2-104">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="659e2-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="659e2-105">Se si verifica un errore in un server Standard Edition che non ospita l'archivio di gestione centrale, seguire le procedure illustrate in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="659e2-105">If a Standard Edition server that does not host the Central Management store fails, follow the procedures in this section.</span></span> <span data-ttu-id="659e2-106">Se l'archivio di gestione centrale ha esito negativo, vedere [ripristino del server che ospita l'archivio di gestione centrale in Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="659e2-106">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="659e2-107">Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema.</span><span class="sxs-lookup"><span data-stu-id="659e2-107">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="659e2-108">È possibile utilizzare questa immagine come punto di rollback, in caso di problemi durante il ripristino.</span><span class="sxs-lookup"><span data-stu-id="659e2-108">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="659e2-109">È possibile acquisire la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare di nuovo i certificati.</span><span class="sxs-lookup"><span data-stu-id="659e2-109">You might want to take the image copy after you install the operating system and SQL Server, and restore or re-enroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a><span data-ttu-id="659e2-110">Per ripristinare un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="659e2-110">To restore a Standard Edition server</span></span>

1.  <span data-ttu-id="659e2-111">Iniziare con un server pulito o nuovo che abbia lo stesso nome di dominio completo (FQDN) del computer in cui si è verificato l'errore, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.</span><span class="sxs-lookup"><span data-stu-id="659e2-111">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="659e2-112">Seguire le procedure di distribuzione dei server dell'organizzazione per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="659e2-112">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="659e2-113">Da un account utente membro del gruppo RTCUniversalServerAdmins e del gruppo Administrators locale, accedere al server che si sta ripristinando.</span><span class="sxs-lookup"><span data-stu-id="659e2-113">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="659e2-114">Ripristinare l'archivio file copiando l'archivio file appropriato da $Backup al percorso dell'archivio file nel server e condividere la cartella.</span><span class="sxs-lookup"><span data-stu-id="659e2-114">Restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server and share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="659e2-115">Il percorso e il nome del file dell'archivio file ripristinato devono essere identici a quelli dell'archivio file di cui è stato eseguito il backup in modo che i componenti che utilizzano i file possano accedervi.</span><span class="sxs-lookup"><span data-stu-id="659e2-115">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="659e2-116">Eseguire Generatore di topologie:</span><span class="sxs-lookup"><span data-stu-id="659e2-116">Run Topology Builder:</span></span>
    
    1.  <span data-ttu-id="659e2-117">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="659e2-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="659e2-118">Fare clic su **Scarica topologia dalla distribuzione esistente** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="659e2-118">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="659e2-p103">Selezionare la topologia e quindi fare clic su **Salva**. Fare clic su **Sì** per confermare la selezione.</span><span class="sxs-lookup"><span data-stu-id="659e2-p103">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>

5.  <span data-ttu-id="659e2-121">Passare alla cartella o al supporto di installazione di Lync Server e quindi avviare la distribuzione guidata di Lync Server in \\ Setup \\ amd64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="659e2-121">Browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="659e2-122">Utilizzare la distribuzione guidata di Lync Server per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="659e2-122">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="659e2-123">Eseguire **Passaggio 1: Installazione dell'archivio di configurazione locale** per installare i file della configurazione locale.</span><span class="sxs-lookup"><span data-stu-id="659e2-123">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="659e2-124">Eseguire il **passaggio 2: installazione o rimozione dei componenti di Lync Server** per installare i ruoli del server Lync Server.</span><span class="sxs-lookup"><span data-stu-id="659e2-124">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="659e2-125">Eseguire **Passaggio 3: Richiesta, installazione o assegnazione dei certificati** per assegnare i certificati.</span><span class="sxs-lookup"><span data-stu-id="659e2-125">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="659e2-126">Eseguire **Passaggio 4: Avvio servizi** per avviare i servizi nel server.</span><span class="sxs-lookup"><span data-stu-id="659e2-126">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="659e2-127">Per informazioni dettagliate sull'esecuzione della Distribuzione guidata, vedere nella documentazione relativa alla distribuzione le informazioni sul ruolo del server che si desidera ripristinare.</span><span class="sxs-lookup"><span data-stu-id="659e2-127">For details about running the Deployment Wizard, see the Deployment documentation for the server role you are restoring.</span></span>

6.  <span data-ttu-id="659e2-128">Ripristinare i dati utente eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="659e2-128">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="659e2-129">Copiare ExportedUserData.zip da $Backup \\ in una directory locale.</span><span class="sxs-lookup"><span data-stu-id="659e2-129">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="659e2-130">Prima di ripristinare i dati degli utenti, è necessario arrestare i servizi Lync.</span><span class="sxs-lookup"><span data-stu-id="659e2-130">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="659e2-131">A tale scopo, digitare:</span><span class="sxs-lookup"><span data-stu-id="659e2-131">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="659e2-132">Per ripristinare i dati utente, nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="659e2-132">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="659e2-133">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="659e2-133">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="659e2-134">Riavviare i servizi di Lync digitando:</span><span class="sxs-lookup"><span data-stu-id="659e2-134">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

7.  <span data-ttu-id="659e2-135">Se è stato distribuito Response Group su questo server Standard Edition, ripristinare i dati di configurazione di Response Group.</span><span class="sxs-lookup"><span data-stu-id="659e2-135">If you deployed Response Group on this Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="659e2-136">Per informazioni dettagliate, vedere [Restoring Response Group Settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="659e2-136">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

8.  <span data-ttu-id="659e2-137">Se è stata distribuita la chat persistente in questo server Standard Edition, ripristinare il database di Persistent Chat (MGC. MDF).</span><span class="sxs-lookup"><span data-stu-id="659e2-137">If you deployed Persistent Chat on this Standard Edition server, restore the Persistent Chat database (mgc.mdf).</span></span>
    
    <span data-ttu-id="659e2-138">Se è stato utilizzato SQL Server backup per eseguire il backup del database di chat persistente, utilizzare le procedure di ripristino di SQL Server per ripristinarlo.</span><span class="sxs-lookup"><span data-stu-id="659e2-138">If you used SQL Server Backup to back up the Persistent Chat database, use SQL Server restore procedures to restore it.</span></span>
    
    <span data-ttu-id="659e2-139">Se è stato utilizzato il cmdlet Export-CsPersistentChatData per eseguirne il backup, utilizzare il Import-CsPersistentChatData per ripristinarlo.</span><span class="sxs-lookup"><span data-stu-id="659e2-139">If you used the Export-CsPersistentChatData cmdlet to back it up, use the Import-CsPersistentChatData to restore it.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

