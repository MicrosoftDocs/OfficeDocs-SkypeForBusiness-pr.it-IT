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
ms.openlocfilehash: 4edd989985c4ed65027ed8d19725ec1f93c2bdc4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>Migrazione di server di archiviazione e monitoraggio

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

Se il server di archiviazione e il Monitoring Server sono stati distribuiti nell'ambiente Lync Server 2010, è possibile distribuire questi server nell'ambiente Lync Server 2013 dopo aver eseguito la migrazione dei pool Front end. Se le funzionalità di archiviazione e monitoraggio sono fondamentali per l'organizzazione, è tuttavia necessario aggiungere l'archiviazione e il monitoraggio al pool pilota di Lync Server 2013 prima di eseguire la migrazione in modo che le funzionalità siano disponibili durante il processo di migrazione.

Se si desidera usufruire delle funzionalità di archiviazione e monitoraggio durante la fase di migrazione, tenere conto delle considerazioni seguenti:

  - I dati di archiviazione e i dati di monitoraggio non vengono spostati nella distribuzione di Lync Server 2013. I dati di cui è stato eseguito il backup prima della rimozione delle autorizzazioni per l'ambiente legacy costituiranno la cronologia delle attività nell'ambiente Lync Server 2010.

  - La versione Lync Server 2010 del server di archiviazione e il Monitoring Server possono essere associati solo a un pool Front End di Lync Server 2010. In Lync Server 2013, l'archiviazione e il monitoraggio non sono più ruoli del server, ma i servizi sono integrati nel pool Front End di Lync Server 2013.

  - Durante il periodo di coesistenza tra le distribuzioni legacy e Lync Server 2013, la versione Lync Server 2010 del server di archiviazione e il Monitoring Server raccolgono i dati per gli utenti ospitati nei pool di Lync Server 2010. L'archiviazione e il monitoraggio in Lync Server 2013 raccolgono dati per gli utenti ospitati nei pool di Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Durante la fase di migrazione quando si utilizza ancora il server perimetrale legacy con il nuovo pool pilota di Lync Server 2013, la versione Lync Server 2010 del server di archiviazione continua a raccogliere dati per gli utenti ospitati nei pool e nell'archiviazione di Lync Server 2010 in Lync Server 2013 raccoglie i dati per gli utenti ospitati nei pool di Lync Server 2013.

    
    </div>

  - Se si utilizza una soluzione di archiviazione e monitoraggio di terze parti insieme all'archiviazione e al monitoraggio in Lync Server 2013, consultare il fornitore quando e come è necessario integrare la soluzione di terze parti con Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

