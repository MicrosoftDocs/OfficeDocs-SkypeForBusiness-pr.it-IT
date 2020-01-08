---
title: 'Lync Server 2013: requisiti per i servizi di conferenza Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dddfd7c2fdfe6cbcefcca7533e93c3c377cceea8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="e131c-102">Requisiti per i servizi di conferenza Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e131c-102">Web conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e131c-103">_**Argomento Ultima modifica:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="e131c-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="e131c-104">Se si è scelto di abilitare i servizi di conferenza Web, è necessario pianificare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e131c-104">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="e131c-105">Accedere all'archivio file, che viene usato per archiviare il contenuto delle conferenze Web.</span><span class="sxs-lookup"><span data-stu-id="e131c-105">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="e131c-106">Integrazione con Office Web Apps Server, che è necessario per condividere i file di PowerPoint durante una conferenza.</span><span class="sxs-lookup"><span data-stu-id="e131c-106">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="e131c-107">Archivio file</span><span class="sxs-lookup"><span data-stu-id="e131c-107">File Store</span></span>

<span data-ttu-id="e131c-108">Il servizio di conferenza Web Lync Server 2013 archivia il contenuto condiviso durante le riunioni nell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="e131c-108">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="e131c-109">Come parte della distribuzione, è necessario specificare una condivisione file da usare come archivio file per il pool di server standard o Enterprise Edition front-end.</span><span class="sxs-lookup"><span data-stu-id="e131c-109">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="e131c-110">È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file, oltre a un nome di cartella per la nuova condivisione file.</span><span class="sxs-lookup"><span data-stu-id="e131c-110">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="e131c-111">Per altre informazioni, vedere Generatore di topologie: definire l'archivio di file per il front-end.</span><span class="sxs-lookup"><span data-stu-id="e131c-111">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="e131c-112">Il servizio Web Conferencing crittografa il contenuto prima di archiviare il contenuto nell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="e131c-112">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="e131c-113">Lync Server 2013 supporta l'uso di condivisioni file in un ambiente di archiviazione Direct Attached (DAS) o in una rete di archiviazione (SAN), incluso il file System distribuito (DFS) e in una matrice ridondante di dischi indipendenti (RAID) per archivi di file.</span><span class="sxs-lookup"><span data-stu-id="e131c-113">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="e131c-114">Dopo che la distribuzione guidata di Lync Server ha definito la posizione della condivisione file, Lync Server crea una struttura di cartelle all'interno della condivisione file simile a:</span><span class="sxs-lookup"><span data-stu-id="e131c-114">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="e131c-115">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="e131c-115">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="e131c-116">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="e131c-116">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="e131c-117">1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="e131c-117">1-WebServices-1</span></span>
    
      - <span data-ttu-id="e131c-118">CollabContent</span><span class="sxs-lookup"><span data-stu-id="e131c-118">CollabContent</span></span>
    
      - <span data-ttu-id="e131c-119">CollabMetadata</span><span class="sxs-lookup"><span data-stu-id="e131c-119">CollabMetadata</span></span>
    
      - <span data-ttu-id="e131c-120">Dataconf</span><span class="sxs-lookup"><span data-stu-id="e131c-120">DataConf</span></span>

<span data-ttu-id="e131c-121">Il servizio Web Conferencing consente quindi di archiviare contenuti come diapositive di PowerPoint, lavagne, sondaggi e allegati nelle cartelle CollabContent e CollabMetadata, che si trovano nella cartella WebServices.</span><span class="sxs-lookup"><span data-stu-id="e131c-121">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="e131c-122">L'amministratore deve impostare le autorizzazioni per la condivisione di file in modo che i gruppi RTC dispongano dell'accesso di lettura e scrittura necessario.</span><span class="sxs-lookup"><span data-stu-id="e131c-122">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="e131c-123">Se si verificano errori con le autorizzazioni, aprire Generatore di topologie, scaricare e ripubblicare la topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="e131c-123">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology.</span></span> <span data-ttu-id="e131c-124">La pubblicazione della topologia verificherà le autorizzazioni di condivisione file e reimpostarle, se necessario.</span><span class="sxs-lookup"><span data-stu-id="e131c-124">Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="e131c-125">Per gestire la modalità di archiviazione del contenuto per una riunione, è possibile usare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e131c-125">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="e131c-126">**ContentGracePeriod**, che si trova in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), imposta il periodo di tempo in cui il contenuto delle conferenze Web rimarrà sul server al termine della riunione.</span><span class="sxs-lookup"><span data-stu-id="e131c-126">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="e131c-127">**MaxContentStorageMB**, che si trova in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), imposta la quantità massima di spazio su file consentita per l'archiviazione del contenuto durante una singola riunione.</span><span class="sxs-lookup"><span data-stu-id="e131c-127">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="e131c-128">**MaxUploadFileSizeMb** non limita l'impostazione di caricamento dei file per Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="e131c-128">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="e131c-129">Il limite di caricamento delle dimensioni dei file per Lync Web App è impostato su circa 30MB e viene controllato dal file Web. config di\[IIS\]:/DataCollabWeb/int ext/handler/Web.config. Per configurare il limite di caricamento delle dimensioni dei file per Lync Web `maxRequestLength` app `maxAllowedContentLength` , aggiornare e nel file Web. config come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e131c-129">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by Lync Web App client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for Lync Web App upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

<span data-ttu-id="e131c-130">È necessario aggiornare il file Web. config per ogni server front-end.</span><span class="sxs-lookup"><span data-stu-id="e131c-130">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="e131c-131">Server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="e131c-131">Office Web Apps Server</span></span>

<span data-ttu-id="e131c-132">Per usare questi nuovi amministratori delle funzionalità, è necessario installare Office Web Apps Server e configurare Lync Server 2013 per la comunicazione con Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="e131c-132">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="e131c-133">Questa documentazione contiene informazioni su come configurare Lync Server 2013 per l'utilizzo con Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="e131c-133">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="e131c-134">La documentazione in questione non è disponibile per informazioni su come installare Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="e131c-134">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="e131c-135">Per informazioni dettagliate sull'installazione, vedere il sito Web Microsoft Office Web <http://go.microsoft.com/fwlink/p/?linkid=257525>Apps Deployment.</span><span class="sxs-lookup"><span data-stu-id="e131c-135">For installation details, see the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="e131c-136">Questa guida include informazioni complete sui prerequisiti per Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="e131c-136">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="e131c-137">Tieni presente che il server Office Web Apps deve essere installato in un computer autonomo che non è in grado di eseguire Lync Server, SQL Server o qualsiasi altra applicazione server.</span><span class="sxs-lookup"><span data-stu-id="e131c-137">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="e131c-138">Non è necessario che nel computer sia installata una versione di Office. Qualsiasi computer usato per eseguire Office Web Apps Server deve avere anche un set di software specifico installato (inclusi .NET Framework 4,5 e Windows PowerShell 3,0).</span><span class="sxs-lookup"><span data-stu-id="e131c-138">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="e131c-139">Questi requisiti, oltre a informazioni sulla configurazione di certificati e Internet Information Services (IIS), vengono descritti in dettaglio nel sito Web Microsoft Office Web Apps Deployment <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span><span class="sxs-lookup"><span data-stu-id="e131c-139">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e131c-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e131c-140">See Also</span></span>


[<span data-ttu-id="e131c-141">Panoramica delle conferenze Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e131c-141">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="e131c-142">Elenco di controllo della distribuzione per i servizi di conferenza Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e131c-142">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

