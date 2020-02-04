---
title: 'Lync Server 2013: backup dei dati e delle impostazioni di base'
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
ms.openlocfilehash: 4185c02bc85077b0f68ca76d83fd48203e0e5fd9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>Backup dei dati e delle impostazioni di base in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-04-23_

Le procedure seguenti usano i cmdlet di Lync Server Management Shell per creare file di backup per le impostazioni e i dati per i servizi principali. Per informazioni dettagliate sugli strumenti usati in questa sezione, inclusi i casi in cui si trovano, vedere [requisiti di backup e ripristino in Lync Server 2013: strumenti e autorizzazioni](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md). Per informazioni dettagliate su come eseguire il backup dei dati di archiviazione e monitoraggio, vedere [backup di archiviazione e monitoraggio di database in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).

<div>


> [!NOTE]  
> Il passaggio in questa sezione per eseguire il backup di Central Management Store include le impostazioni e la configurazione per l'archiviazione e il monitoraggio.



</div>

È possibile eseguire i cmdlet descritti in questa sezione localmente o in remoto.

<div>

## <a name="to-back-up-core-data-and-settings"></a>Per eseguire il backup dei dati e delle impostazioni principali

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere a qualsiasi computer della distribuzione interna.

2.  Per archiviare i backup creati nei passaggi seguenti, creare una nuova cartella condivisa e aggiornare il percorso a cui fa riferimento **$backup** alla nuova cartella condivisa.

3.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

4.  Eseguire il backup del file di configurazione di Central Management store. Nella riga di comando digitare quanto segue:
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    Ad esempio:
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > Questo passaggio Esporta la topologia, i criteri e le impostazioni di configurazione di Lync Server in un file. Nessun altro passaggio è necessario per eseguire il backup dei dati della topologia.

    
    </div>

5.  Copiare il file di configurazione dell'archivio di gestione centralizzato di cui\\è stato eseguito il backup in $backup.

6.  Eseguire il backup dei dati del servizio informazioni sulla posizione. Nella riga di comando digitare quanto segue:
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    Ad esempio:
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  Copiare il file di configurazione del servizio informazioni posizione di cui è stato\\eseguito il backup in $backup.

8.  Eseguire il backup dei dati degli utenti in tutti i database back-end di un pool Front-end e di ogni server Standard Edition. Nella riga di comando digitare quanto segue:
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    Ad esempio:
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  Copiare il file utente di cui è stato eseguito\\il backup in $backup.

10. In tutti i pool che esegue l'applicazione Response Group, eseguire il backup della configurazione del gruppo di risposte. Effettuare le seguenti operazioni:
    
    1.  Nella riga di comando digitare:
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        Ad esempio:
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. Copiare il file di configurazione del gruppo di risposta di cui\\è stato eseguito il backup in $backup.

</div>

</div>

<span> </span>

</div>

</div>

</div>

