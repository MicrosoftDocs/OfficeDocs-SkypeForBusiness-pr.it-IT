---
title: Ripristino di un mirroring del server back-end Enterprise Edition con mirroring
description: Ripristino di un mirroring del server back-end Enterprise Edition con mirroring.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 011c0aaa10ffed6fef7d579dbc16993fd3341070
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543802"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a><span data-ttu-id="5228b-103">Ripristino di un server back-end Enterprise Edition con mirroring in Lync Server 2013-mirror</span><span class="sxs-lookup"><span data-stu-id="5228b-103">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5228b-104">_**Ultimo argomento modificato:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="5228b-104">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="5228b-105">Se si dispone di un server back-end Enterprise Edition in una configurazione con mirroring e solo il mirror ha esito negativo, seguire le procedure descritte in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="5228b-105">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the mirror fails, follow the procedures in this section.</span></span> <span data-ttu-id="5228b-106">Se il database primario e il mirror non riescono, vedere [Restoring an Enterprise Edition back end server in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span><span class="sxs-lookup"><span data-stu-id="5228b-106">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="5228b-107">Se solo l'operazione principale ha esito negativo, vedere [Restoring a mirroring Enterprise Edition back end server in Lync server 2013-Primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span><span class="sxs-lookup"><span data-stu-id="5228b-107">If only the primary fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span></span> <span data-ttu-id="5228b-108">Se il database che ospita l'archivio di gestione centrale ha esito negativo, vedere [ripristino del server che ospita l'archivio di gestione centrale in Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="5228b-108">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="5228b-109">Se si verifica un errore di un server membro Enterprise Edition che non è il server back-end, vedere [Restoring an Enterprise Edition member server in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="5228b-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="5228b-110">Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema.</span><span class="sxs-lookup"><span data-stu-id="5228b-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="5228b-111">È possibile utilizzare questa immagine come punto di rollback, in caso di problemi durante il ripristino.</span><span class="sxs-lookup"><span data-stu-id="5228b-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="5228b-112">È possibile che si desideri prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare nuovamente i certificati.</span><span class="sxs-lookup"><span data-stu-id="5228b-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a><span data-ttu-id="5228b-113">Per ripristinare un database mirror del server back-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="5228b-113">To restore an Enterprise Edition Back End Server Mirror Database</span></span>

1.  <span data-ttu-id="5228b-114">Accedere a un front end server da un account utente membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5228b-114">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="5228b-115">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5228b-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5228b-116">Disinstallazione del mirroring.</span><span class="sxs-lookup"><span data-stu-id="5228b-116">Uninstall mirroring.</span></span> <span data-ttu-id="5228b-117">Per prima cosa, digitare il seguente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5228b-117">First, type the following cmdlet:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="5228b-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5228b-118">For example:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    <span data-ttu-id="5228b-119">Eseguire questa operazione per tutti i tipi di database sul server.</span><span class="sxs-lookup"><span data-stu-id="5228b-119">Do this for all database types on this server.</span></span>

4.  <span data-ttu-id="5228b-120">Creare un server pulito o nuovo con lo stesso nome di dominio completo (FQDN) (DB1.contoso.com) del computer in cui si è verificato l'errore, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.</span><span class="sxs-lookup"><span data-stu-id="5228b-120">Create a clean or new server that has the same fully qualified domain name (FQDN) (DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="5228b-121">Questo server funzionerà come nuovo mirror.</span><span class="sxs-lookup"><span data-stu-id="5228b-121">This server will function as the new mirror.</span></span>

5.  <span data-ttu-id="5228b-122">Accedere al nuovo server da un account utente membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5228b-122">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

6.  <span data-ttu-id="5228b-123">Installare SQL Server 2012 o SQL Server 2008 R2, mantenendo i nomi delle istanze identici a quelli precedenti all'errore.</span><span class="sxs-lookup"><span data-stu-id="5228b-123">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

7.  <span data-ttu-id="5228b-124">Accedere a un front end server da un account utente membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5228b-124">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

8.  <span data-ttu-id="5228b-125">Utilizzare Generatore di topologie per installare il database mirror.</span><span class="sxs-lookup"><span data-stu-id="5228b-125">Use Topology Builder to install the mirror database.</span></span> <span data-ttu-id="5228b-126">Eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5228b-126">Perform the following:</span></span>
    
      - <span data-ttu-id="5228b-127">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="5228b-127">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="5228b-128">Fare clic con il pulsante destro del mouse sul nodo Lync Server 2013, scegliere **topologia**e quindi fare clic su **Installa database**.</span><span class="sxs-lookup"><span data-stu-id="5228b-128">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="5228b-129">Seguire la procedura guidata di **installazione del database** .</span><span class="sxs-lookup"><span data-stu-id="5228b-129">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="5228b-130">Nella pagina **Crea database** selezionare i database che si desidera ricreare.</span><span class="sxs-lookup"><span data-stu-id="5228b-130">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="5228b-131">Seguire la procedura guidata fino a quando non viene visualizzata una richiesta di **creazione del database mirror** .</span><span class="sxs-lookup"><span data-stu-id="5228b-131">Follow the wizard until a prompt of **Create Mirror Database** appears.</span></span> <span data-ttu-id="5228b-132">Selezionare il database che si desidera installare e completare il processo.</span><span class="sxs-lookup"><span data-stu-id="5228b-132">Select the database that you want to install and complete this process.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="5228b-133">Anziché eseguire Generatore di topologie, è possibile utilizzare il cmdlet <STRONG>Install-CsMirrorDatabase</STRONG> per configurare il mirroring.</span><span class="sxs-lookup"><span data-stu-id="5228b-133">Instead of running Topology Builder, you can use the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="5228b-134">Per informazioni dettagliate, vedere la documentazione relativa a Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5228b-134">For details, see the Lync Server Management Shell documentation.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

