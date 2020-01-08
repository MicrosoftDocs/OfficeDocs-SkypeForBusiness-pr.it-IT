---
title: 'Lync Server 2013: ripristino di un server Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 101cf0cb2fc4073e2b79aa008187465f84d2d439
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="f293e-102">Ripristino di un server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f293e-102">Restoring a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f293e-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f293e-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f293e-104">Se un server Standard Edition che non ospita il Central Management store non riesce, seguire le procedure descritte in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="f293e-104">If a Standard Edition server that does not host the Central Management store fails, follow the procedures in this section.</span></span> <span data-ttu-id="f293e-105">Se l'archivio di gestione centrale non riesce, vedere [ripristino del server che ospita l'archivio di gestione centrale in Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="f293e-105">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="f293e-106">Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema.</span><span class="sxs-lookup"><span data-stu-id="f293e-106">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="f293e-107">È possibile usare questa immagine come punto di rollback, in caso di problemi durante il ripristino.</span><span class="sxs-lookup"><span data-stu-id="f293e-107">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="f293e-108">Potrebbe essere necessario prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare di nuovo i certificati.</span><span class="sxs-lookup"><span data-stu-id="f293e-108">You might want to take the image copy after you install the operating system and SQL Server, and restore or re-enroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a><span data-ttu-id="f293e-109">Per ripristinare un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f293e-109">To restore a Standard Edition server</span></span>

1.  <span data-ttu-id="f293e-110">Iniziare con un nuovo server pulito o con lo stesso nome di dominio completo (FQDN) del computer non riuscito, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.</span><span class="sxs-lookup"><span data-stu-id="f293e-110">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f293e-111">Per eseguire questo passaggio, seguire le procedure di distribuzione del server dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f293e-111">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="f293e-112">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins e del gruppo Administrators locale, accedere al server che si sta ripristinando.</span><span class="sxs-lookup"><span data-stu-id="f293e-112">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="f293e-113">Ripristinare l'archivio file copiando l'archivio di file appropriato da $Backup nella posizione dell'archivio di file nel server e condividere la cartella.</span><span class="sxs-lookup"><span data-stu-id="f293e-113">Restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server and share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f293e-114">Il percorso e il nome file dell'archivio file ripristinato devono essere esattamente gli stessi dell'archivio di file di cui è stato eseguito il backup in modo che i componenti che usano i file possano accedervi.</span><span class="sxs-lookup"><span data-stu-id="f293e-114">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="f293e-115">Eseguire Generatore di topologie:</span><span class="sxs-lookup"><span data-stu-id="f293e-115">Run Topology Builder:</span></span>
    
    1.  <span data-ttu-id="f293e-116">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f293e-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="f293e-117">Fare clic su **Scarica topologia dalla distribuzione esistente**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f293e-117">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="f293e-118">Selezionare la topologia e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f293e-118">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="f293e-119">Fare clic su **Sì** per confermare la selezione.</span><span class="sxs-lookup"><span data-stu-id="f293e-119">Click **Yes** to confirm your selection.</span></span>

5.  <span data-ttu-id="f293e-120">Passare alla cartella di installazione o al supporto di Lync Server, quindi avviare la distribuzione guidata di Lync Server \\in\\Setup\\amd64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="f293e-120">Browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="f293e-121">Usare la distribuzione guidata di Lync Server per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f293e-121">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="f293e-122">Eseguire il **passaggio 1: installare l'archivio configurazione locale** per installare i file di configurazione locali.</span><span class="sxs-lookup"><span data-stu-id="f293e-122">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="f293e-123">Eseguire il **passaggio 2: configurare o rimuovere i componenti di Lync Server** per installare i ruoli di Lync Server Server.</span><span class="sxs-lookup"><span data-stu-id="f293e-123">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="f293e-124">Eseguire il **passaggio 3: richiedere, installare o assegnare certificati** per assegnare i certificati.</span><span class="sxs-lookup"><span data-stu-id="f293e-124">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="f293e-125">Eseguire il **passaggio 4: avviare i servizi** per avviare i servizi nel server.</span><span class="sxs-lookup"><span data-stu-id="f293e-125">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="f293e-126">Per informazioni dettagliate sull'eseguire la distribuzione guidata, vedere la documentazione relativa alla distribuzione per il ruolo del server che si sta ripristinando.</span><span class="sxs-lookup"><span data-stu-id="f293e-126">For details about running the Deployment Wizard, see the Deployment documentation for the server role you are restoring.</span></span>

6.  <span data-ttu-id="f293e-127">Ripristinare i dati degli utenti eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f293e-127">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="f293e-128">Copiare ExportedUserData. zip da $Backup\\ a una directory locale.</span><span class="sxs-lookup"><span data-stu-id="f293e-128">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="f293e-129">Prima di ripristinare i dati utente, è necessario arrestare i servizi Lync.</span><span class="sxs-lookup"><span data-stu-id="f293e-129">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="f293e-130">A tale scopo, digitare:</span><span class="sxs-lookup"><span data-stu-id="f293e-130">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="f293e-131">Per ripristinare i dati utente, nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="f293e-131">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="f293e-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f293e-132">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="f293e-133">Riavviare i servizi Lync digitando:</span><span class="sxs-lookup"><span data-stu-id="f293e-133">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

7.  <span data-ttu-id="f293e-134">Se il gruppo di risposte è stato distribuito in questo server Standard Edition, ripristinare i dati di configurazione di Response Group.</span><span class="sxs-lookup"><span data-stu-id="f293e-134">If you deployed Response Group on this Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="f293e-135">Per informazioni dettagliate, vedere [ripristino delle impostazioni dei gruppi di risposte in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f293e-135">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

8.  <span data-ttu-id="f293e-136">Se è stata distribuita la chat persistente in questo server Standard Edition, ripristinare il database della chat persistente (MGC. MDF).</span><span class="sxs-lookup"><span data-stu-id="f293e-136">If you deployed Persistent Chat on this Standard Edition server, restore the Persistent Chat database (mgc.mdf).</span></span>
    
    <span data-ttu-id="f293e-137">Se è stato usato backup di SQL Server per eseguire il backup del database della chat persistente, usare le procedure di ripristino di SQL Server per ripristinarlo.</span><span class="sxs-lookup"><span data-stu-id="f293e-137">If you used SQL Server Backup to back up the Persistent Chat database, use SQL Server restore procedures to restore it.</span></span>
    
    <span data-ttu-id="f293e-138">Se è stato usato il cmdlet Export-CsPersistentChatData per eseguire il backup, usare Import-CsPersistentChatData per ripristinarlo.</span><span class="sxs-lookup"><span data-stu-id="f293e-138">If you used the Export-CsPersistentChatData cmdlet to back it up, use the Import-CsPersistentChatData to restore it.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

