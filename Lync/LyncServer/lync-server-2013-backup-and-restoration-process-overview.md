---
title: 'Lync Server 2013: Panoramica del processo di backup e ripristino'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9d5e2700065444691dee1041ff210768e9bade7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044878"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>Panoramica del processo di backup e ripristino per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-26_

In questa sezione viene fornita una panoramica di come funziona il processo di backup e ripristino per Lync Server 2013. È possibile utilizzare lo stesso processo per tutti i server Standard Edition e i server Enterprise Edition, indipendentemente dalla posizione in cui si trova.

In generale, il processo di backup funziona come indicato di seguito:

  - È possibile creare un percorso di backup come cartella condivisa in un computer autonomo che non fa parte di un pool. La posizione del backup è referenziata in **$backup**.

  - In base a una pianificazione regolare, è necessario eseguire il backup di tutti i database di Lync Server e di tutti gli archivi di file descritti in [requisiti di backup e ripristino in Lync server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) seguendo le procedure descritte in [backup di Lync Server 2013](lync-server-2013-backing-up-lync-server.md) nell'archivio di gestione centrale sono incluse tutte le impostazioni e le configurazioni del server.

  - Ogni volta che si esegue un backup successivo, si crea una nuova cartella condivisa e si modifica il percorso **$backup** riferimenti.

In generale, il processo di ripristino funziona come indicato di seguito:

  - Quando si verifica un errore o un'interruzione, ripristinare i dati nel percorso a cui viene fatto riferimento **$backup** ai computer nuovi o puliti.
    
    <div>
    

    > [!IMPORTANT]  
    > Questo processo di ripristino non ripristina i dati su uno stato del server esistente. Questo è il processo che richiede che il server sia pulito o nuovo.

    
    </div>

  - Affinché le informazioni sull'utente e sulla conferenza possano essere recuperate fino al punto di errore, è possibile implementare una topologia di ripristino di emergenza con pool Front End abbinati, come descritto in [pianificazione della disponibilità elevata e del ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - Tutte le configurazioni DNS (Domain Name System), la configurazione del protocollo DHCP (Dynamic Host Configuration Protocol), i nomi di dominio, i nomi di dominio completi (FQDN) del computer, i percorsi di archiviazione dei file e così via devono essere uguali al momento del ripristino che si trovavano al momento del eseguire il backup.

Se un server su cui è in esecuzione Lync Server ha esito negativo, il ripristino include i passaggi seguenti:

  - Installare il sistema operativo in un computer nuovo o pulito con lo stesso FQDN del computer in cui si è verificato l'errore.

  - Reinstallare i certificati.

  - Se il server ospita un database, installare Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2.

  - In generale, se il server ospita un database, eseguire Generatore di topologie per creare e installare il database e configurare gli elenchi di controllo di accesso (ACL, Access Control List).

  - In generale, se il server ospita un ruolo del server, eseguire il passaggio 1 del passaggio 4 della distribuzione guidata di Lync Server per installare i file di configurazione locali, installare i componenti del ruolo del server, assegnare i certificati e avviare i servizi.
    
    <div>
    

    > [!NOTE]  
    > Se il server ospita un database collocato con il ruolo del server, l'esecuzione del passaggio 2 della distribuzione guidata di Lync Server consente di ricreare il database.

    
    </div>

  - Se il server ospita un database, ripristinare i dati di cui è stato eseguito il backup.

</div>

<span> </span>

</div>

</div>

</div>

