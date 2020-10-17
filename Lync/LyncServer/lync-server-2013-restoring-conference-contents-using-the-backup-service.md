---
title: 'Lync Server 2013: ripristino del contenuto delle conferenze tramite il servizio di backup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 252cdf6713db7fcb3c4658cc4adb0eb51905c1ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511449"
---
# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a>Ripristino del contenuto delle conferenze tramite il servizio di backup in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Se le informazioni sulla conferenza memorizzate nell'archivio file di un pool Front End diventano non disponibili, è necessario ripristinarle in modo che gli utenti presenti nel pool possano mantenere i propri dati della conferenza. Se il pool Front End che ha perso i dati della conferenza è associato a un altro pool Front End, è possibile utilizzare il servizio di backup per ripristinarli.

È inoltre necessario eseguire questa attività se si verifica un errore dell'intero pool e si deve eseguire il failover degli utenti che vi appartengono in un pool di backup. Quando viene eseguito nuovamente il failover di questi utenti nel pool originale, è necessario utilizzare questa procedura anche per copiare il contenuto della conferenza nel pool originale.

Partire dal presupposto che Pool1 è associato a Pool2, e che i dati della conferenza di Pool1 siano stati persi. È possibile utilizzare il cmdlet seguente per richiamare il servizio di backup per ripristinare il contenuto:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Il ripristino del contenuto della conferenza può richiedere del tempo, a seconda delle dimensioni. È possibile usare il cmdlet seguente per verificare lo stato del processo:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Il processo è terminato quando questo cmdlet restituisce il valore di stato stabile per il modulo della conferenza dati.

</div>

<span> </span>

</div>

</div>

</div>

