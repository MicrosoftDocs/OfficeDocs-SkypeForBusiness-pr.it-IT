---
title: Ripristino di un server back-end con mirroring Enterprise Edition-mirror
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 113d69d7aa39673686ff870c36a64bd1a8fe90f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a><span data-ttu-id="b8dac-102">Ripristino di un server back-end Enterprise Edition con mirroring in Lync Server 2013-mirror</span><span class="sxs-lookup"><span data-stu-id="b8dac-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8dac-103">_**Argomento Ultima modifica:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="b8dac-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="b8dac-104">Se si ha un server back-end Enterprise Edition in una configurazione con mirroring e solo lo specchio non riesce, seguire le procedure descritte in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="b8dac-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the mirror fails, follow the procedures in this section.</span></span> <span data-ttu-id="b8dac-105">Se sia il database primario che il mirror non riescono, vedere [ripristino di un server back-end Enterprise Edition in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span><span class="sxs-lookup"><span data-stu-id="b8dac-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="b8dac-106">Se solo il principale non riesce, vedere [ripristino di un server back-end Enterprise Edition con mirroring in Lync server 2013-primario](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span><span class="sxs-lookup"><span data-stu-id="b8dac-106">If only the primary fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span></span> <span data-ttu-id="b8dac-107">Se il database che ospita l'archivio di gestione centrale non riesce, vedere [ripristino del server che ospita l'archivio di gestione centrale in Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="b8dac-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="b8dac-108">Se un server membro di Enterprise Edition che non è il server back-end non riesce, vedere [ripristino di un server membro di Enterprise Edition in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="b8dac-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="b8dac-109">Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema.</span><span class="sxs-lookup"><span data-stu-id="b8dac-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="b8dac-110">È possibile usare questa immagine come punto di rollback, in caso di problemi durante il ripristino.</span><span class="sxs-lookup"><span data-stu-id="b8dac-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="b8dac-111">Potrebbe essere necessario prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare di nuovo i certificati.</span><span class="sxs-lookup"><span data-stu-id="b8dac-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a><span data-ttu-id="b8dac-112">Per ripristinare un database mirror di Enterprise Edition back end server</span><span class="sxs-lookup"><span data-stu-id="b8dac-112">To restore an Enterprise Edition Back End Server Mirror Database</span></span>

1.  <span data-ttu-id="b8dac-113">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere a un server front-end.</span><span class="sxs-lookup"><span data-stu-id="b8dac-113">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="b8dac-114">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b8dac-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b8dac-115">Disinstallare il mirroring.</span><span class="sxs-lookup"><span data-stu-id="b8dac-115">Uninstall mirroring.</span></span> <span data-ttu-id="b8dac-116">Prima di tutto, digitare il seguente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b8dac-116">First, type the following cmdlet:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="b8dac-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b8dac-117">For example:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    <span data-ttu-id="b8dac-118">Eseguire questa operazione per tutti i tipi di database nel server.</span><span class="sxs-lookup"><span data-stu-id="b8dac-118">Do this for all database types on this server.</span></span>

4.  <span data-ttu-id="b8dac-119">Creare un nuovo server pulito o con lo stesso nome di dominio completo (FQDN) (DB1.contoso.com) del computer non riuscito, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.</span><span class="sxs-lookup"><span data-stu-id="b8dac-119">Create a clean or new server that has the same fully qualified domain name (FQDN) (DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="b8dac-120">Questo server funzionerà come nuovo mirror.</span><span class="sxs-lookup"><span data-stu-id="b8dac-120">This server will function as the new mirror.</span></span>

5.  <span data-ttu-id="b8dac-121">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere al nuovo server.</span><span class="sxs-lookup"><span data-stu-id="b8dac-121">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

6.  <span data-ttu-id="b8dac-122">Installare SQL Server 2012 o SQL Server 2008 R2, mantenendo i nomi delle istanze come prima dell'errore.</span><span class="sxs-lookup"><span data-stu-id="b8dac-122">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

7.  <span data-ttu-id="b8dac-123">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere a un server front-end.</span><span class="sxs-lookup"><span data-stu-id="b8dac-123">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

8.  <span data-ttu-id="b8dac-124">Usare generatore di topologie per installare il database mirror.</span><span class="sxs-lookup"><span data-stu-id="b8dac-124">Use Topology Builder to install the mirror database.</span></span> <span data-ttu-id="b8dac-125">Eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8dac-125">Perform the following:</span></span>
    
      - <span data-ttu-id="b8dac-126">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b8dac-126">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="b8dac-127">Fare clic con il pulsante destro del mouse sul nodo Lync Server 2013, scegliere **topologia**e quindi fare clic su **Installa database**.</span><span class="sxs-lookup"><span data-stu-id="b8dac-127">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="b8dac-128">Seguire la procedura guidata **Installa database** .</span><span class="sxs-lookup"><span data-stu-id="b8dac-128">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="b8dac-129">Nella pagina **Crea database** selezionare i database che si desidera ricreare.</span><span class="sxs-lookup"><span data-stu-id="b8dac-129">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="b8dac-130">Seguire la procedura guidata fino a quando non viene visualizzata una richiesta di **creazione di database mirror** .</span><span class="sxs-lookup"><span data-stu-id="b8dac-130">Follow the wizard until a prompt of **Create Mirror Database** appears.</span></span> <span data-ttu-id="b8dac-131">Selezionare il database che si vuole installare e completare il processo.</span><span class="sxs-lookup"><span data-stu-id="b8dac-131">Select the database that you want to install and complete this process.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="b8dac-132">Invece di eseguire Generatore di topologie, puoi usare il cmdlet <STRONG>Install-CsMirrorDatabase</STRONG> per configurare il mirroring.</span><span class="sxs-lookup"><span data-stu-id="b8dac-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="b8dac-133">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b8dac-133">For details, see the Lync Server Management Shell documentation.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

