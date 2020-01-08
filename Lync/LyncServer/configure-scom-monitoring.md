---
title: Configurare il monitoraggio di SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e114d3f18e482c11a8e83c9d4308f3c5712932c
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40977360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a>Configurare il monitoraggio di SCOM

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-04_

Dopo aver eseguito la migrazione a Microsoft Lync Server 2013, è necessario completare alcune attività per configurare Lync Server 2013 per l'utilizzo con System Center Operations Manager.

  - Applicare gli aggiornamenti di Lync Server 2010 a un server scelto per gestire la logica di individuazione centrale.

  - Aggiornare la chiave del registro di sistema del server di individuazione centrale.

  - Configurare il server di gestione di System Center Operations Manager principale per eseguire l'override del nodo di individuazione centrale candidata.

Di seguito sono riportate le istruzioni per l'esecuzione di ciascuna di queste attività.

**Applicare gli aggiornamenti di Lync Server 2010 a un server scelto per gestire la logica di individuazione centrale.**

1.  Eleggere un server in cui sono installati i file dell'agente di System Center Operations Manager ed è configurato come nodo di individuazione candidata.

2.  Applicare gli aggiornamenti di Lync Server 2010 al server. Vedere l'argomento [applicare gli aggiornamenti di Lync Server 2010](apply-lync-server-2010-updates.md).

**Aggiornare la chiave del registro di sistema del server di individuazione centrale.**

1.  Nel server scelto per gestire la logica di individuazione centrale aprire una finestra di comando di Windows PowerShell.

2.  Nella riga di comando digitare quanto segue:
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > Ogni volta che si modifica il registro di sistema, potrebbe verificarsi un errore che indica che il comando non è riuscito se la chiave del registro di sistema esiste già. Se si verifica questo problema, è possibile ignorare in modo sicuro l'errore.

    
    </div>

**Configurare il server di gestione di System Center Operations Manager principale per eseguire l'override del nodo di Watcher individuazione centrale candidato.**

1.  In un computer in cui è installata la console di System Center Operations Manager, espandere **oggetti Management Pack** e quindi selezionare individuazioni **oggetti**.

2.  Fare clic su **Cambia ambito.** ..

3.  Nella pagina **oggetti Management Pack di ambito** selezionare **ls Discovery candidate**.

4.  Eseguire l'override del **valore effettivo del candidato di individuazione LS** per il nome del server candidato eletto nella procedura precedente.

Infine, per finalizzare le modifiche, riavviare il servizio integrità nel server di gestione radice di System Center Operations Manager.

</div>

<span> </span>

</div>

</div>

</div>

