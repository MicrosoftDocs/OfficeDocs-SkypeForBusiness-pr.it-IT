---
title: 'Lync Server 2013: Ripristino del contenuto delle conferenze tramite il servizio di backup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14ee33f24f7b1a58812db146901695cba1ae05f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a>Ripristino del contenuto delle conferenze tramite il servizio di backup in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Se le informazioni sulla conferenza archiviate nell'archivio di file di un pool Front-end diventano non disponibili. è necessario ripristinare queste informazioni in modo che gli utenti ospitati nel pool mantengono i dati della conferenza. Se il pool Front-end che ha perso i dati della conferenza è associato a un altro pool Front-End, è possibile usare il servizio di backup per ripristinare i dati.

È necessario eseguire questa operazione anche se un intero pool non è riuscito e non è necessario superare gli utenti in un pool di backup. Quando questi utenti non vengono riattivati nel pool originale, è necessario usare questa procedura per copiare il contenuto della conferenza anche di nuovo nel pool originale.

Supponiamo che pool1 sia associato a Pool2 e che i dati della conferenza in pool1 vengano persi. Puoi usare il cmdlet seguente per richiamare il servizio di backup per ripristinare il contenuto:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Il ripristino del contenuto della conferenza può richiedere del tempo, a seconda delle dimensioni. Puoi usare il cmdlet seguente per controllare lo stato del processo:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Il processo viene eseguito quando questo cmdlet restituisce il valore di stato costante per il modulo conferenza dati.

</div>

<span> </span>

</div>

</div>

</div>

