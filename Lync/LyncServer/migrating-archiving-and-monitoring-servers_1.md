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
ms.openlocfilehash: 100ec85b345a744232e9bfab37a2ee11c7f84430
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>Migrazione di server di archiviazione e monitoraggio

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

Se il server di archiviazione e il Monitoring Server sono stati distribuiti in Office Communications Server 2007 R2, è possibile distribuire questi server nell'ambiente Lync Server 2013 dopo aver eseguito la migrazione dei pool Front end. Se le funzionalità di archiviazione e monitoraggio sono di importanza cruciale per l'organizzazione, tuttavia, è consigliabile aggiungerle al pool pilota prima di eseguire la migrazione in modo che le funzionalità siano disponibili durante il processo di migrazione.

Se si desiderano funzionalità di archiviazione e monitoraggio durante la fase di migrazione e coesistenza, tenere presente quanto segue:

  - I dati di archiviazione e i dati di monitoraggio non vengono spostati nella distribuzione di Lync Server 2013. I dati di cui è stato eseguito il backup prima della rimozione dell'ambiente legacy saranno la cronologia delle attività in Office Communications Server 2007 R2.

  - La versione Office Communications Server 2007 R2 del server di archiviazione e il Monitoring Server possono essere associati solo a un pool Front End di Office Communications Server 2007 R2. In Lync Server 2013, l'archiviazione e il monitoraggio non sono più ruoli del server, ma i servizi sono integrati nel pool Front End di Lync Server 2013.

  - Durante il periodo di coesistenza tra le distribuzioni legacy e Lync Server 2013, la versione Office Communications Server 2007 R2 del server di archiviazione e il Monitoring Server raccolgono i dati per gli utenti ospitati nei pool di Office Communications Server 2007 R2. La versione Lync Server 2013 del server di archiviazione e il Monitoring Server raccolgono i dati per gli utenti ospitati nei pool di Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Durante la fase di migrazione quando si utilizza ancora il server perimetrale legacy con il nuovo pool pilota di Lync Server 2013, la versione Office Communications Server 2007 R2 del server di archiviazione continua a raccogliere dati per gli utenti ospitati in Office Communications Server 2007 I pool R2 e la versione Lync Server 2013 del server di archiviazione raccolgono i dati per gli utenti ospitati nei pool di Lync Server 2013.

    
    </div>

  - Se si utilizza una soluzione di archiviazione e monitoraggio di terze parti insieme al server di archiviazione e al Monitoring Server, contattare il fornitore quando e in che modo è necessario integrare la soluzione di terze parti con Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

