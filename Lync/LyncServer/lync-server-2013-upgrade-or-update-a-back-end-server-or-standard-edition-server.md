---
title: Aggiornare o aggiornare un server back-end o un server Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd3617098c42cd38e9928f055a6348a7bf2f9342
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>Aggiornare o aggiornare un server back-end o un server Standard Edition in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

In questo argomento viene descritto come installare un aggiornamento in un server di back-end Enterprise Edition o in un server Standard Edition.

Se un server back-end è inverso verso il basso per almeno 30 minuti mentre lo si sta aggiornando, gli utenti possono accedere alla modalità di resilienza. Al termine dell'aggiornamento e i server back-end sono di nuovo connessi con i Front End Server nel pool, gli utenti vengono restituiti alla funzionalità completa. Se l'aggiornamento richiede meno di 30 minuti, gli utenti non saranno coinvolti.

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Per aggiornare un server back-end o un server Standard Edition

1.  Eseguire l'accesso al server da aggiornare come membro del ruolo CsAdministrator.

2.  Scaricare l'aggiornamento ed estrarlo nel disco rigido locale.

3.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

4.  Arrestare i servizi di Lync Server. Nella riga di comando digitare il comando seguente:
    
        Stop-CsWindowsService

5.  Arrestare il servizio World Wide Web. Nella riga di comando digitare il comando seguente:
    
        net stop w3svc

6.  Chiudere tutte le finestre di Lync Server Management Shell.

7.  Installare l'aggiornamento.

8.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

9.  Arrestare di nuovo i servizi di Lync Server per rilevare la Global Assembly Cache (GAC) – d Assemblies. Nella riga di comando digitare:
    
        Stop-CsWindowsService

10. Riavviare il servizio World Wide Web. Nella riga di comando digitare:
    
        net start w3svc

11. Applicare le modifiche apportate da LyncServerUpdateInstaller.exe ai database di SQL Server eseguendo una delle operazioni seguenti:
    
      - Se si tratta di un server back-end Enterprise Edition e non sono presenti database collocati nel server, ad esempio i database di archiviazione o di monitoraggio, digitare quanto segue nella riga di comando:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - Se si tratta di un server back-end Enterprise Edition e sono presenti database collocati nel server, digitare quanto segue nella riga di comando:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - Se si tratta di un server Standard Edition, digitare quanto segue nella riga di comando:
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

