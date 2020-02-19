---
title: 'Lync Server 2013: requisiti di Web Conferencing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b75663f1e5bc51136ac0a2254944541716ad6f74
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="0d800-102">Requisiti di Web Conferencing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d800-102">Web conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d800-103">_**Ultimo argomento modificato:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="0d800-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="0d800-104">Se si decide di abilitare le conferenze Web, è necessario pianificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0d800-104">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="0d800-105">Accesso all'archivio file utilizzato per l'archiviazione del contenuto delle conferenze Web.</span><span class="sxs-lookup"><span data-stu-id="0d800-105">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="0d800-106">Integrazione con il server Office Web Apps, che è necessario per condividere i file di PowerPoint durante una conferenza.</span><span class="sxs-lookup"><span data-stu-id="0d800-106">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="0d800-107">Archivio file</span><span class="sxs-lookup"><span data-stu-id="0d800-107">File Store</span></span>

<span data-ttu-id="0d800-108">Il servizio Web Conferencing di Lync Server 2013 archivia il contenuto condiviso durante le riunioni nell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="0d800-108">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="0d800-109">Nell'ambito della distribuzione, è necessario specificare una condivisione file da utilizzare come archivio file per il server Standard Edition o per il pool Enterprise Edition front end.</span><span class="sxs-lookup"><span data-stu-id="0d800-109">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="0d800-110">È possibile utilizzare una condivisione di file esistente per l'archivio file oppure specificare una nuova condivisione di file indicando il nome di dominio completo (FQDN) del file server in cui deve essere posizionata la condivisione di file, nonché un nome di cartella per la nuova condivisione di file.</span><span class="sxs-lookup"><span data-stu-id="0d800-110">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="0d800-111">Per ulteriori informazioni, vedere Generatore di topologie – Definire l'archivio file per il pool Front End.</span><span class="sxs-lookup"><span data-stu-id="0d800-111">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="0d800-112">Il servizio per conferenze Web crittografa il contenuto prima di archiviarlo nell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="0d800-112">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="0d800-113">Lync Server 2013 supporta l'utilizzo di condivisioni file su una rete di archiviazione diretta (DAS, Direct Attached Storage) o su un sistema di archiviazione (SAN), incluso il file System distribuito (DFS) e un array di dischi indipendenti (RAID) ridondante per gli archivi di file.</span><span class="sxs-lookup"><span data-stu-id="0d800-113">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="0d800-114">Dopo che la distribuzione guidata di Lync Server ha definito il percorso della condivisione file, Lync Server crea una struttura di cartelle all'interno della condivisione file simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="0d800-114">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="0d800-115">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="0d800-115">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="0d800-116">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="0d800-116">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="0d800-117">1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="0d800-117">1-WebServices-1</span></span>
    
      - <span data-ttu-id="0d800-118">CollabContent</span><span class="sxs-lookup"><span data-stu-id="0d800-118">CollabContent</span></span>
    
      - <span data-ttu-id="0d800-119">CollabMetadata</span><span class="sxs-lookup"><span data-stu-id="0d800-119">CollabMetadata</span></span>
    
      - <span data-ttu-id="0d800-120">Dataconf</span><span class="sxs-lookup"><span data-stu-id="0d800-120">DataConf</span></span>

<span data-ttu-id="0d800-121">Il servizio di conferenza Web archivia quindi il contenuto, ad esempio diapositive di PowerPoint, lavagne, sondaggi e allegati, nelle cartelle CollabContent e CollabMetadata che si trovano nella cartella WebServices.</span><span class="sxs-lookup"><span data-stu-id="0d800-121">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="0d800-122">L'amministratore deve impostare le autorizzazioni sulla condivisione file in modo che i gruppi RTC dispongano delle necessarie autorizzazioni di accesso in lettura e scrittura.</span><span class="sxs-lookup"><span data-stu-id="0d800-122">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0d800-p103">In caso di problemi con le autorizzazioni, aprire il Generatore di topologie, scaricare e ripubblicare la topologia esistente. Durante la pubblicazione della topologia vengono verificate le autorizzazioni per la condivisione file e vengono reimpostate, se necessario.</span><span class="sxs-lookup"><span data-stu-id="0d800-p103">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology. Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="0d800-125">È possibile utilizzare le impostazioni seguenti per gestire l'archiviazione del contenuto per una riunione:</span><span class="sxs-lookup"><span data-stu-id="0d800-125">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="0d800-126">**ContentGracePeriod**, disponibile in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), consente di impostare il tempo di permanenza del contenuto Web Conferencing sul server dopo la fine della riunione.</span><span class="sxs-lookup"><span data-stu-id="0d800-126">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="0d800-127">**MaxContentStorageMB**, che si trova in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), imposta la quantità massima di spazio di file consentita per l'archiviazione del contenuto durante una singola riunione.</span><span class="sxs-lookup"><span data-stu-id="0d800-127">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="0d800-128">**MaxUploadFileSizeMb** non limita l'impostazione di caricamento dei file per Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="0d800-128">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="0d800-129">Il limite di caricamento delle dimensioni dei file per Lync Web App è impostato su approssimativamente 30MB ed è controllato dal file Web. config di\[IIS\]:/DataCollabWeb/int ext/handler/Web.config. Per configurare il limite di caricamento delle dimensioni dei file per Lync Web `maxRequestLength` app `maxAllowedContentLength` , aggiornarlo e nel file Web. config come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0d800-129">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

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

<span data-ttu-id="0d800-130">È necessario aggiornare il file Web. config per ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="0d800-130">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="0d800-131">server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="0d800-131">Office Web Apps Server</span></span>

<span data-ttu-id="0d800-132">Per poter utilizzare questi nuovi amministratori delle funzionalità, è necessario installare il server Office Web Apps e configurare Lync Server 2013 per la comunicazione con il server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="0d800-132">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="0d800-133">In questa documentazione vengono fornite informazioni su come configurare Lync Server 2013 per l'utilizzo con il server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="0d800-133">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="0d800-134">La documentazione non fornita contiene informazioni su come installare il server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="0d800-134">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="0d800-135">Per informazioni dettagliate sull'installazione, vedere il sito Web Microsoft Office Web <https://go.microsoft.com/fwlink/p/?linkid=257525>Apps Deployment all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="0d800-135">For installation details, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="0d800-136">Tale guida include informazioni complete sui prerequisiti per il server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="0d800-136">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="0d800-137">Si noti che il server Office Web Apps deve essere installato in un computer autonomo che non esegue Lync Server, SQL Server o qualsiasi altra applicazione server.</span><span class="sxs-lookup"><span data-stu-id="0d800-137">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="0d800-138">Non è necessario disporre di una versione di Office installata nel computer in questione. Qualsiasi computer utilizzato per eseguire il server Office Web Apps deve disporre anche di un insieme specifico di software installato (inclusi .NET Framework 4,5 e Windows PowerShell 3,0).</span><span class="sxs-lookup"><span data-stu-id="0d800-138">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="0d800-139">Tali requisiti, oltre alle informazioni sulla configurazione dei certificati e di Internet Information Services (IIS), vengono illustrati in dettaglio nel sito Web Microsoft Office Web <https://go.microsoft.com/fwlink/p/?linkid=257525>Apps Deployment all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="0d800-139">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0d800-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d800-140">See Also</span></span>


[<span data-ttu-id="0d800-141">Panoramica delle conferenze Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d800-141">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="0d800-142">Elenco di controllo di distribuzione per le conferenze Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d800-142">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

