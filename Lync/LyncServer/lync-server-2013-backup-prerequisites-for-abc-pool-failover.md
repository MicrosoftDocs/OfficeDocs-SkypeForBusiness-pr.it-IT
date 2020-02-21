---
title: 'Lync Server 2013: prerequisiti di backup per il failover del pool ABC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bd6bd22b29cd5031e83f0e8e8a09755c730be64
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a><span data-ttu-id="47439-102">Prerequisiti di backup per il failover del pool ABC in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47439-102">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47439-103">_**Ultimo argomento modificato:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="47439-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="47439-104">Per ottenere il massimo vantaggio dall'utilizzo della procedura di failover del pool ABC, è necessario eseguire alcuni backup prima che si verifichino le operazioni di emergenza e failover:</span><span class="sxs-lookup"><span data-stu-id="47439-104">To get the maximum benefit from using the ABC pool failover procedure, you must perform certain backups before the disaster and failover happen:</span></span>

  - <span data-ttu-id="47439-105">È necessario eseguire regolarmente il backup dei dati di configurazione LIS (Location Information Service) dal pool A utilizzando il cmdlet **Export-CsLISConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="47439-105">You must regularly back up the Location Information Service (LIS) configuration data from pool A by using the **Export-CsLISConfiguration** cmdlet.</span></span>
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - <span data-ttu-id="47439-106">È necessario eseguire regolarmente il backup dei dati di configurazione di Response Group nel pool A utilizzando il cmdlet **Export-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="47439-106">You must regularly back up the Response Group configuration data in pool A by using the **Export-CsRgsConfiguration** cmdlet.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <span data-ttu-id="47439-107">In generale, è consigliabile eseguire backup giornalieri, ma in presenza di un volume elevato di modifiche è possibile pianificare backup più frequenti.</span><span class="sxs-lookup"><span data-stu-id="47439-107">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="47439-108">La quantità di informazioni che possono essere perse in caso di emergenza dipende dalla frequenza dei backup, nonché dalla frequenza e dal volume delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="47439-108">The amount of information that you can lose in the event of a disaster depends on the frequency of your backups, as well as on the frequency and volume of changes.</span></span>
    
    <span data-ttu-id="47439-109">L'applicazione Response Group è in grado di archiviare solo un set di impostazioni a livello di applicazione per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="47439-109">The Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="47439-110">È possibile accedere a queste impostazioni tramite i cmdlet **Get-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="47439-110">These settings can be accessed through the **Get-CsRgsConfiguration** cmdlets.</span></span> <span data-ttu-id="47439-111">Le impostazioni includono la configurazione predefinita per la musica in attesa, il file audio predefinito per la musica in attesa, il periodo di tolleranza Ring-back dell'agente e la configurazione del contesto di chiamata.</span><span class="sxs-lookup"><span data-stu-id="47439-111">The settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ring-back grace period, and the call context configuration.</span></span> <span data-ttu-id="47439-112">Queste impostazioni possono essere trasferite da un pool all'altro tramite il cmdlet **Import-CsRgsConfiguration** utilizzando il parametro **ReplaceExistingSettings** , ma questa operazione sostituirà tutte le impostazioni a livello di applicazione nel pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="47439-112">These settings can be transferred from one pool to another through the **Import-CsRgsConfiguration** cmdlet by using the **ReplaceExistingSettings** parameter, but this operation will override any application-level settings in the destination pool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="47439-113">In un percorso separato, conservare una copia di backup di tutti i file audio originali che sono stati utilizzati per configurare l'applicazione Response Group, ovvero eventuali registrazioni o file musicali in attesa.</span><span class="sxs-lookup"><span data-stu-id="47439-113">In a separate location, keep a backup copy of all the original audio files that have been used to configure the Response Group application (that is, any recordings or music-on-hold files).</span></span>

    
    </div>
    
    <span data-ttu-id="47439-114">Se si dispone di file musicali personalizzati che sono stati caricati per il parcheggio di chiamata in un pool, è consigliabile conservarne una copia in un'altra posizione.</span><span class="sxs-lookup"><span data-stu-id="47439-114">If you have any customized music-on-hold files that have been uploaded for Call Park in a pool, you should keep a copy of these in another location.</span></span> <span data-ttu-id="47439-115">Questi file non vengono sottoposti a backup come parte del processo di ripristino di emergenza di Lync Server 2013 e verranno persi se i file caricati nel pool sono danneggiati, danneggiati o eliminati.</span><span class="sxs-lookup"><span data-stu-id="47439-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="47439-116">L'applicazione Parcheggio di chiamata può archiviare un solo set di impostazioni e un file audio personalizzato per il pool.</span><span class="sxs-lookup"><span data-stu-id="47439-116">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="47439-117">È possibile accedere a queste impostazioni tramite il cmdlet <STRONG>Get-CsCpsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="47439-117">These settings can be accessed through the <STRONG>Get-CsCpsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="47439-118">Poiché il meccanismo di ripristino di emergenza per il parcheggio di chiamata si basa sull'applicazione Parcheggio di chiamata del pool di backup, le impostazioni del pool primario non vengono sottoposte a backup o conservate se si verifica un evento di emergenza.</span><span class="sxs-lookup"><span data-stu-id="47439-118">Because the disaster recovery mechanism for Call Park relies on the Call Park application of the backup pool, the settings of the primary pool are not backed up or preserved if a disaster occurs.</span></span> <span data-ttu-id="47439-119">Se il pool primario è perduto, queste impostazioni non possono essere ripristinate e quando viene distribuito un nuovo pool per sostituire il pool primario, è necessario riconfigurare le impostazioni del parcheggio di chiamata e qualsiasi file audio di musica in attesa personalizzato.</span><span class="sxs-lookup"><span data-stu-id="47439-119">If the primary pool is lost, these settings cannot be recovered, and when a new pool is deployed to replace the primary pool, the Call Park settings and any customized music-on-hold audio file would need to be reconfigured.</span></span>

    
    </div>

  - <span data-ttu-id="47439-120">Se si configurano annunci come parte della funzionalità per i numeri non assegnati, è consigliabile mantenere in un'altra posizione una copia di qualsiasi file audio originale utilizzato durante la configurazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="47439-120">If you configure any announcements as part of the Unassigned Number Voice Feature, we recommend that you keep in another location a copy of any original audio file used during the initial configuration.</span></span> <span data-ttu-id="47439-121">In caso contrario, è possibile ottenere una copia dei file audio configurati nell'archivio file del server o del pool in cui sono stati importati i file audio.</span><span class="sxs-lookup"><span data-stu-id="47439-121">If you did not do that, you can get a copy of the configured audio files in the file store of the server or pool to which the audio files were imported.</span></span> <span data-ttu-id="47439-122">Questi file non vengono sottoposti a backup come parte del processo di ripristino di emergenza di Lync Server 2013 e verranno persi se i file caricati nel pool sono danneggiati, danneggiati o eliminati.</span><span class="sxs-lookup"><span data-stu-id="47439-122">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="47439-123">Per copiare tutti i file audio utilizzati per configurare la funzionalità vocale numeri non assegnati dall'archivio file di un server o di un pool, utilizzare:</span><span class="sxs-lookup"><span data-stu-id="47439-123">To copy all the audio files used to configure the Unassigned Number Voice Feature from the file store of a server or a pool, use:</span></span>
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - <span data-ttu-id="47439-124">Se si dispone di database di monitoraggio e archiviazione in un pool, è consigliabile utilizzare gli strumenti di gestione di SQL Server per eseguirne il backup.</span><span class="sxs-lookup"><span data-stu-id="47439-124">If you have Monitoring and Archiving databases in a pool, you should use SQL Server management tools to back them up.</span></span> <span data-ttu-id="47439-125">Nella procedura di failover ABC, i database di monitoraggio e archiviazione non vengono conservati se sono collocati nel pool A, perché non è stato eseguito il backup di questi database tramite il servizio di backup di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="47439-125">In the ABC failover procedure, Monitoring and Archiving databases are not preserved if they are collocated in pool A, because these databases are not backed up through Lync Server Backup Service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

