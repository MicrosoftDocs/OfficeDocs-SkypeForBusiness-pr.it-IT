---
title: 'Lync Server 2013: backup dei dati di base e delle impostazioni'
description: 'Lync Server 2013: backup dei dati di base e delle impostazioni.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 637eeb950a3b8380f6e756f46a5083f51b5d7e1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543742"
---
# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>Backup dei dati di base e delle impostazioni in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-04-23_

Nelle procedure seguenti vengono utilizzati i cmdlet di Lync Server Management Shell per creare file di backup per le impostazioni e i dati per i servizi di base. Per informazioni dettagliate sugli strumenti utilizzati in questa sezione, incluso il percorso in cui si trovano, vedere [backup and Restoration requirements in Lync Server 2013: Tools and Permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md). Per informazioni dettagliate sul backup dei dati di archiviazione e di monitoraggio, vedere [backing up Archiving and Monitoring Databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).

<div>


> [!NOTE]  
> Il passaggio in questa sezione per eseguire il backup dell'archivio di gestione centrale include le impostazioni e la configurazione per l'archiviazione e il monitoraggio.



</div>

È possibile eseguire i cmdlet descritti in questa sezione localmente o da postazione remota.

<div>

## <a name="to-back-up-core-data-and-settings"></a>Per eseguire il backup dei dati e delle impostazioni di base

1.  Eseguire l'accesso a un computer della distribuzione interna utilizzando un account utente membro del gruppo RTCUniversalServerAdmins.

2.  Per archiviare i backup creati nei passaggi seguenti, creare una nuova cartella condivisa e aggiornare il percorso utilizzato come riferimento da **$Backup** sostituendolo con la nuova cartella condivisa.

3.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

4.  Eseguire il backup del file di configurazione dell'archivio di gestione centrale. Nella riga di comando digitare quanto segue:
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    Ad esempio:
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > In questo passaggio vengono esportate in un file la topologia, i criteri e le impostazioni di configurazione di Lync Server. Non sono richieste altre operazioni per il backup dei dati della topologia.

    
    </div>

5.  Copiare il file di configurazione dell'archivio di gestione centrale di cui è stato eseguito il backup in $Backup \\ .

6.  Eseguire il backup dei dati del servizio Informazioni percorso. Nella riga di comando digitare il comando seguente:
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    Ad esempio:
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  Copiare il file di configurazione del servizio informazioni percorso di cui è stato eseguito il backup in $Backup \\ .

8.  Eseguire il backup dei dati degli utenti su ogni database back-end di un pool Front end e di ogni server Standard Edition. Nella riga di comando digitare quanto segue:
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    Ad esempio:
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  Copiare il file dell'utente di cui è stato eseguito il backup in $Backup \\ .

10. In ogni pool che esegue l'applicazione Response Group eseguire il backup della configurazione di Response Group. Eseguire le operazioni seguenti:
    
    1.  Nella riga di comando digitare il comando seguente:
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        Ad esempio:
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. Copiare il file di configurazione di Response Group di cui è stato eseguito il backup su $Backup \\ .

</div>

</div>

<span> </span>

</div>

</div>

</div>

