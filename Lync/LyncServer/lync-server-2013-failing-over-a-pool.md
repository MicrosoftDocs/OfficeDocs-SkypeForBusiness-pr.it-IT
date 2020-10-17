---
title: 'Lync Server 2013: failover di un pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bf54f1949627c39291388be248e0029077e9278
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530963"
---
# <a name="failing-over-a-pool-in-lync-server-2013"></a>Failover di un pool in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-10-10_

Se si verifica un errore in un singolo pool Front End ed è necessario eseguirne il failover, utilizzare la procedura indicata di seguito. In questa procedura, Datacenter1 contiene Pool1 e l'errore si è verificato in Pool1. Viene eseguito il failover su Pool2 situato in Datacenter2.

La maggior parte del lavoro per il failover del pool comporta l'failover dell'archivio di gestione centrale, se necessario. Questo è importante perché l'archivio di gestione centrale deve essere funzionale quando gli utenti del pool non sono più in grado di eseguire l'operazione.

Inoltre, se si verifica un errore in un pool Front End ma il pool di server perimetrali presso il sito è ancora in esecuzione, è necessario sapere se quest'ultimo pool utilizza quello in cui si è verificato l'errore come pool hop successivo. In caso affermativo, è necessario impostare il pool di server perimetrali in modo da utilizzare un pool Front End diverso prima del failover del pool Front End in errore. La modifica dell'impostazione relativa all'hop successivo varia a seconda che sia utilizzato un pool che si trova nello stesso sito o in un sito diverso.

**Per impostare un pool di server perimetrali per l'utilizzo di un pool hop successivo nello stesso sito**

1.  Aprire Generatore di topologie, fare clic con il pulsante destro del mouse sul pool di server perimetrali che deve essere modificato e scegliere **modifica proprietà**.

2.  Fare clic su **Hop successivo**. Nell'elenco **Pool hop successivo** selezionare il pool da utilizzare come pool hop successivo.

3.  Fare clic su **OK**, quindi pubblicare le modifiche.

**Per impostare un pool di server perimetrali per l'utilizzo di un pool hop successivo in un sito diverso**

1.  Aprire una finestra di Lync Server Management Shell e digitare il cmdlet seguente:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Per eseguire il failover di un pool in caso di emergenza**

1.  Individuare il pool che ospita il server di gestione centrale digitando il cmdlet seguente in un front end server in Pool2:
    
        Invoke-CsManagementServerFailover -Whatif
    
    I risultati di questo cmdlet mostrano quale pool ospita attualmente il server di gestione centrale. Nella parte restante di questa procedura, questo pool è noto come \_ pool CMS.

2.  Utilizzare Generatore di topologie per individuare la versione di Lync Server in esecuzione nel \_ pool CMS. Se è in esecuzione Lync Server 2013, utilizzare il cmdlet seguente per individuare il pool di backup del pool 1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Fare in modo che \_ il pool di backup sia il pool di backup.

3.  Controllare lo stato dell'archivio di gestione centrale con il cmdlet seguente:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Questo cmdlet deve mostrare che sia ActiveMasterFQDN che ActiveFileTransferAgents puntano al nome di dominio completo del \_ pool CMS. Se sono vuoti, il server di gestione centrale non è disponibile ed è necessario eseguirne il failover.

4.  Se l'archivio di gestione centrale non è disponibile o se l'archivio di gestione centrale è in esecuzione su Pool1, ovvero il pool che ha avuto esito negativo, è necessario eseguire il failover del server di gestione centrale prima che venga eseguito il failover del pool. Se è necessario eseguire il failover del server di gestione centrale ospitato in un pool che esegue Lync Server 2013, utilizzare il cmdlet nel passaggio 5 di questa procedura. Se è necessario eseguire il failover del server di gestione centrale ospitato in un pool che esegue Lync Server 2010, utilizzare il cmdlet nel passaggio 6 di questa procedura. Se non è necessario eseguire il failover del server di gestione centrale, passare al passaggio 7 di questa procedura.

5.  Per eseguire il failover dell'archivio di gestione centrale in un pool che esegue Lync Server 2013, eseguire le operazioni seguenti:
    
      - Verificare innanzitutto quale server back-end \_ del pool di backup esegue l'istanza principale dell'archivio di gestione centrale digitando quanto segue:
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Se il server back-end principale del \_ pool di backup è il principale, digitare quanto segue:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Se il server back-end mirror del \_ pool di backup è il principale, digitare quanto segue:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Verificare che il failover del server di gestione centrale sia stato completato. Digitare quanto segue:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Verificare che sia ActiveMasterFQDN che ActiveFileTransferAgents puntino al nome di dominio completo del pool di backup \_ .
    
      - Infine, controllare lo stato della replica per tutti i Front End Server digitando quanto segue:
        
            Get-CsManagementStoreReplicationStatus 
        
        Verificare che il valore di tutte le repliche sia True.
        
        Passare al passaggio 7 di questa procedura.

6.  Installare l'archivio di gestione centrale nel server back-end del \_ pool di backup.
    
      - Prima di tutto, eseguire il comando seguente:
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - \_Per forzare lo spostamento dell'archivio di gestione centrale, eseguire il comando successivo in uno dei front end server del pool di backup:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Verificare che lo spostamento sia stato completato:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Verificare che sia ActiveMasterFQDN che ActiveFileTransferAgents puntino al nome di dominio completo del pool di backup \_ .
    
      - Controllare lo stato della replica per tutti i Front End Server digitando quanto segue:
        
            Get-CsManagementStoreReplicationStatus 
        
        Verificare che il valore di tutte le repliche sia True.
    
      - Installare il servizio server di gestione centrale nel resto dei front end server nel pool di backup \_ . A tale scopo, eseguire il comando riportato di seguito in tutti i Front End Server, tranne quello utilizzato per forzare lo spostamento dell'archivio di gestione centrale in precedenza in questa procedura:
        
            Bootstrapper /Setup 

7.  Eseguire il failover degli utenti da pool1 a Pool2 eseguendo il cmdlet seguente in una finestra di Lync Server Management Shell:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Poiché le operazioni eseguite nelle parti precedenti di questa procedura per verificare lo stato dell'archivio di gestione centrale non sono universali, è comunque possibile che questo cmdlet non venga eseguito correttamente perché l'archivio di gestione centrale non è ancora completamente superato. In questo caso, è necessario correggere l'archivio di gestione centrale in base ai messaggi di errore visualizzati e quindi eseguire di nuovo questo cmdlet.
    
    Se viene visualizzato il seguente messaggio di errore, è necessario impostare il pool di server perimetrali di questo sito in modo che utilizzi un pool diverso come hop successivo prima di eseguire il failover del pool. Per informazioni dettagliate, vedere la procedura all'inizio di questo argomento.
    
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

