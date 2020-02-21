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

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Prerequisiti di backup per il failover del pool ABC in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-26_

Per ottenere il massimo vantaggio dall'utilizzo della procedura di failover del pool ABC, è necessario eseguire alcuni backup prima che si verifichino le operazioni di emergenza e failover:

  - È necessario eseguire regolarmente il backup dei dati di configurazione LIS (Location Information Service) dal pool A utilizzando il cmdlet **Export-CsLISConfiguration** .
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - È necessario eseguire regolarmente il backup dei dati di configurazione di Response Group nel pool A utilizzando il cmdlet **Export-CsRgsConfiguration** .
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    In generale, è consigliabile eseguire backup giornalieri, ma in presenza di un volume elevato di modifiche è possibile pianificare backup più frequenti. La quantità di informazioni che possono essere perse in caso di emergenza dipende dalla frequenza dei backup, nonché dalla frequenza e dal volume delle modifiche.
    
    L'applicazione Response Group è in grado di archiviare solo un set di impostazioni a livello di applicazione per ogni pool. È possibile accedere a queste impostazioni tramite i cmdlet **Get-CsRgsConfiguration** . Le impostazioni includono la configurazione predefinita per la musica in attesa, il file audio predefinito per la musica in attesa, il periodo di tolleranza Ring-back dell'agente e la configurazione del contesto di chiamata. Queste impostazioni possono essere trasferite da un pool all'altro tramite il cmdlet **Import-CsRgsConfiguration** utilizzando il parametro **ReplaceExistingSettings** , ma questa operazione sostituirà tutte le impostazioni a livello di applicazione nel pool di destinazione.
    
    <div>
    

    > [!TIP]  
    > In un percorso separato, conservare una copia di backup di tutti i file audio originali che sono stati utilizzati per configurare l'applicazione Response Group, ovvero eventuali registrazioni o file musicali in attesa.

    
    </div>
    
    Se si dispone di file musicali personalizzati che sono stati caricati per il parcheggio di chiamata in un pool, è consigliabile conservarne una copia in un'altra posizione. Questi file non vengono sottoposti a backup come parte del processo di ripristino di emergenza di Lync Server 2013 e verranno persi se i file caricati nel pool sono danneggiati, danneggiati o eliminati.
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > L'applicazione Parcheggio di chiamata può archiviare un solo set di impostazioni e un file audio personalizzato per il pool. È possibile accedere a queste impostazioni tramite il cmdlet <STRONG>Get-CsCpsConfiguration</STRONG> . Poiché il meccanismo di ripristino di emergenza per il parcheggio di chiamata si basa sull'applicazione Parcheggio di chiamata del pool di backup, le impostazioni del pool primario non vengono sottoposte a backup o conservate se si verifica un evento di emergenza. Se il pool primario è perduto, queste impostazioni non possono essere ripristinate e quando viene distribuito un nuovo pool per sostituire il pool primario, è necessario riconfigurare le impostazioni del parcheggio di chiamata e qualsiasi file audio di musica in attesa personalizzato.

    
    </div>

  - Se si configurano annunci come parte della funzionalità per i numeri non assegnati, è consigliabile mantenere in un'altra posizione una copia di qualsiasi file audio originale utilizzato durante la configurazione iniziale. In caso contrario, è possibile ottenere una copia dei file audio configurati nell'archivio file del server o del pool in cui sono stati importati i file audio. Questi file non vengono sottoposti a backup come parte del processo di ripristino di emergenza di Lync Server 2013 e verranno persi se i file caricati nel pool sono danneggiati, danneggiati o eliminati. Per copiare tutti i file audio utilizzati per configurare la funzionalità vocale numeri non assegnati dall'archivio file di un server o di un pool, utilizzare:
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - Se si dispone di database di monitoraggio e archiviazione in un pool, è consigliabile utilizzare gli strumenti di gestione di SQL Server per eseguirne il backup. Nella procedura di failover ABC, i database di monitoraggio e archiviazione non vengono conservati se sono collocati nel pool A, perché non è stato eseguito il backup di questi database tramite il servizio di backup di Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

