---
title: Migrazione di server di archiviazione e di monitoraggio
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba32bf2b35a0d2e8b0048ebb9c62aac09cb6eb7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527410"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="00439-102">Migrazione di server di archiviazione e di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="00439-102">Migrating Archiving and Monitoring servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00439-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="00439-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="00439-104">Se il server di archiviazione e il Monitoring Server sono stati distribuiti nell'ambiente Lync Server 2010, è possibile distribuire questi server nell'ambiente Lync Server 2013 dopo aver eseguito la migrazione dei pool Front end.</span><span class="sxs-lookup"><span data-stu-id="00439-104">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="00439-105">Se le funzionalità di archiviazione e monitoraggio sono fondamentali per l'organizzazione, è tuttavia necessario aggiungere l'archiviazione e il monitoraggio al pool pilota di Lync Server 2013 prima di eseguire la migrazione in modo che le funzionalità siano disponibili durante il processo di migrazione.</span><span class="sxs-lookup"><span data-stu-id="00439-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="00439-106">Se si desidera usufruire delle funzionalità di archiviazione e monitoraggio durante la fase di migrazione, tenere conto delle considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="00439-106">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="00439-107">I dati di archiviazione e i dati di monitoraggio non vengono spostati nella distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00439-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="00439-108">I dati di cui è stato eseguito il backup prima della rimozione delle autorizzazioni per l'ambiente legacy costituiranno la cronologia delle attività nell'ambiente Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="00439-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="00439-109">La versione Lync Server 2010 del server di archiviazione e il Monitoring Server possono essere associati solo a un pool Front End di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="00439-109">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="00439-110">In Lync Server 2013, l'archiviazione e il monitoraggio non sono più ruoli del server, ma i servizi sono integrati nel pool Front End di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00439-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="00439-111">Durante il periodo di coesistenza tra le distribuzioni legacy e Lync Server 2013, la versione Lync Server 2010 del server di archiviazione e il Monitoring Server raccolgono i dati per gli utenti ospitati nei pool di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="00439-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="00439-112">L'archiviazione e il monitoraggio in Lync Server 2013 raccolgono dati per gli utenti ospitati nei pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00439-112">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00439-113">Durante la fase di migrazione quando si utilizza ancora il server perimetrale legacy con il nuovo pool pilota di Lync Server 2013, la versione Lync Server 2010 del server di archiviazione continua a raccogliere dati per gli utenti ospitati nei pool di Lync Server 2010 e l'archiviazione in Lync Server 2013 raccoglie i dati per gli utenti ospitati nei pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00439-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="00439-114">Se si utilizza una soluzione di archiviazione e monitoraggio di terze parti insieme all'archiviazione e al monitoraggio in Lync Server 2013, consultare il fornitore quando e come è necessario integrare la soluzione di terze parti con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00439-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

