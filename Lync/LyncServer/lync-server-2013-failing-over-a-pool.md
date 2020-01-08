---
title: 'Lync Server 2013: Failover di un pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 512d7bc09d40d7b99cc66970cdd2a5584030fea9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a>Failover di un pool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-10-10_

Se un singolo pool Front-end non è riuscito e non è più necessario, eseguire la procedura seguente. In questa procedura, Datacenter1 contiene pool1 e pool1 non è riuscito. Non si riesce più a Pool2 situato in Datacenter2.

La maggior parte del lavoro per il failover del pool comporta l'assenza di errori sopra l'Central Management store, se necessario. Questo è importante perché l'archivio di gestione centrale deve essere funzionale quando gli utenti del pool non riescono più.

Inoltre, se un pool Front-end non riesce ma il pool di Edge in tale sito è ancora in corso, è necessario sapere se il pool di Edge usa il pool non riuscito come pool di hop successivo. In caso affermativo, è necessario modificare il pool di bordi per usare un pool Front-end diverso prima di non superare il pool Front-end non riuscito. La modalità di modifica dell'impostazione hop successiva varia a seconda che il bordo usi un pool nello stesso sito del pool di bordi o in un altro sito.

**Per impostare un pool di bordi per l'uso di un pool di hop successivo nello stesso sito**

1.  Aprire Generatore di topologia, fare clic con il pulsante destro del mouse sul pool di bordi che deve essere modificato e quindi scegliere **modifica proprietà**.

2.  Fare clic su **hop successivo**. Nell'elenco **hop successivo:** selezionare il pool che ora fungerà da pool hop successivo.

3.  Fare clic su **OK**e quindi pubblicare le modifiche.

**Per impostare un pool di bordi per l'uso di un pool di hop successivo in un altro sito**

1.  Aprire una finestra di Lync Server Management Shell e digitare il cmdlet seguente:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Per eseguire il failover di un pool in un caso di emergenza**

1.  Individuare il pool che ospita il server di gestione centralizzato digitando il cmdlet seguente in un server front-end in Pool2:
    
        Invoke-CsManagementServerFailover -Whatif
    
    I risultati di questo cmdlet mostrano quale pool ospita attualmente il server di gestione centrale. Nel resto della procedura questo pool è noto come pool di CMS\_.

2.  Usare generatore di topologie per trovare la versione di Lync Server in esecuzione\_nel pool di CMS. Se è in uso Lync Server 2013, usare il cmdlet seguente per trovare il pool di backup del pool 1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Consentire al\_pool di backup di essere il pool di backup.

3.  Controllare lo stato di Central Management Store con il cmdlet seguente:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Questo cmdlet deve indicare che sia ActiveMasterFQDN che ActiveFileTransferAgents puntano al nome FQDN del pool\_di CMS. Se sono vuoti, il server di gestione centrale non è disponibile ed è necessario riuscire.

4.  Se l'archivio di gestione centrale non è disponibile o se l'archivio di gestione centrale è in esecuzione in pool1, ovvero il pool non è riuscito, è necessario eseguire il failover del server di gestione centralizzato prima di non riuscire nel pool. Se è necessario eseguire il failover del server di gestione centrale ospitato in un pool in cui è in esecuzione Lync Server 2013, usare il cmdlet nel passaggio 5 di questa procedura. Se è necessario eseguire il failover del server di gestione centrale ospitato in un pool in cui è in esecuzione Lync Server 2010, usare il cmdlet nel passaggio 6 di questa procedura. Se non è necessario eseguire il failover del server di gestione centrale, passare al passaggio 7 di questa procedura.

5.  Per eseguire il failover dell'Central Management store in un pool in cui è in esecuzione Lync Server 2013, procedere come segue:
    
      - Prima di tutto, controlla che il server back\_-end nel pool di backup esegua l'istanza principale di Central Management Store digitando quanto segue:
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Se il server di back-end principale\_nel pool di backup è l'entità, digitare:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Se il server mirror back-end nel\_pool di backup è l'entità, digitare:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Verificare che il failover di Central Management Server sia completo. Digitare quanto segue:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Verificare che sia ActiveMasterFQDN che ActiveFileTransferAgents indichino il nome di dominio completo\_del pool di backup.
    
      - Infine, controlla lo stato della replica per tutti i server front-end digitando quanto segue:
        
            Get-CsManagementStoreReplicationStatus 
        
        Verificare che tutte le repliche abbiano il valore true.
        
        Passare al passaggio 7 in questa procedura.

6.  Installare il Central Management store nel server back-end del pool\_di backup.
    
      - Eseguire prima di tutto il comando seguente:
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Eseguire il comando successivo in uno dei server front-end del pool\_di backup per forzare lo stato di trasferimento di Central Management store:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Convalidare lo stato di trasferimento è completo:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Verificare che sia ActiveMasterFQDN che ActiveFileTransferAgents indichino il nome di dominio completo\_del pool di backup.
    
      - Controllare lo stato della replica per tutti i server front-end digitando quanto segue:
        
            Get-CsManagementStoreReplicationStatus 
        
        Verificare che tutte le repliche abbiano il valore true.
    
      - Installare il servizio Central Management Server nel resto dei server front-end nel pool di\_backup. A tale scopo, eseguire il comando seguente in tutti i server front-end, ad eccezione di quello usato per forzare lo stato precedente della procedura:
        
            Bootstrapper /Setup 

7.  Eseguire il failover degli utenti da pool1 a Pool2 eseguendo il cmdlet seguente in una finestra di Lync Server Management Shell:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Poiché la procedura adottata nelle parti precedenti di questa procedura per verificare lo stato dell'archivio di gestione centrale non è universale, è comunque possibile che il cmdlet non riesca perché l'archivio di gestione centrale non è ancora completamente riuscito. In questo caso, è necessario correggere l'Central Management store in base ai messaggi di errore visualizzati e quindi eseguire di nuovo questo cmdlet.
    
    Se viene visualizzato il messaggio di errore seguente, è necessario modificare il pool di Edge in questo sito per usare un pool diverso come hop successivo prima di non superare il pool. Per informazioni dettagliate, vedere le procedure all'inizio di questo argomento.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

