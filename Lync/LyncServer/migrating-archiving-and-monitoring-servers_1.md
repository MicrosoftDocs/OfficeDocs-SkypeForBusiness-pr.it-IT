---
title: Migrazione di server di archiviazione e di monitoraggio
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 902970548d4bd9e95e1bd4e7d6eba75e2fe405d3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="b82ea-102">Migrazione di server di archiviazione e di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="b82ea-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b82ea-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b82ea-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b82ea-104">Se il server di archiviazione e il server di monitoraggio sono stati distribuiti in Office Communications Server 2007 R2, è possibile distribuire questi server nell'ambiente Lync Server 2013 dopo la migrazione dei pool di front-end.</span><span class="sxs-lookup"><span data-stu-id="b82ea-104">If you deployed Archiving Server and Monitoring Server in your Office Communications Server 2007 R2, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="b82ea-105">Se le funzionalità di archiviazione e monitoraggio sono critiche per l'organizzazione, è tuttavia necessario aggiungere l'archiviazione e il monitoraggio al pool di piloti prima di eseguire la migrazione in modo che la funzionalità sia disponibile durante il processo di migrazione.</span><span class="sxs-lookup"><span data-stu-id="b82ea-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="b82ea-106">Per le funzionalità di archiviazione e monitoraggio durante la fase di migrazione e coesistenza, tieni presenti le considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b82ea-106">If you want archiving and monitoring functionality during the migration and coexistence phase, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="b82ea-107">L'archiviazione dei dati e il monitoraggio dei dati non vengono spostati nella distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b82ea-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="b82ea-108">I dati di cui eseguire il backup prima della disattivazione dell'ambiente legacy saranno la cronologia delle attività in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b82ea-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="b82ea-109">La versione di Office Communications Server 2007 R2 del server di archiviazione e del server di monitoraggio può essere associata solo a un pool Front-End di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b82ea-109">The Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server can be associated only with a Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="b82ea-110">In Lync Server 2013 l'archiviazione e il monitoraggio non sono più ruoli del server, ma i servizi sono integrati nel pool Front End di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b82ea-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="b82ea-111">Durante il periodo di coesistenza tra le distribuzioni legacy e Lync Server 2013, la versione Office Communications Server 2007 R2 di Archiving Server e Monitoring Server raccoglie i dati per gli utenti ospitati nei pool di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b82ea-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server gather data for users homed on Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="b82ea-112">La versione Lync Server 2013 di archiviazione del server e del server di monitoraggio raccoglie i dati per gli utenti ospitati nei pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b82ea-112">The Lync Server 2013 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b82ea-113">Durante la fase di migrazione quando si usa ancora il server perimetrale legacy con il nuovo pool di piloti di Lync Server 2013, la versione di archiviazione di Office Communications Server 2007 R2 continua a raccogliere dati per gli utenti ospitati in Office Communications Server 2007 I pool R2 e la versione Lync Server 2013 del server di archiviazione raccolgono i dati per gli utenti ospitati nei pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b82ea-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Office Communications Server 2007 R2 version of Archiving Server continues to gather data for users homed on Office Communications Server 2007 R2 pools and the Lync Server 2013 version of Archiving Server gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="b82ea-114">Se si usa una soluzione di archiviazione e monitoraggio di terze parti in combinazione con server di archiviazione e server di monitoraggio, rivolgersi al proprio fornitore per informazioni su quando e in che modo è necessario integrare la soluzione di terze parti con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b82ea-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving Server and Monitoring Server, talk to your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

