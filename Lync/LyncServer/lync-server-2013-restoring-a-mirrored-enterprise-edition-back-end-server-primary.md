---
title: Ripristino di un server back-end Enterprise con mirroring-Primary
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbf0c8562ed4180fb14bf0bda74a03dd4ee8f746
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a><span data-ttu-id="cd837-102">Ripristino di un server back-end Enterprise Edition con mirroring in Lync Server 2013-primario</span><span class="sxs-lookup"><span data-stu-id="cd837-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd837-103">_**Argomento Ultima modifica:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="cd837-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="cd837-104">Se si ha un server back-end Enterprise Edition in una configurazione con mirroring e solo il database principale non riesce, seguire le procedure descritte in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="cd837-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the primary database fails, follow the procedures in this section.</span></span> <span data-ttu-id="cd837-105">Se sia il database primario che il mirror non riescono, vedere [ripristino di un server back-end Enterprise Edition in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span><span class="sxs-lookup"><span data-stu-id="cd837-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="cd837-106">Se solo lo specchio non riesce, vedere [ripristino di un server back-end Enterprise Edition con mirroring in Lync server 2013-mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span><span class="sxs-lookup"><span data-stu-id="cd837-106">If only the mirror fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span></span> <span data-ttu-id="cd837-107">Se il database che ospita l'archivio di gestione centrale non riesce, vedere [ripristino del server che ospita l'archivio di gestione centrale in Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="cd837-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="cd837-108">Se un server membro di Enterprise Edition che non è il server back-end non riesce, vedere [ripristino di un server membro di Enterprise Edition in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="cd837-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="cd837-109">Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema.</span><span class="sxs-lookup"><span data-stu-id="cd837-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="cd837-110">È possibile usare questa immagine come punto di rollback, in caso di problemi durante il ripristino.</span><span class="sxs-lookup"><span data-stu-id="cd837-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="cd837-111">Potrebbe essere necessario prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare di nuovo i certificati.</span><span class="sxs-lookup"><span data-stu-id="cd837-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<span data-ttu-id="cd837-112">In questo argomento, il database primario di esempio avrà un nome di dominio completo (FQDN) di BE1.contoso.com e il database mirror avrà un FQDN di BE2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cd837-112">In this topic, the example primary database will have a fully qualified domain name (FQDN) of BE1.contoso.com, and the mirror database will have an FQDN of BE2.contoso.com.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a><span data-ttu-id="cd837-113">Per ripristinare un database primario del server back-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="cd837-113">To restore an Enterprise Edition Back End Server Primary Database</span></span>

1.  <span data-ttu-id="cd837-114">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere a un server front-end.</span><span class="sxs-lookup"><span data-stu-id="cd837-114">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="cd837-115">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cd837-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cd837-116">Forzare il failover di tutti i database configurati allo specchio.</span><span class="sxs-lookup"><span data-stu-id="cd837-116">Force all of the configured databases to fail over to the Mirror.</span></span> <span data-ttu-id="cd837-117">Per ogni tipo di database configurato in questo server, digitare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="cd837-117">For each of the database types that you have configured on this server, type the following cmdlet:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    <span data-ttu-id="cd837-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cd837-118">For example:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="cd837-119">Se il database back-end è stato configurato per usare il mirroring sincronizzato con un testimone, il failover è automatico.</span><span class="sxs-lookup"><span data-stu-id="cd837-119">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span>

    
    </div>

4.  <span data-ttu-id="cd837-120">Dopo aver completato il failover, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd837-120">After completing failover, perform the following:</span></span>
    
      - <span data-ttu-id="cd837-121">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cd837-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="cd837-122">Disabilitare il mirroring sul server back-end: fare clic con il pulsante destro del mouse sul pool in pool **Enterprise Edition front-end** e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cd837-122">Disable mirroring on the Back End Server: Right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="cd837-123">Nella scheda **generale** , in **associazioni**, deselezionare la casella di controllo **Abilita mirroring di SQL Server Store** .</span><span class="sxs-lookup"><span data-stu-id="cd837-123">On the **General** tab, under **Associations**, clear the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="cd837-124">Eseguire questa operazione per l'archiviazione e il monitoraggio, se necessario.</span><span class="sxs-lookup"><span data-stu-id="cd837-124">Do this for Archiving and Monitoring as necessary.</span></span> <span data-ttu-id="cd837-125">Quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd837-125">Then click **OK**.</span></span>
    
      - <span data-ttu-id="cd837-126">Fare clic con il pulsante destro del mouse sul nodo Lync Server 2013, scegliere **topologia**e quindi fare clic su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="cd837-126">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="cd837-127">Selezionare il backend ancora funzionante (BE2.contoso.com) come nuovo archivio SQL.</span><span class="sxs-lookup"><span data-stu-id="cd837-127">Select the still functioning backend (BE2.contoso.com) to be the new SQL store.</span></span> <span data-ttu-id="cd837-128">A questo scopo, fai clic con il pulsante destro del mouse sul pool in pool di **front end di Enterprise Edition** e scegli **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cd837-128">To do this, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="cd837-129">Nella scheda **generale** , in **associazioni**, digitare il nome di dominio completo del backend funzionante nel campo **Archivio di SQL Server** (in questo esempio, be2.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cd837-129">On the **General** tab, under **Associations**, type the FQDN of the functioning backend in the **SQL Server store** field (in our example, BE2.contoso.com).</span></span>
    
      - <span data-ttu-id="cd837-130">Fare clic con il pulsante destro del mouse sul nodo Lync Server 2013, scegliere **topologia**e quindi fare clic su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="cd837-130">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="cd837-131">Riavviare i servizi in modo che ogni server possa leggere la nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="cd837-131">Restart services so that each server can read the new topology.</span></span> <span data-ttu-id="cd837-132">Da un Lync Server Management Shell eseguire i cmdlet seguenti in ogni server front-end che appartiene a questo pool:</span><span class="sxs-lookup"><span data-stu-id="cd837-132">From a Lync Server Management Shell, run the following cmdlets on each Front End Server that belongs to this pool:</span></span>
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  <span data-ttu-id="cd837-133">Disinstallare il mirroring.</span><span class="sxs-lookup"><span data-stu-id="cd837-133">Uninstall mirroring.</span></span> <span data-ttu-id="cd837-134">Da un Lync Server Management Shell eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="cd837-134">From a Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="cd837-135">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cd837-135">For example:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    <span data-ttu-id="cd837-136">Eseguire questa operazione per tutti i tipi di database nel server.</span><span class="sxs-lookup"><span data-stu-id="cd837-136">Do this for all database types on this server.</span></span>

6.  <span data-ttu-id="cd837-137">Creare un server pulito o nuovo con lo stesso nome di dominio completo (in questo esempio, DB1.contoso.com) come computer non riuscito, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.</span><span class="sxs-lookup"><span data-stu-id="cd837-137">Create a clean or new server that has the same FQDN (in this example, DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="cd837-138">Questo server funzionerà come nuovo mirror.</span><span class="sxs-lookup"><span data-stu-id="cd837-138">This server will function as the new mirror.</span></span>

7.  <span data-ttu-id="cd837-139">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere al nuovo server.</span><span class="sxs-lookup"><span data-stu-id="cd837-139">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

8.  <span data-ttu-id="cd837-140">Installare SQL Server 2012 o SQL Server 2008 R2, mantenendo i nomi delle istanze come prima dell'errore.</span><span class="sxs-lookup"><span data-stu-id="cd837-140">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

9.  <span data-ttu-id="cd837-141">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere a un server front-end.</span><span class="sxs-lookup"><span data-stu-id="cd837-141">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

10. <span data-ttu-id="cd837-142">Usare generatore di topologie per installare mirror DB.</span><span class="sxs-lookup"><span data-stu-id="cd837-142">Use Topology Builder to install mirror DB.</span></span> <span data-ttu-id="cd837-143">Eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="cd837-143">Perform the following steps:</span></span>
    
      - <span data-ttu-id="cd837-144">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cd837-144">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="cd837-145">Abilitare il mirroring sul server back-end.</span><span class="sxs-lookup"><span data-stu-id="cd837-145">Enable mirroring on the Back End Server.</span></span> <span data-ttu-id="cd837-146">A questo scopo, fai clic con il pulsante destro del mouse sul pool in pool di **front end di Enterprise Edition** e scegli **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cd837-146">To do so, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="cd837-147">Nella scheda **generale** , in **associazioni**, selezionare la casella di controllo **Abilita mirroring di SQL Server Store** .</span><span class="sxs-lookup"><span data-stu-id="cd837-147">On the **General** tab, under **Associations**, select the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="cd837-148">Eseguire questa operazione anche per l'archiviazione e il monitoraggio, se necessario.</span><span class="sxs-lookup"><span data-stu-id="cd837-148">Also do this for Archiving and Monitoring, if necessary.</span></span>
        
        <span data-ttu-id="cd837-149">Nel campo archivio di **SQL Server mirroring** Digitare quindi il nome di dominio completo del nuovo server (n questo esempio, BE1.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cd837-149">Then, in the **Mirroring SQL Server store** field, type the FQDN of the new server (n this example, BE1.contoso.com).</span></span> <span data-ttu-id="cd837-150">Quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd837-150">Then click **OK**.</span></span>
    
      - <span data-ttu-id="cd837-151">Fare clic con il pulsante destro del mouse sul nodo Lync Server 2013, scegliere **topologia**e quindi fare clic su **Installa database**.</span><span class="sxs-lookup"><span data-stu-id="cd837-151">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="cd837-152">Seguire la procedura guidata **Installa database** .</span><span class="sxs-lookup"><span data-stu-id="cd837-152">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="cd837-153">Nella pagina **Crea database** selezionare i database che si desidera ricreare.</span><span class="sxs-lookup"><span data-stu-id="cd837-153">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="cd837-154">Seguire la procedura guidata fino a raggiungere il prompt, **creare un database mirror**.</span><span class="sxs-lookup"><span data-stu-id="cd837-154">Follow the wizard until you come to the prompt, **Create Mirror Database**.</span></span> <span data-ttu-id="cd837-155">Selezionare il database che si vuole installare e completare il processo.</span><span class="sxs-lookup"><span data-stu-id="cd837-155">Select the database that you want to install, and complete this process.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

