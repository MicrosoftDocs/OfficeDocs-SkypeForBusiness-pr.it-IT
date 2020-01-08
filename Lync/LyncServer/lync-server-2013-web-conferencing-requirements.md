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

# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Requisiti per i servizi di conferenza Web in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-30_

Se si è scelto di abilitare i servizi di conferenza Web, è necessario pianificare le operazioni seguenti:

  - <span></span>  
    Accedere all'archivio file, che viene usato per archiviare il contenuto delle conferenze Web.

  - <span></span>  
    Integrazione con Office Web Apps Server, che è necessario per condividere i file di PowerPoint durante una conferenza.

<div>

## <a name="file-store"></a>Archivio file

Il servizio di conferenza Web Lync Server 2013 archivia il contenuto condiviso durante le riunioni nell'archivio file. Come parte della distribuzione, è necessario specificare una condivisione file da usare come archivio file per il pool di server standard o Enterprise Edition front-end. È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file, oltre a un nome di cartella per la nuova condivisione file.Per altre informazioni, vedere Generatore di topologie: definire l'archivio di file per il front-end. Il servizio Web Conferencing crittografa il contenuto prima di archiviare il contenuto nell'archivio file.

Lync Server 2013 supporta l'uso di condivisioni file in un ambiente di archiviazione Direct Attached (DAS) o in una rete di archiviazione (SAN), incluso il file System distribuito (DFS) e in una matrice ridondante di dischi indipendenti (RAID) per archivi di file. Dopo che la distribuzione guidata di Lync Server ha definito la posizione della condivisione file, Lync Server crea una struttura di cartelle all'interno della condivisione file simile a:

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - Dataconf

Il servizio Web Conferencing consente quindi di archiviare contenuti come diapositive di PowerPoint, lavagne, sondaggi e allegati nelle cartelle CollabContent e CollabMetadata, che si trovano nella cartella WebServices.

L'amministratore deve impostare le autorizzazioni per la condivisione di file in modo che i gruppi RTC dispongano dell'accesso di lettura e scrittura necessario.

<div>


> [!WARNING]  
> Se si verificano errori con le autorizzazioni, aprire Generatore di topologie, scaricare e ripubblicare la topologia esistente. La pubblicazione della topologia verificherà le autorizzazioni di condivisione file e reimpostarle, se necessario.



</div>

Per gestire la modalità di archiviazione del contenuto per una riunione, è possibile usare le impostazioni seguenti:

  - **ContentGracePeriod**, che si trova in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), imposta il periodo di tempo in cui il contenuto delle conferenze Web rimarrà sul server al termine della riunione.

  - **MaxContentStorageMB**, che si trova in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), imposta la quantità massima di spazio su file consentita per l'archiviazione del contenuto durante una singola riunione.

**MaxUploadFileSizeMb** non limita l'impostazione di caricamento dei file per Lync Web App. Il limite di caricamento delle dimensioni dei file per Lync Web App è impostato su circa 30MB e viene controllato dal file Web. config di\[IIS\]:/DataCollabWeb/int ext/handler/Web.config. Per configurare il limite di caricamento delle dimensioni dei file per Lync Web `maxRequestLength` app `maxAllowedContentLength` , aggiornare e nel file Web. config come illustrato di seguito.

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

È necessario aggiornare il file Web. config per ogni server front-end.

</div>

<div>

## <a name="office-web-apps-server"></a>Server Office Web Apps

Per usare questi nuovi amministratori delle funzionalità, è necessario installare Office Web Apps Server e configurare Lync Server 2013 per la comunicazione con Office Web Apps Server. Questa documentazione contiene informazioni su come configurare Lync Server 2013 per l'utilizzo con Office Web Apps Server. La documentazione in questione non è disponibile per informazioni su come installare Office Web Apps Server. Per informazioni dettagliate sull'installazione, vedere il sito Web Microsoft Office Web <http://go.microsoft.com/fwlink/p/?linkid=257525>Apps Deployment. Questa guida include informazioni complete sui prerequisiti per Office Web Apps Server. Tieni presente che il server Office Web Apps deve essere installato in un computer autonomo che non è in grado di eseguire Lync Server, SQL Server o qualsiasi altra applicazione server. Non è necessario che nel computer sia installata una versione di Office. Qualsiasi computer usato per eseguire Office Web Apps Server deve avere anche un set di software specifico installato (inclusi .NET Framework 4,5 e Windows PowerShell 3,0). Questi requisiti, oltre a informazioni sulla configurazione di certificati e Internet Information Services (IIS), vengono descritti in dettaglio nel sito Web Microsoft Office Web Apps Deployment <http://go.microsoft.com/fwlink/p/?linkid=257525>.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Panoramica delle conferenze Web in Lync Server 2013](lync-server-2013-web-conferencing-overview.md)  
[Elenco di controllo della distribuzione per i servizi di conferenza Web in Lync Server 2013](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

