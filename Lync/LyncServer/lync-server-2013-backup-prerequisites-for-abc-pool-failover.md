---
title: 'Lync Server 2013: prerequisiti di backup per il failover del pool ABC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7cdb228b0a748c830aa488e7b058bf8664360d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Prerequisiti di backup per il failover del pool ABC in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-26_

Per ottenere il massimo vantaggio dall'uso della procedura di failover del pool ABC, è necessario eseguire alcuni backup prima che si verifichino le calamità e il failover:

  - È necessario eseguire regolarmente il backup dei dati di configurazione LIS (Location Information Service) dal pool A usando il cmdlet **Export-CsLISConfiguration** .
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - È necessario eseguire regolarmente il backup dei dati di configurazione del gruppo di risposte nel pool A usando il cmdlet **Export-CsRgsConfiguration** .
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    In generale, ti consigliamo di eseguire backup giornalieri, ma se hai un volume elevato di modifiche, potresti voler pianificare backup più frequenti. La quantità di informazioni che è possibile perdere in caso di emergenza dipende dalla frequenza dei backup, nonché dalla frequenza e dal volume delle modifiche.
    
    L'applicazione Response Group può archiviare solo un set di impostazioni a livello di applicazione per ogni pool. È possibile accedere a queste impostazioni tramite i cmdlet **Get-CsRgsConfiguration** . Le impostazioni includono la configurazione predefinita per la musica in blocco, il file audio predefinito per la musica in attesa, il periodo di tolleranza per la chiamata dell'agente e la configurazione del contesto delle chiamate. Queste impostazioni possono essere trasferite da un pool a un altro tramite il cmdlet **Import-CsRgsConfiguration** usando il parametro **ReplaceExistingSettings** , ma questa operazione eseguirà l'override di tutte le impostazioni a livello di applicazione nel pool di destinazione.
    
    <div>
    

    > [!TIP]  
    > In un percorso distinto mantenere una copia di backup di tutti i file audio originali usati per configurare l'applicazione Response Group, ovvero eventuali registrazioni o file musicali in blocco.

    
    </div>
    
    Se sono presenti file personalizzati per la musica in attesa caricati per il parcheggio delle chiamate in un pool, è consigliabile conservarne una copia in un'altra posizione. Non è possibile eseguire il backup di questi file come parte del processo di ripristino di emergenza di Lync Server 2013 e andranno perduti se i file caricati nel pool sono danneggiati, danneggiati o eliminati.
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > L'applicazione per il parcheggio delle chiamate può archiviare solo un set di impostazioni e un file audio in blocco musicale personalizzato per ogni pool. È possibile accedere a queste impostazioni tramite il cmdlet <STRONG>Get-CsCpsConfiguration</STRONG> . Poiché il meccanismo di ripristino di emergenza per il parcheggio delle chiamate si basa sull'applicazione Call Park del pool di backup, le impostazioni del pool principale non vengono supportate o mantenute se si verifica un disastro. Se il pool principale viene perso, queste impostazioni non possono essere recuperate e quando viene distribuito un nuovo pool per sostituire il pool principale, le impostazioni del parcheggio delle chiamate e qualsiasi file audio personalizzato per la musica in attesa devono essere riconfigurati.

    
    </div>

  - Se si configurano gli annunci come parte della caratteristica voce numero non assegnati, è consigliabile conservare in un'altra posizione una copia di un file audio originale usato durante la configurazione iniziale. In caso contrario, è possibile ottenere una copia dei file audio configurati nell'archivio file del server o del pool in cui sono stati importati i file audio. Non è possibile eseguire il backup di questi file come parte del processo di ripristino di emergenza di Lync Server 2013 e andranno perduti se i file caricati nel pool sono danneggiati, danneggiati o eliminati. Per copiare tutti i file audio usati per configurare la caratteristica vocale numero non assegnato dall'archivio file di un server o di un pool, usare:
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - Se si hanno il monitoraggio e l'archiviazione di database in un pool, è consigliabile usare gli strumenti di gestione di SQL Server per eseguirne il backup. Nella procedura di failover ABC i database di monitoraggio e archiviazione non vengono mantenuti se installati nel pool A, perché non è possibile eseguire il backup di questi database tramite il servizio di backup di Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

