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

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="9e97d-102">Ripristino del contenuto delle conferenze tramite il servizio di backup in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e97d-102">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e97d-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9e97d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9e97d-104">Se le informazioni sulla conferenza archiviate nell'archivio di file di un pool Front-end diventano non disponibili.</span><span class="sxs-lookup"><span data-stu-id="9e97d-104">If the conference information stored in the file store of a Front End pool becomes unavailable.</span></span> <span data-ttu-id="9e97d-105">è necessario ripristinare queste informazioni in modo che gli utenti ospitati nel pool mantengono i dati della conferenza.</span><span class="sxs-lookup"><span data-stu-id="9e97d-105">you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="9e97d-106">Se il pool Front-end che ha perso i dati della conferenza è associato a un altro pool Front-End, è possibile usare il servizio di backup per ripristinare i dati.</span><span class="sxs-lookup"><span data-stu-id="9e97d-106">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="9e97d-107">È necessario eseguire questa operazione anche se un intero pool non è riuscito e non è necessario superare gli utenti in un pool di backup.</span><span class="sxs-lookup"><span data-stu-id="9e97d-107">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="9e97d-108">Quando questi utenti non vengono riattivati nel pool originale, è necessario usare questa procedura per copiare il contenuto della conferenza anche di nuovo nel pool originale.</span><span class="sxs-lookup"><span data-stu-id="9e97d-108">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="9e97d-109">Supponiamo che pool1 sia associato a Pool2 e che i dati della conferenza in pool1 vengano persi.</span><span class="sxs-lookup"><span data-stu-id="9e97d-109">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="9e97d-110">Puoi usare il cmdlet seguente per richiamare il servizio di backup per ripristinare il contenuto:</span><span class="sxs-lookup"><span data-stu-id="9e97d-110">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="9e97d-111">Il ripristino del contenuto della conferenza può richiedere del tempo, a seconda delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="9e97d-111">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="9e97d-112">Puoi usare il cmdlet seguente per controllare lo stato del processo:</span><span class="sxs-lookup"><span data-stu-id="9e97d-112">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="9e97d-113">Il processo viene eseguito quando questo cmdlet restituisce il valore di stato costante per il modulo conferenza dati.</span><span class="sxs-lookup"><span data-stu-id="9e97d-113">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

