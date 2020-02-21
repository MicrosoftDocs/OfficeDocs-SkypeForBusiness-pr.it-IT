---
title: Migrazione di server di archiviazione e monitoraggio
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67896576fce21eea630533a5826bbcbc53392fa0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="30486-102">Migrazione di server di archiviazione e monitoraggio</span><span class="sxs-lookup"><span data-stu-id="30486-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30486-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="30486-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="30486-104">Se il server di archiviazione e il Monitoring Server sono stati distribuiti in Office Communications Server 2007 R2, è possibile distribuire questi server nell'ambiente Lync Server 2013 dopo aver eseguito la migrazione dei pool Front end.</span><span class="sxs-lookup"><span data-stu-id="30486-104">If you deployed Archiving Server and Monitoring Server in your Office Communications Server 2007 R2, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="30486-105">Se le funzionalità di archiviazione e monitoraggio sono di importanza cruciale per l'organizzazione, tuttavia, è consigliabile aggiungerle al pool pilota prima di eseguire la migrazione in modo che le funzionalità siano disponibili durante il processo di migrazione.</span><span class="sxs-lookup"><span data-stu-id="30486-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="30486-106">Se si desiderano funzionalità di archiviazione e monitoraggio durante la fase di migrazione e coesistenza, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="30486-106">If you want archiving and monitoring functionality during the migration and coexistence phase, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="30486-107">I dati di archiviazione e i dati di monitoraggio non vengono spostati nella distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30486-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="30486-108">I dati di cui è stato eseguito il backup prima della rimozione dell'ambiente legacy saranno la cronologia delle attività in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="30486-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="30486-109">La versione Office Communications Server 2007 R2 del server di archiviazione e il Monitoring Server possono essere associati solo a un pool Front End di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="30486-109">The Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server can be associated only with a Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="30486-110">In Lync Server 2013, l'archiviazione e il monitoraggio non sono più ruoli del server, ma i servizi sono integrati nel pool Front End di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30486-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="30486-111">Durante il periodo di coesistenza tra le distribuzioni legacy e Lync Server 2013, la versione Office Communications Server 2007 R2 del server di archiviazione e il Monitoring Server raccolgono i dati per gli utenti ospitati nei pool di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="30486-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server gather data for users homed on Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="30486-112">La versione Lync Server 2013 del server di archiviazione e il Monitoring Server raccolgono i dati per gli utenti ospitati nei pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30486-112">The Lync Server 2013 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30486-113">Durante la fase di migrazione quando si utilizza ancora il server perimetrale legacy con il nuovo pool pilota di Lync Server 2013, la versione Office Communications Server 2007 R2 del server di archiviazione continua a raccogliere dati per gli utenti ospitati in Office Communications Server 2007 I pool R2 e la versione Lync Server 2013 del server di archiviazione raccolgono i dati per gli utenti ospitati nei pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30486-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Office Communications Server 2007 R2 version of Archiving Server continues to gather data for users homed on Office Communications Server 2007 R2 pools and the Lync Server 2013 version of Archiving Server gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="30486-114">Se si utilizza una soluzione di archiviazione e monitoraggio di terze parti insieme al server di archiviazione e al Monitoring Server, contattare il fornitore quando e in che modo è necessario integrare la soluzione di terze parti con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30486-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving Server and Monitoring Server, talk to your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

