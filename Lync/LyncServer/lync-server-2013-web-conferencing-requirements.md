---
title: 'Lync Server 2013: requisiti di Web Conferencing'
description: 'Lync Server 2013: requisiti di Web Conferencing.'
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
ms.openlocfilehash: 6c1fce932d3cc02ac29364d53d04ec336693e43b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576392"
---
# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="58913-103">Requisiti di Web Conferencing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58913-103">Web conferencing requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58913-104">_**Ultimo argomento modificato:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="58913-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="58913-105">Se si decide di abilitare le conferenze Web, è necessario pianificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="58913-105">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="58913-106">Accesso all'archivio file utilizzato per l'archiviazione del contenuto delle conferenze Web.</span><span class="sxs-lookup"><span data-stu-id="58913-106">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="58913-107">Integrazione con il server Office Web Apps, che è necessario per condividere i file di PowerPoint durante una conferenza.</span><span class="sxs-lookup"><span data-stu-id="58913-107">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="58913-108">Archivio file</span><span class="sxs-lookup"><span data-stu-id="58913-108">File Store</span></span>

<span data-ttu-id="58913-109">Il servizio Web Conferencing di Lync Server 2013 archivia il contenuto condiviso durante le riunioni nell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="58913-109">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="58913-110">Nell'ambito della distribuzione, è necessario specificare una condivisione file da utilizzare come archivio file per il server Standard Edition o per il pool Enterprise Edition front end.</span><span class="sxs-lookup"><span data-stu-id="58913-110">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="58913-111">È possibile utilizzare una condivisione di file esistente per l'archivio file oppure specificare una nuova condivisione di file indicando il nome di dominio completo (FQDN) del file server in cui deve essere posizionata la condivisione di file, nonché un nome di cartella per la nuova condivisione di file.</span><span class="sxs-lookup"><span data-stu-id="58913-111">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="58913-112">Per ulteriori informazioni, vedere Generatore di topologie – Definire l'archivio file per il pool Front End.</span><span class="sxs-lookup"><span data-stu-id="58913-112">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="58913-113">Il servizio per conferenze Web crittografa il contenuto prima di archiviarlo nell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="58913-113">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="58913-114">Lync Server 2013 supporta l'utilizzo di condivisioni file su una rete di archiviazione diretta (DAS, Direct Attached Storage) o su un sistema di archiviazione (SAN), incluso il file System distribuito (DFS) e un array di dischi indipendenti (RAID) ridondante per gli archivi di file.</span><span class="sxs-lookup"><span data-stu-id="58913-114">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="58913-115">Dopo che la distribuzione guidata di Lync Server ha definito il percorso della condivisione file, Lync Server crea una struttura di cartelle all'interno della condivisione file simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="58913-115">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="58913-116">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="58913-116">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="58913-117">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="58913-117">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="58913-118">1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="58913-118">1-WebServices-1</span></span>
    
      - <span data-ttu-id="58913-119">CollabContent</span><span class="sxs-lookup"><span data-stu-id="58913-119">CollabContent</span></span>
    
      - <span data-ttu-id="58913-120">CollabMetadata</span><span class="sxs-lookup"><span data-stu-id="58913-120">CollabMetadata</span></span>
    
      - <span data-ttu-id="58913-121">Dataconf</span><span class="sxs-lookup"><span data-stu-id="58913-121">DataConf</span></span>

<span data-ttu-id="58913-122">Il servizio di conferenza Web archivia quindi il contenuto, ad esempio diapositive di PowerPoint, lavagne, sondaggi e allegati, nelle cartelle CollabContent e CollabMetadata che si trovano nella cartella WebServices.</span><span class="sxs-lookup"><span data-stu-id="58913-122">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="58913-123">L'amministratore deve impostare le autorizzazioni sulla condivisione file in modo che i gruppi RTC dispongano delle necessarie autorizzazioni di accesso in lettura e scrittura.</span><span class="sxs-lookup"><span data-stu-id="58913-123">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="58913-p103">In caso di problemi con le autorizzazioni, aprire il Generatore di topologie, scaricare e ripubblicare la topologia esistente. Durante la pubblicazione della topologia vengono verificate le autorizzazioni per la condivisione file e vengono reimpostate, se necessario.</span><span class="sxs-lookup"><span data-stu-id="58913-p103">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology. Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="58913-126">È possibile utilizzare le impostazioni seguenti per gestire l'archiviazione del contenuto per una riunione:</span><span class="sxs-lookup"><span data-stu-id="58913-126">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="58913-127">**ContentGracePeriod**, disponibile in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), consente di impostare il tempo di permanenza del contenuto Web Conferencing sul server dopo la fine della riunione.</span><span class="sxs-lookup"><span data-stu-id="58913-127">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="58913-128">**MaxContentStorageMB**, che si trova in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), imposta la quantità massima di spazio di file consentita per l'archiviazione del contenuto durante una singola riunione.</span><span class="sxs-lookup"><span data-stu-id="58913-128">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="58913-129">**MaxUploadFileSizeMb** non limita l'impostazione di caricamento dei file per Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="58913-129">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="58913-130">Il limite di caricamento delle dimensioni dei file per Lync Web App è impostato su approssimativamente 30MB ed è controllato dal file di web.config di IIS:/DataCollabWeb/Int \[ ext \] /handler/web.config. Per configurare il limite di caricamento delle dimensioni dei file per Lync Web App, aggiornarlo `maxRequestLength` e `maxAllowedContentLength` nel file web.config come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="58913-130">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

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

<span data-ttu-id="58913-131">È necessario aggiornare il file di web.config per ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="58913-131">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="58913-132">server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="58913-132">Office Web Apps Server</span></span>

<span data-ttu-id="58913-133">Per poter utilizzare questi nuovi amministratori delle funzionalità, è necessario installare il server Office Web Apps e configurare Lync Server 2013 per la comunicazione con il server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="58913-133">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="58913-134">In questa documentazione vengono fornite informazioni su come configurare Lync Server 2013 per l'utilizzo con il server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="58913-134">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="58913-135">La documentazione non fornita contiene informazioni su come installare il server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="58913-135">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="58913-136">Per informazioni dettagliate sull'installazione, vedere il sito Web Microsoft Office Web Apps Deployment all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="58913-136">For installation details, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="58913-137">Tale guida include informazioni complete sui prerequisiti per il server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="58913-137">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="58913-138">Si noti che il server Office Web Apps deve essere installato in un computer autonomo che non esegue Lync Server, SQL Server o qualsiasi altra applicazione server.</span><span class="sxs-lookup"><span data-stu-id="58913-138">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="58913-139">Non è necessario disporre di una versione di Office installata nel computer in questione. Qualsiasi computer utilizzato per eseguire il server Office Web Apps deve disporre anche di un insieme specifico di software installato (inclusi .NET Framework 4,5 e Windows PowerShell 3,0).</span><span class="sxs-lookup"><span data-stu-id="58913-139">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="58913-140">Tali requisiti, oltre alle informazioni sulla configurazione dei certificati e di Internet Information Services (IIS), vengono illustrati in dettaglio nel sito Web Microsoft Office Web Apps Deployment all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="58913-140">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="58913-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58913-141">See Also</span></span>


[<span data-ttu-id="58913-142">Panoramica delle conferenze Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58913-142">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="58913-143">Elenco di controllo di distribuzione per le conferenze Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58913-143">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

