---
title: 'Lync Server 2013: installazione del database mediante Lync Server Management Shell'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d46d3bc2ce881edc183e4996c0c71d6a90af4e6a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>Installazione di database mediante Lync Server Management Shell in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-06-16_

La separazione dei ruoli e delle responsabilità tra gli amministratori dei server e gli amministrazione di SQL Server può causare ritardi nell'implementazione. Lync Server 2013 utilizza il controllo di accesso basato sui ruoli (RBAC) per attenuare tali difficoltà. In alcuni casi, l'amministratore di SQL Server deve gestire l'installazione dei database nel server basato su SQL Server al di fuori del controllo dell'accesso basato sui ruoli. Lync Server 2013 Management Shell consente all'amministratore di SQL Server di eseguire i cmdlet di Windows PowerShell studiati per configurare i database con i dati e i file di registro corretti. Per informazioni dettagliate, vedere [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

<div class=" ">


> [!IMPORTANT]  
> La procedura seguente presuppone che sia installato almeno il Lync Server 2013 OCSCore. msi, SQL Server Native Client (sqlncli. msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 e Microsoft SQL Server 2012 ADOMD.NET. OCSCore.msi si trova sul supporto di installazione nella directory \Setup\AMD64\Setup. I componenti restanti si trovano in \Setup\amd64. Inoltre, la preparazione di Active Directory per Lync Server 2013 è stata completata correttamente.



</div>

**Install-CsDatabase** è il cmdlet di Windows PowerShell utilizzato per installare i database. Il cmdlet di **Install-CsDatabase** include un numero elevato di parametri, solo alcuni dei quali verranno descritti in questa sezione. Per informazioni dettagliate sui possibili parametri, vedere la documentazione di Lync Server 2013 Management Shell.

<div class=" ">


> [!WARNING]  
> Per evitare le prestazioni e i possibili problemi di timeout, utilizzare sempre nomi di dominio completi (FQDN) quando si fa riferimento a server basati su SQL Server. Evitare di utilizzare riferimenti solo nome host. Ad esempio, utilizzare sqlbe01.contoso.net, ma evitare di utilizzare SQLBE01.



</div>

Per l'installazione dei database, **Install-CsDatabase** utilizza tre metodi principali per inserire i database nel server basato su SQL Server preparato:

  - Eseguire **Install-CsDatabase** senza DatabasePaths o UseDefaultSqlPath. Il cmdlet utilizza un algoritmo predefinito per determinare la posizione migliore per i file di registro e di dati. L'algoritmo può essere utilizzato solo per le implementazioni di SQL Server autonome.

  - Eseguire **Install-CsDatabase** con il parametro DatabasePaths. Se il parametro DatabasePaths è definito, viene utilizzato l'algoritmo predefinito per ottimizzare i percorsi dei file di registro e di dati. Se si utilizza questo parametro, è possibile definire le posizioni in cui verranno distribuiti i file di log e di dati.

  - Eseguire **Install-CsDatabase** con UseDefaultSqlPaths. Questa opzione non utilizza l'algoritmo predefinito per ottimizzare le posizioni dei file di registro e di dati. Tali file vengono distribuiti in base ai valori predefiniti impostati dall'amministratore di SQL Server. Questi percorsi vengono in genere impostati per l'amministrazione automatica dei file di dati e di registro in SQL Server in anticipo e non sono associati al programma di installazione di Lync Server 2013.

  - È inoltre possibile utilizzare il parametro DatabasePathMap per specificare in modo esplicito un percorso per ogni database e il rispettivo file di registro.

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>Per utilizzare i cmdlet di Windows PowerShell per configurare l'archivio di gestione centrale di SQL Server

1.  Su un computer qualsiasi accedere con le credenziali amministrative per la creazione dei database sul server basato su SQL Server. Per informazioni dettagliate, vedere [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

2.  Aprire Lync Server 2013 Management Shell. Se non sono stati regolati i criteri di esecuzione per Windows PowerShell, è necessario modificare il criterio per consentire l'esecuzione degli script di Windows PowerShell. Per informazioni dettagliate, vedere "esame del criterio di esecuzione" [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)all'indirizzo.

3.  Utilizzare il cmdlet **Install-CsDatabase** per installare l'archivio di gestione centrale.
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > Il parametro Report è facoltativo ma è utile per documentare il processo di installazione.

    
    </div>

4.  **Install-CsDatabase – DatabasePaths** è in grado di utilizzare un massimo di sei parametri di percorso, ognuno dei quali definisce i percorsi delle unità, come definito in SQL Server Data and log file Placement. In base alle regole logiche della configurazione del database in Lync Server 2013, le unità vengono analizzate in bucket di due, quattro o sei. A seconda della configurazione di SQL Server e del numero di bucket, verranno forniti due percorsi, quattro percorsi o sei percorsi.
    
    Se si dispone di tre unità, il registro ha la priorità e i file di dati vengono distribuiti successivamente. Un esempio di un server basato su SQL Server configurato con sei unità:
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  Al termine dell'installazione del database, è possibile chiudere Lync Server 2013 Management Shell oppure passare all'installazione dei database configurati di Lync Server 2013 definiti in Generatore di topologie.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>Per utilizzare i cmdlet di Windows PowerShell per impostare i database configurati nella topologia di SQL Server

1.  Per installare i database configurati da generatore di topologie per Lync Server 2013, l'amministratore di Lync Server 2013 deve pubblicare la topologia. Per ulteriori informazioni, vedere [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md) nella documentazione relativa alla distribuzione.

2.  Su un computer qualsiasi collegarsi con le credenziali amministrative per la creazione dei database sul server basato su SQL Server. Per ulteriori informazioni, vedere l'argomento [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Per poter configurare i database basati su SQL Server, assicurarsi che l'account di amministratore di SQL Server utilizzato per eseguire la procedura descritta di seguito sia anche un membro del gruppo sysadmins (o equivalente) sul server che esegue SQL Server e che detenga la gestione centralizzata. Ruolo del server. Questo è particolarmente importante per controllare eventuali pool di Lync Server 2013 aggiuntivi che richiedono l'installazione o la configurazione del database di SQL Server. Ad esempio, se si sta distribuendo un secondo pool (pool02), ma il ruolo del server di gestione centrale è mantenuto da pool01. Il gruppo sysadmin di SQL Server (o equivalente) deve disporre delle autorizzazioni per entrambi i database basati su SQL Server.

    
    </div>

3.  Aprire Lync Server 2013 Management Shell, se non è già aperto.

4.  Utilizzare il cmdlet **Install-CsDatabase** per installare i database configurati per il generatore di topologie.
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > Il parametro Report è facoltativo ma è utile per documentare il processo di installazione.

    
    </div>

5.  Al termine dell'installazione del database, chiudere Lync Server 2013 Management Shell.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>Per utilizzare i cmdlet di Windows PowerShell per configurare la topologia di SQL Server tramite il parametro DatabasePathMap

1.  Per installare i database per Lync Server 2013, è necessario che l'amministratore di Lync Server crei i percorsi e distribuisca i file dei database e i file di registro in base a un set di regole predefinito.

2.  Su un computer qualsiasi collegarsi con le credenziali amministrative per la creazione dei database sul server basato su SQL Server. Per ulteriori informazioni, vedere l'argomento [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Per poter configurare i database basati su SQL Server, assicurarsi che l'account di amministratore di SQL Server utilizzato per eseguire la procedura descritta di seguito sia anche un membro del gruppo sysadmins (o equivalente) sul server che esegue SQL Server e che detenga la gestione centralizzata. Ruolo del server. Questo è particolarmente importante per controllare eventuali pool di Lync Server aggiuntivi che richiedono l'installazione o la configurazione del database di SQL Server. Ad esempio, se si sta distribuendo un secondo pool (pool02), ma il ruolo del server di gestione centrale è mantenuto da pool01. Il gruppo sysadmin di SQL Server (o equivalente) deve disporre delle autorizzazioni per entrambi i database basati su SQL Server.

    
    </div>

3.  Aprire Lync Server Management Shell, se non è già aperto.

4.  Utilizzare il cmdlet **Install-CsDatabase** con il parametro DatabasePathMap e una tabella hash di PowerShell per installare i database configurati per il generatore di topologie.

5.  Nel codice di esempio, i percorsi definiti per i database possono essere determinati in modo granulare utilizzando il parametro – DatabasePathMap e una tabella hash definita come indicato di seguito (nell'esempio viene utilizzato "\\c: CSData" per tutti i file di database (con estensione MDF)\\e "c: CSLogFiles" per tutti i file di registro (con estensione ldf). La cartella verrà creata secondo le esigenze di Install-CsDatabase):
    ```powershell
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
    "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
    "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
    }
    Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
6.  Poiché il database e i file di registro sono denominati in modo esplicito con la posizione sul server di database di destinazione, è possibile definire percorsi specifici per il database e il percorso del registro effettivi di ogni tipo di servizio. Nell'esempio seguente vengono attivati i database per ogni tipo di servizio specifico su dischi separati e i file di registro associati su un altro. Ad esempio:
    
      - Tutti i database RTC su "D\\: RTCDatabase"
    
      - Tutti i file di registro RTC su "\\E: RTCLogs"
    
      - Tutti i database dell'archivio applicazioni su "\\F: CPSDatabases"
    
      - Tutti i registri dell'archivio applicazioni in "\\G: CPSLogs"
    
      - Tutti i database dell'archivio di Response Group su\\"H: RGSDatabases"
    
      - Tutti i registri dell'archivio di Response Group su\\"I: RGSLogs"
    
      - Tutti i database dell'archivio delle rubriche su "\\J: ABSDatabases"
    
      - Tutti i file di registro dell'archivio delle rubriche su\\"K: ABSLogs"
    
      - Tutti i database dell'archivio di archiviazione su "\\L: ArchivingDatabases"
    
      - Tutti i registri dell'archivio di archiviazione su "\\M: ArchivingLogs"
    
      - Tutti i database dell'archivio di monitoraggio su\\"N: MonitoringDatabases"
    
      - Tutti i file di registro dell'archivio di monitoraggio\\in "O: MonitoringLogfiles"
    
    <!-- end list -->
    
    ```powershell    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    Se si utilizza il parametro – DatabasePathMap, è possibile definire qualsiasi combinazione di mapping lettera di unità logica che fornisce la soluzione migliore per i requisiti di posizionamento e prestazioni di SQL Server.

Se si configurano i file di dati e i file di registro del database utilizzando il metodo **DatabasePathMap** , sarà necessario apportare una leggera modifica al processo normale quando si utilizza il generatore di topologie. In genere, è necessario definire le scelte di topologia, pubblicare la topologia e scegliere di distribuire le selezioni di database.

Se è stato utilizzato **DatabasePathMap** , è già stata eseguita la terza parte del processo di generatore di topologie. Nel caso di un server di database completamente configurato prima dell'esecuzione del generatore di topologie, è comunque necessario definire tutti i ruoli e le opzioni del server, ma deselezionare l'opzione per la creazione dei database.

</div>

</div>

<span> </span>

</div>

</div>

</div>

