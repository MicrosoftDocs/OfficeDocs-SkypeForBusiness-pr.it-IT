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
ms.openlocfilehash: 559ebb5a5d5ba91b5a4952037c18ad509ed5cec7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>Panoramica del processo di backup e ripristino per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-26_

Questa sezione offre una panoramica del funzionamento del processo di backup e ripristino per Lync Server 2013. Si usa lo stesso processo per tutti i server Standard Edition e i server Enterprise Edition, indipendentemente dalla loro posizione.

In generale, il processo di backup funziona nel modo seguente:

  - Si crea un percorso di backup come cartella condivisa in un computer autonomo che non fa parte di nessun pool. In **$backup**viene fatto riferimento alla posizione del backup.

  - In base a una normale pianificazione, è possibile eseguire il backup di tutti i database di Lync Server e di tutti gli archivi di file descritti in [requisiti di backup e ripristino in Lync server 2013: dati](lync-server-2013-backup-and-restoration-requirements-data.md) seguendo le procedure descritte in [backup di Lync Server 2013](lync-server-2013-backing-up-lync-server.md) l'archivio di gestione centrale include tutte le impostazioni e le configurazioni del server.

  - Ogni volta che si esegue un backup successivo, si crea una nuova cartella condivisa e si modifica il percorso **$backup** riferimenti.

In generale, il processo di ripristino funziona nel modo seguente:

  - Quando si verifica un errore o un'interruzione, ripristinare i dati nella posizione a cui fa riferimento **$backup** ai computer nuovi o puliti.
    
    <div>
    

    > [!IMPORTANT]  
    > Questo processo di ripristino non ripristina i dati su uno stato del server esistente. Questo processo richiede che il server sia pulito o nuovo.

    
    </div>

  - Per consentire all'utente e alle informazioni della conferenza di essere recuperabili fino al punto di errore, è possibile implementare una topologia di ripristino di emergenza con pool Front-End associati, come descritto in [pianificazione per l'elevata disponibilità e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - Tutte le configurazioni DNS (Domain Name System), la configurazione DHCP (Dynamic Host Configuration Protocol), i nomi di dominio, i nomi di dominio completi di computer (FQDN), i percorsi di archiviazione dei file e così via devono essere uguali al momento del ripristino eseguire il backup.

Se un server che esegue Lync Server non riesce, il ripristino include i passaggi seguenti:

  - Installare il sistema operativo in un computer nuovo o pulito con lo stesso nome di dominio completo del computer non riuscito.

  - Reinstallare i certificati.

  - Se il server ha ospitato un database, installare Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2.

  - In generale, se il server ha ospitato un database, eseguire Generatore di topologie per creare e installare il database e configurare gli elenchi di controllo di accesso (ACL).

  - In generale, se il server ha ospitato un ruolo del server, eseguire il passaggio 1 al passaggio 4 della distribuzione guidata di Lync Server per installare i file di configurazione locali, installare i componenti del ruolo del server, assegnare i certificati e avviare i servizi.
    
    <div>
    

    > [!NOTE]  
    > Se il server ha ospitato un database collocato con il ruolo del server, l'applicazione del passaggio 2 della distribuzione guidata di Lync Server ricrea il database.

    
    </div>

  - Se il server ha ospitato un database, ripristinare i dati di cui è stato eseguito il backup.

</div>

<span> </span>

</div>

</div>

</div>

