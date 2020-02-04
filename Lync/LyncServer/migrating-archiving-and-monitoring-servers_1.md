---
title: Migrazione di server di archiviazione e di monitoraggio
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
ms.openlocfilehash: ee3abd26386ad26e3b6628d5b9db873bd17373be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>Migrazione di server di archiviazione e di monitoraggio

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

Se il server di archiviazione e il server di monitoraggio sono stati distribuiti in Office Communications Server 2007 R2, è possibile distribuire questi server nell'ambiente Lync Server 2013 dopo la migrazione dei pool di front-end. Se le funzionalità di archiviazione e monitoraggio sono critiche per l'organizzazione, è tuttavia necessario aggiungere l'archiviazione e il monitoraggio al pool di piloti prima di eseguire la migrazione in modo che la funzionalità sia disponibile durante il processo di migrazione.

Per le funzionalità di archiviazione e monitoraggio durante la fase di migrazione e coesistenza, tieni presenti le considerazioni seguenti:

  - L'archiviazione dei dati e il monitoraggio dei dati non vengono spostati nella distribuzione di Lync Server 2013. I dati di cui eseguire il backup prima della disattivazione dell'ambiente legacy saranno la cronologia delle attività in Office Communications Server 2007 R2.

  - La versione di Office Communications Server 2007 R2 del server di archiviazione e del server di monitoraggio può essere associata solo a un pool Front-End di Office Communications Server 2007 R2. In Lync Server 2013 l'archiviazione e il monitoraggio non sono più ruoli del server, ma i servizi sono integrati nel pool Front End di Lync Server 2013.

  - Durante il periodo di coesistenza tra le distribuzioni legacy e Lync Server 2013, la versione Office Communications Server 2007 R2 di Archiving Server e Monitoring Server raccoglie i dati per gli utenti ospitati nei pool di Office Communications Server 2007 R2. La versione Lync Server 2013 di archiviazione del server e del server di monitoraggio raccoglie i dati per gli utenti ospitati nei pool di Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Durante la fase di migrazione quando si usa ancora il server perimetrale legacy con il nuovo pool di piloti di Lync Server 2013, la versione di archiviazione di Office Communications Server 2007 R2 continua a raccogliere dati per gli utenti ospitati in Office Communications Server 2007 I pool R2 e la versione Lync Server 2013 del server di archiviazione raccolgono i dati per gli utenti ospitati nei pool di Lync Server 2013.

    
    </div>

  - Se si usa una soluzione di archiviazione e monitoraggio di terze parti in combinazione con server di archiviazione e server di monitoraggio, rivolgersi al proprio fornitore per informazioni su quando e in che modo è necessario integrare la soluzione di terze parti con Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

