---
title: 'Lync Server 2013: ripristino del contenuto delle conferenze tramite il servizio di backup'
description: 'Lync Server 2013: ripristino del contenuto delle conferenze tramite il servizio di backup.'
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
ms.openlocfilehash: a3a0037af711948c008e74c5444373ed995f0e6e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555182"
---
# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="81292-103">Ripristino del contenuto delle conferenze tramite il servizio di backup in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81292-103">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81292-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="81292-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="81292-p101">Se le informazioni sulla conferenza memorizzate nell'archivio file di un pool Front End diventano non disponibili, è necessario ripristinarle in modo che gli utenti presenti nel pool possano mantenere i propri dati della conferenza. Se il pool Front End che ha perso i dati della conferenza è associato a un altro pool Front End, è possibile utilizzare il servizio di backup per ripristinarli.</span><span class="sxs-lookup"><span data-stu-id="81292-p101">If the conference information stored in the file store of a Front End pool becomes unavailable. you must restore this information so that users homed on the pool retain their conference data. If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="81292-p102">È inoltre necessario eseguire questa attività se si verifica un errore dell'intero pool e si deve eseguire il failover degli utenti che vi appartengono in un pool di backup. Quando viene eseguito nuovamente il failover di questi utenti nel pool originale, è necessario utilizzare questa procedura anche per copiare il contenuto della conferenza nel pool originale.</span><span class="sxs-lookup"><span data-stu-id="81292-p102">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="81292-110">Partire dal presupposto che Pool1 è associato a Pool2, e che i dati della conferenza di Pool1 siano stati persi.</span><span class="sxs-lookup"><span data-stu-id="81292-110">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="81292-111">È possibile utilizzare il cmdlet seguente per richiamare il servizio di backup per ripristinare il contenuto:</span><span class="sxs-lookup"><span data-stu-id="81292-111">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="81292-p104">Il ripristino del contenuto della conferenza può richiedere del tempo, a seconda delle dimensioni. È possibile usare il cmdlet seguente per verificare lo stato del processo:</span><span class="sxs-lookup"><span data-stu-id="81292-p104">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="81292-114">Il processo è terminato quando questo cmdlet restituisce il valore di stato stabile per il modulo della conferenza dati.</span><span class="sxs-lookup"><span data-stu-id="81292-114">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

