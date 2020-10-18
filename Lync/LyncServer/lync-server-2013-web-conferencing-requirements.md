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
# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Requisiti di Web Conferencing in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-30_

Se si decide di abilitare le conferenze Web, è necessario pianificare quanto segue:

  - <span></span>  
    Accesso all'archivio file utilizzato per l'archiviazione del contenuto delle conferenze Web.

  - <span></span>  
    Integrazione con il server Office Web Apps, che è necessario per condividere i file di PowerPoint durante una conferenza.

<div>

## <a name="file-store"></a>Archivio file

Il servizio Web Conferencing di Lync Server 2013 archivia il contenuto condiviso durante le riunioni nell'archivio file. Nell'ambito della distribuzione, è necessario specificare una condivisione file da utilizzare come archivio file per il server Standard Edition o per il pool Enterprise Edition front end. È possibile utilizzare una condivisione di file esistente per l'archivio file oppure specificare una nuova condivisione di file indicando il nome di dominio completo (FQDN) del file server in cui deve essere posizionata la condivisione di file, nonché un nome di cartella per la nuova condivisione di file.Per ulteriori informazioni, vedere Generatore di topologie – Definire l'archivio file per il pool Front End. Il servizio per conferenze Web crittografa il contenuto prima di archiviarlo nell'archivio file.

Lync Server 2013 supporta l'utilizzo di condivisioni file su una rete di archiviazione diretta (DAS, Direct Attached Storage) o su un sistema di archiviazione (SAN), incluso il file System distribuito (DFS) e un array di dischi indipendenti (RAID) ridondante per gli archivi di file. Dopo che la distribuzione guidata di Lync Server ha definito il percorso della condivisione file, Lync Server crea una struttura di cartelle all'interno della condivisione file simile alla seguente:

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - Dataconf

Il servizio di conferenza Web archivia quindi il contenuto, ad esempio diapositive di PowerPoint, lavagne, sondaggi e allegati, nelle cartelle CollabContent e CollabMetadata che si trovano nella cartella WebServices.

L'amministratore deve impostare le autorizzazioni sulla condivisione file in modo che i gruppi RTC dispongano delle necessarie autorizzazioni di accesso in lettura e scrittura.

<div>


> [!WARNING]  
> In caso di problemi con le autorizzazioni, aprire il Generatore di topologie, scaricare e ripubblicare la topologia esistente. Durante la pubblicazione della topologia vengono verificate le autorizzazioni per la condivisione file e vengono reimpostate, se necessario.



</div>

È possibile utilizzare le impostazioni seguenti per gestire l'archiviazione del contenuto per una riunione:

  - **ContentGracePeriod**, disponibile in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), consente di impostare il tempo di permanenza del contenuto Web Conferencing sul server dopo la fine della riunione.

  - **MaxContentStorageMB**, che si trova in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), imposta la quantità massima di spazio di file consentita per l'archiviazione del contenuto durante una singola riunione.

**MaxUploadFileSizeMb** non limita l'impostazione di caricamento dei file per Lync Web App. Il limite di caricamento delle dimensioni dei file per Lync Web App è impostato su approssimativamente 30MB ed è controllato dal file di web.config di IIS:/DataCollabWeb/Int \[ ext \] /handler/web.config. Per configurare il limite di caricamento delle dimensioni dei file per Lync Web App, aggiornarlo `maxRequestLength` e `maxAllowedContentLength` nel file web.config come illustrato di seguito.

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

È necessario aggiornare il file di web.config per ogni Front End Server.

</div>

<div>

## <a name="office-web-apps-server"></a>server Office Web Apps

Per poter utilizzare questi nuovi amministratori delle funzionalità, è necessario installare il server Office Web Apps e configurare Lync Server 2013 per la comunicazione con il server Office Web Apps. In questa documentazione vengono fornite informazioni su come configurare Lync Server 2013 per l'utilizzo con il server Office Web Apps. La documentazione non fornita contiene informazioni su come installare il server Office Web Apps. Per informazioni dettagliate sull'installazione, vedere il sito Web Microsoft Office Web Apps Deployment all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=257525> . Tale guida include informazioni complete sui prerequisiti per il server Office Web Apps. Si noti che il server Office Web Apps deve essere installato in un computer autonomo che non esegue Lync Server, SQL Server o qualsiasi altra applicazione server. Non è necessario disporre di una versione di Office installata nel computer in questione. Qualsiasi computer utilizzato per eseguire il server Office Web Apps deve disporre anche di un insieme specifico di software installato (inclusi .NET Framework 4,5 e Windows PowerShell 3,0). Tali requisiti, oltre alle informazioni sulla configurazione dei certificati e di Internet Information Services (IIS), vengono illustrati in dettaglio nel sito Web Microsoft Office Web Apps Deployment all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=257525> .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Panoramica delle conferenze Web in Lync Server 2013](lync-server-2013-web-conferencing-overview.md)  
[Elenco di controllo di distribuzione per le conferenze Web in Lync Server 2013](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

