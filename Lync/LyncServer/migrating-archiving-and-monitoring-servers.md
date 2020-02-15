---
title: Migrazione di server di archiviazione e monitoraggio
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f201b1f7520b365654635c61e4fcebae3c46a0c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="cb7ea-102">Migrazione di server di archiviazione e monitoraggio</span><span class="sxs-lookup"><span data-stu-id="cb7ea-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb7ea-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="cb7ea-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="cb7ea-104">Se il server di archiviazione e il Monitoring Server sono stati distribuiti nell'ambiente Lync Server 2010, è possibile distribuire questi server nell'ambiente Lync Server 2013 dopo aver eseguito la migrazione dei pool Front end.</span><span class="sxs-lookup"><span data-stu-id="cb7ea-104">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="cb7ea-105">Se le funzionalità di archiviazione e monitoraggio sono fondamentali per l'organizzazione, è tuttavia necessario aggiungere l'archiviazione e il monitoraggio al pool pilota di Lync Server 2013 prima di eseguire la migrazione in modo che le funzionalità siano disponibili durante il processo di migrazione.</span><span class="sxs-lookup"><span data-stu-id="cb7ea-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="cb7ea-106">Se si desidera usufruire delle funzionalità di archiviazione e monitoraggio durante la fase di migrazione, tenere conto delle considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb7ea-106">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="cb7ea-107">I dati di archiviazione e i dati di monitoraggio non vengono spostati nella distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb7ea-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="cb7ea-108">I dati di cui è stato eseguito il backup prima della rimozione delle autorizzazioni per l'ambiente legacy costituiranno la cronologia delle attività nell'ambiente Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cb7ea-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="cb7ea-109">La versione Lync Server 2010 del server di archiviazione e il Monitoring Server possono essere associati solo a un pool Front End di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cb7ea-109">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="cb7ea-110">In Lync Server 2013, l'archiviazione e il monitoraggio non sono più ruoli del server, ma i servizi sono integrati nel pool Front End di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb7ea-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="cb7ea-111">Durante il periodo di coesistenza tra le distribuzioni legacy e Lync Server 2013, la versione Lync Server 2010 del server di archiviazione e il Monitoring Server raccolgono i dati per gli utenti ospitati nei pool di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cb7ea-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="cb7ea-112">L'archiviazione e il monitoraggio in Lync Server 2013 raccolgono dati per gli utenti ospitati nei pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb7ea-112">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cb7ea-113">Durante la fase di migrazione quando si utilizza ancora il server perimetrale legacy con il nuovo pool pilota di Lync Server 2013, la versione Lync Server 2010 del server di archiviazione continua a raccogliere dati per gli utenti ospitati nei pool e nell'archiviazione di Lync Server 2010 in Lync Server 2013 raccoglie i dati per gli utenti ospitati nei pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb7ea-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="cb7ea-114">Se si utilizza una soluzione di archiviazione e monitoraggio di terze parti insieme all'archiviazione e al monitoraggio in Lync Server 2013, consultare il fornitore quando e come è necessario integrare la soluzione di terze parti con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb7ea-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

