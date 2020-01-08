---
title: 'Lync Server 2013: Installazione di database mediante Lync Server Management Shell'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: deac68fb5f20066632bc48a9e9b6244a9bd34fe9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40979619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>Installazione di database mediante Lync Server Management Shell in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-06-16_

La separazione dei ruoli e delle responsabilità tra gli amministratori del server e gli amministratori di SQL Server può causare ritardi nell'implementazione. Lync Server 2013 usa il controllo di accesso basato sui ruoli (RBAC) per attenuare queste difficoltà. In alcuni casi, l'amministratore di SQL Server deve gestire l'installazione di database nel server basato su SQL Server all'esterno di RBAC. Lync Server 2013 Management Shell consente all'amministratore di SQL Server di eseguire i cmdlet di Windows PowerShell progettati per configurare i database con i dati e i file di log corretti. Per informazioni dettagliate, vedere [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

<div class=" ">


> [!IMPORTANT]  
> La procedura seguente presuppone che almeno gli oggetti di gestione di Lync Server 2013 OCSCore. msi, SQL Server Native Client (sqlncli. msi) Microsoft SQL Server 2012, i tipi CLR per Microsoft SQL Server 2012 e Microsoft SQL Server 2012 ADOMD.NET siano installati. Il file OCSCore. msi si trova nel supporto di installazione nella directory \Setup\AMD64\Setup. I componenti rimanenti si trovano in \Setup\amd64. Inoltre, la preparazione di Active Directory per Lync Server 2013 è stata completata correttamente.



</div>

**Install-CsDatabase** è il cmdlet di Windows PowerShell usato per installare i database. Il cmdlet **Install-CsDatabase** ha un numero elevato di parametri, solo alcuni dei quali sono discussi qui. Per informazioni dettagliate sui possibili parametri, vedere la documentazione di Lync Server 2013 Management Shell.

<div class=" ">


> [!WARNING]  
> Per evitare le prestazioni e i possibili problemi di timeout, USA sempre nomi di dominio completi (FQDN) quando si fa riferimento a server basati su SQL Server. Evitare di usare i riferimenti solo al nome host. Ad esempio, USA sqlbe01.contoso.net, ma evita di usare SQLBE01.



</div>

Per l'installazione di database, **Install-CsDatabase** usa tre metodi principali per posizionare i database nel server basato su SQL Server preparato:

  - Eseguire **Install-CsDatabase** senza DatabasePaths o UseDefaultSqlPath. Il cmdlet usa un algoritmo incorporato per determinare la posizione ottimale per i file di log e di dati. L'algoritmo funziona solo per le implementazioni di SQL Server autonome.

  - Eseguire **Install-CsDatabase** con il parametro DatabasePaths. L'algoritmo predefinito per ottimizzare le posizioni di log e file di dati non viene usato se il parametro DatabasePaths è definito. L'uso di questo parametro consente di definire le posizioni in cui verranno distribuiti i file di log e di dati.

  - Eseguire **Install-CsDatabase** con UseDefaultSqlPaths. Questa opzione non usa l'algoritmo predefinito per ottimizzare il log e i percorsi dei file di dati. I file di log e di dati vengono distribuiti in base alle impostazioni predefinite impostate dall'amministratore di SQL Server. Questi percorsi sono in genere impostati per l'amministrazione automatica dei file di log e di dati in SQL Server in anticipo e non sono associati alla configurazione di Lync Server 2013.

  - Il parametro DatabasePathMap può essere usato anche per specificare in modo esplicito una posizione per ogni database e il rispettivo file di log.

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>Per usare i cmdlet di Windows PowerShell per configurare SQL Server Central Management store

1.  In qualsiasi computer accedere con le credenziali amministrative per creare i database nel server basato su SQL Server. Per informazioni dettagliate, vedere [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

2.  Aprire Lync Server 2013 Management Shell. Se il criterio di esecuzione non è stato regolato per Windows PowerShell, è necessario modificare i criteri per consentire l'esecuzione degli script di Windows PowerShell. Per informazioni dettagliate, vedere "esaminare il criterio di [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)esecuzione".

3.  Usare il cmdlet **Install-CsDatabase** per installare Central Management store.
    
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
    > Il parametro report è facoltativo, ma è utile se si sta documentando il processo di installazione.

    
    </div>

4.  **Install-CsDatabase-DatabasePaths** può usare un massimo di sei parametri di percorso, ognuno dei quali definisce i percorsi per le unità come definito nei dati di SQL Server e nella posizione del file di log. In base alle regole logiche della configurazione del database in Lync Server 2013, le unità vengono analizzate in bucket di due, quattro o sei. In base alla configurazione di SQL Server e al numero di contenitori, verranno forniti due percorsi, quattro percorsi o sei percorsi.
    
    Se si hanno tre unità, il log diventa prioritario e i file di dati vengono distribuiti dopo. Esempio di server basato su SQL Server configurato con sei unità:
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  Al termine dell'installazione del database, è possibile chiudere Lync Server 2013 Management Shell oppure procedere con l'installazione dei database configurati da Lync Server 2013 definiti in Generatore di topologie.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>Per usare i cmdlet di Windows PowerShell per configurare i database di topologia di SQL Server configurati

1.  Per installare i database configurati da generatore di topologia per Lync Server 2013, l'amministratore di Lync Server 2013 deve pubblicare la topologia. Per informazioni dettagliate, vedere [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md) nella documentazione relativa alla distribuzione.

2.  In qualsiasi computer accedere con le credenziali amministrative per creare i database nel server basato su SQL Server. Vedere l'argomento [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Per poter configurare i database basati su SQL Server, verificare che l'account di amministratore di SQL Server usato per eseguire la procedura descritta in questo articolo sia anche un membro del gruppo sysadmin (o equivalente) nel server che esegue SQL Server e che detiene la gestione centralizzata Ruolo del server. Questa operazione è particolarmente importante per verificare se sono presenti altri pool di Lync Server 2013 che richiedono l'installazione o la configurazione di database di SQL Server. Ad esempio, se si sta distribuendo un secondo pool (pool02), ma il ruolo del server di gestione centrale è mantenuto da pool01. Il gruppo sysadmin di SQL Server (o equivalente) deve disporre delle autorizzazioni per entrambi i database basati su SQL Server.

    
    </div>

3.  Aprire Lync Server 2013 Management Shell, se non è già aperto.

4.  Usare il cmdlet **Install-CsDatabase** per installare i database configurati da generatore di topologia.
    
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
    > Il parametro report è facoltativo, ma è utile se si sta documentando il processo di installazione.

    
    </div>

5.  Al termine dell'installazione del database, chiudere Lync Server 2013 Management Shell.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>Per usare i cmdlet di Windows PowerShell per configurare la topologia di SQL Server tramite il parametro DatabasePathMap

1.  Per installare database per Lync Server 2013, l'amministratore di Lync Server deve creare i percorsi e distribuire i file di database e i file di log in base a un set di regole predefinito.

2.  In qualsiasi computer accedere con le credenziali amministrative per creare i database nel server basato su SQL Server. Vedere l'argomento [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Per poter configurare i database basati su SQL Server, verificare che l'account di amministratore di SQL Server usato per eseguire la procedura descritta in questo articolo sia anche un membro del gruppo sysadmin (o equivalente) nel server che esegue SQL Server e che detiene la gestione centralizzata Ruolo del server. Questa operazione è particolarmente importante per verificare la necessità di eventuali pool di Lync Server aggiuntivi che richiedono l'installazione o la configurazione di database di SQL Server. Ad esempio, se si sta distribuendo un secondo pool (pool02), ma il ruolo del server di gestione centrale è mantenuto da pool01. Il gruppo sysadmin di SQL Server (o equivalente) deve disporre delle autorizzazioni per entrambi i database basati su SQL Server.

    
    </div>

3.  Aprire Lync Server Management Shell, se non è già aperto.

4.  Usa il cmdlet **Install-CsDatabase** con il parametro DatabasePathMap e una tabella hash di PowerShell per installare i database configurati da generatore di topologia.

5.  Nel codice di esempio i percorsi definiti per i database possono essere determinati in modo granulare usando il parametro – DatabasePathMap e una tabella hash definita come indicato di seguito (nell'esempio viene usato "C\\: CSData" per tutti i file di database (MDF) e "c\\: CSLogFiles" per tutti i file di log (con estensione ldf). La cartella verrà creata in base alle esigenze di Install-CsDatabase):
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
6.  Poiché il database e i file di log sono denominati in modo esplicito con la loro posizione nel server di database di destinazione, è possibile definire percorsi specifici per il database effettivo e la posizione del log del tipo di servizio. L'esempio seguente inserisce i database per ogni tipo di servizio specifico su dischi separati e i file di log associati in un altro. Ad esempio:
    
      - Tutti i database RTC in "D\\: RTCDatabase"
    
      - Tutti i file di log RTC in "\\E: RTCLogs"
    
      - Tutti i database dell'archivio applicazioni in "\\F: CPSDatabases"
    
      - Tutti i registri dell'archivio applicazioni in "\\G: CPSLogs"
    
      - Tutti i database degli archivi di Response Group in\\"H: RGSDatabases"
    
      - Tutti i registri degli archivi di Response Group su\\"I: RGSLogs"
    
      - Tutti i database dell'archivio Rubrica per "J\\: ABSDatabases"
    
      - Tutti i file di log dell'archivio Rubrica in "\\K: ABSLogs"
    
      - Tutti i database di archiviazione archiviati in "L\\: ArchivingDatabases"
    
      - Tutti i registri degli archivi archiviati in "M\\: ArchivingLogs"
    
      - Tutti i database dell'archivio di monitoraggio in\\"N: MonitoringDatabases"
    
      - Tutti i file di log dell'archivio di monitoraggio\\in "O: MonitoringLogfiles"
    
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
    
    Usando il parametro – DatabasePathMap, puoi definire qualsiasi combinazione logica di mapping delle lettere dell'unità che offre la soluzione migliore per i requisiti di prestazioni e posizionamento di SQL Server.

Se si configurano i file di dati del database e i file di log usando il metodo **DatabasePathMap** , è necessario apportare una lieve modifica al processo normale quando si usa generatore di topologie. In genere, è necessario definire le opzioni di topologia, pubblicare la topologia e scegliere di distribuire le selezioni del database.

Se è stato usato **DatabasePathMap** , è già stata eseguita la terza parte del processo di generatore di topologia. Nel caso di un server di database completamente configurato prima dell'uso di generatore di topologia, è comunque necessario definire tutti i ruoli e le opzioni del server, ma deselezionare l'opzione per la creazione dei database.

</div>

</div>

<span> </span>

</div>

</div>

</div>

