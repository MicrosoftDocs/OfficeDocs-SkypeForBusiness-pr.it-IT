---
title: Mancanza di un nuovo pool
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 2848261164ac568d3db4dd05160b7e50ec3981d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195533"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Mancanza di un pool in Skype for Business Server 

Usare le procedure seguenti se un singolo pool Front-end non è riuscito e deve essere fallito o il pool che ha sperimentato il disastro è tornato online ed è necessario ripristinare lo stato di lavoro normale. Scopri anche come eseguire il failover e il failover del pool di Edge usato per la Federazione Skype for business o la Federazione XMPP oppure modificare il pool di bordi associato a un pool Front-end.

- [Failover di un pool Front-End](#fail-over-a-front-end-pool)
- [Eseguire il failover di un pool](#fail-back-a-pool)
- [Failover del pool di Edge usato per la Federazione di Skype for Business Server](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Failover del pool di Edge usato per la Federazione XMPP in Skype for Business Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Eseguire il failover del pool di Edge usato per la Federazione di Skype for Business Server o la Federazione XMPP](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Cambiare il pool di bordi associato a un pool Front-End](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Failover di un pool Front-End

In questa procedura, Datacenter1 contiene pool1 e pool1 non è riuscito. Non si riesce più a Pool2 situato in Datacenter2.

La maggior parte del lavoro per il failover del pool comporta l'assenza di errori sopra l'Central Management store, se necessario. Questo è importante perché l'archivio di gestione centrale deve essere funzionale quando gli utenti del pool non riescono più.

Inoltre, se un pool Front-end non riesce ma il pool di Edge in tale sito è ancora in corso, è necessario sapere se il pool di Edge usa il pool non riuscito come pool di hop successivo. In caso affermativo, è necessario modificare il pool di bordi per usare un pool Front-end diverso prima di non superare il pool Front-end non riuscito. La modalità di modifica dell'impostazione hop successiva varia a seconda che il bordo usi un pool nello stesso sito del pool di bordi o in un altro sito.

**Per impostare un pool di bordi per l'uso di un pool di hop successivo nello stesso sito**

1.  Aprire Generatore di topologia, fare clic con il pulsante destro del mouse sul pool di bordi che deve essere modificato e quindi scegliere **modifica proprietà**.

2.  Fare clic su **hop successivo**. Nell'elenco **hop successivo:** selezionare il pool che ora fungerà da pool hop successivo.

3.  Fare clic su **OK**e quindi pubblicare le modifiche.

**Per impostare un pool di bordi per l'uso di un pool di hop successivo in un altro sito**

1.  Aprire una finestra di Management Shell di Skype for Business Server e digitare il cmdlet seguente:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Per eseguire il failover di un pool in un caso di emergenza**

1.  Individuare il pool che ospita il server di gestione centralizzato digitando il cmdlet seguente in un server front-end in Pool2:
    
        Invoke-CsManagementServerFailover -Whatif
    
    I risultati di questo cmdlet mostrano quale pool ospita attualmente il server di gestione centrale. Nel resto della procedura questo pool è noto come pool di CMS\_.

2.  USA generatore di topologia per trovare la versione di Skype for Business Server in esecuzione\_nel pool di CMS. Se è in uso Skype for Business Server, usare il cmdlet seguente per trovare il pool di backup del pool 1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Consentire al\_pool di backup di essere il pool di backup.

3.  Controllare lo stato di Central Management Store con il cmdlet seguente:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Questo cmdlet deve indicare che sia ActiveMasterFQDN che ActiveFileTransferAgents puntano al nome FQDN del pool\_di CMS. Se sono vuoti, il server di gestione centrale non è disponibile ed è necessario riuscire.

4.  Se l'archivio di gestione centrale non è disponibile o se l'archivio di gestione centrale è in esecuzione in pool1, ovvero il pool non è riuscito, è necessario eseguire il failover del server di gestione centralizzato prima di non riuscire nel pool. Se è necessario eseguire il failover del server di gestione centrale ospitato in un pool che usa Skype for Business Server, usare il cmdlet nel passaggio 5 di questa procedura. Se non è necessario eseguire il failover del server di gestione centrale, passare al passaggio 7 di questa procedura.

5.  Per non superare l'Central Management store in un pool che esegue Skype for Business Server, eseguire le operazioni seguenti:
    
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

7.  Eseguire il failover degli utenti da pool1 a Pool2 eseguendo il cmdlet seguente in una finestra di Management Shell di Skype for Business Server:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Poiché la procedura adottata nelle parti precedenti di questa procedura per verificare lo stato dell'archivio di gestione centrale non è universale, è comunque possibile che il cmdlet non riesca perché l'archivio di gestione centrale non è ancora completamente riuscito. In questo caso, è necessario correggere l'Central Management store in base ai messaggi di errore visualizzati e quindi eseguire di nuovo questo cmdlet.
    
    Se viene visualizzato il messaggio di errore seguente, è necessario modificare il pool di Edge in questo sito per usare un pool diverso come hop successivo prima di non superare il pool. Per informazioni dettagliate, vedere le procedure all'inizio di questo argomento.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>Eseguire il failover di un pool

Dopo che il pool che ha sperimentato il disastro è di nuovo online, ovvero pool1 in questo esempio, eseguire la procedura seguente per ripristinare lo stato di lavoro normale.

Tieni presente che il processo di failback richiede diversi minuti per il completamento.Per riferimento, si prevede di richiedere fino a 60 minuti per un pool di utenti di 20.000.

Non è possibile eseguire il failover degli utenti che erano stati originariamente ospitati in pool1 e che non hanno eseguito il failover di Pool2 digitando il cmdlet seguente:
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Nessun altro passaggio è necessario. Se non è stato superato il server di gestione centrale, è possibile lasciarlo in Pool2.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Failover del pool di Edge usato per la Federazione di Skype for Business Server 

Se il pool di Edge in cui è stata configurata la Federazione di Skype for Business Server si abbassa, è necessario cambiare la Federazione per usare un pool di bordi diverso per il lavoro della Federazione.

1.  In un server front-end aprire Generatore di topologia. Espandere **pool di bordi**e quindi fare clic con il pulsante destro del mouse sul pool di Edge Server o Edge Server attualmente configurato per la Federazione. Selezionare **modifica proprietà**.

2.  In **modifica proprietà** in **generale**deselezionare **Abilita federazione per questo pool di bordi (porta 5061)**. Fare clic su **OK**.

3.  Espandere **pool di bordi**e quindi fare clic con il pulsante destro del mouse sul pool di Edge Server o Edge Server che si desidera utilizzare per la Federazione. Selezionare **modifica proprietà**.

4.  In **modifica proprietà** in **generale**Selezionare **Abilita federazione per questo pool di bordi (porta 5061)**. Fare clic su **OK**.

5.  Fare clic su **azione**, selezionare **topologia**, quindi **pubblica**. Quando viene richiesto di **pubblicare la topologia**, fare clic su **Avanti**. Al termine della pubblicazione, fare clic su **fine**.

6.  Nel server perimetrale aprire la distribuzione guidata di Skype for Business Server. Fare clic su **Installa o Aggiorna Skype for Business Server System**, quindi fare clic su **Imposta o Rimuovi componenti di Skype for Business Server**. Fare di nuovo clic su **Esegui**.

7.  Fare clic su **Avanti**. La schermata di riepilogo mostrerà le azioni Man mano che vengono eseguite. Dopo aver completato la distribuzione, fare clic su **Visualizza log** per visualizzare i file di log disponibili. Fare clic su **fine** per completare la distribuzione.
    
    Se il sito che contiene il pool di Edge non riuscito contiene server front-end ancora in corso, è necessario aggiornare il servizio servizi di conferenza Web e il servizio di conferenza telefonica a/V in questi pool di front-end per usare un pool di Edge in un sito remoto ancora in corso. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Failover del pool di Edge usato per la Federazione XMPP in Skype for Business Server 

Nell'organizzazione esiste un pool di bordi designato come pool da usare per la Federazione XMPP. Se il pool scende, è necessario eseguire il failover della Federazione XMPP per usare un pool di bordi diverso prima che la Federazione XMPP possa funzionare di nuovo.

La prima volta che si installano pool di bordi e si Abilita la Federazione XMPP, è possibile semplificare il processo di ripristino di emergenza impostando i record SRV DNS esterni per tutti i pool di Edge per la Federazione XMPP, anziché solo uno. Ognuno di questi record SRV deve avere un set di priorità diverso. Tutto il traffico federativo XMPP passa attraverso il pool con il record SRV con la massima priorità. 

Nella procedura seguente, EdgePool1 è il pool che ospitava originariamente la Federazione XMPP e EdgePool2 è il pool che ora ospiterà la Federazione XMPP.


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>Per eseguire il failover del pool di Edge usato per la Federazione XMPP

1.  Se non si dispone già di un altro pool di Edge distribuito, oltre a quello attualmente in calo, distribuire il pool. 

2.  In ogni Edge Server nel nuovo pool di Edge che ora ospiterà la Federazione XMPP (EdgePool2), eseguire il cmdlet seguente:
    
        Stop-CsWindowsService

3.  Eseguire il cmdlet seguente per reindirizzare la route federativo XMPP a EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    In questo esempio, sito2 è il sito che contiene il pool di bordi che ora ospiterà la route federativa XMPP e EdgeServer2.contoso.com è il nome di dominio completo di un server perimetrale in tale pool.

4.  Nel server DNS esterno modificare il record DNS per la Federazione XMPP in punti a EdgeServer2.contoso.com.

5.  Se non si ha già un record SRV DNS per la Federazione XMPP che si risolve nel pool di Edge che ora ospiterà la Federazione XMPP, è necessario aggiungerlo, come nell'esempio seguente. Questo record SRV deve avere un valore di porta 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Verificare che il pool di Edge che ora ospita la Federazione XMPP contenga la porta 5269 aperta esternamente.

7.  Avviare i servizi in tutti i server perimetrali nel pool di Edge, che ora ospiterà la Federazione XMPP:
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Eseguire il failover del pool di Edge usato per la Federazione di Skype for Business Server o la Federazione XMPP 

Dopo che un pool di Edge non riuscito usato per ospitare la Federazione è stato riportato online, usare questa procedura per non eseguire più la route federativa di Skype for Business Server e/o la route della Federazione XMPP per usare di nuovo questo pool di Edge ripristinato.

1.  Nel pool di Edge ora disponibile di nuovo, avviare i servizi Edge.

2.  Se si vuole ripristinare la route federativo di Skype for Business Server per l'uso del server perimetrale ripristinato, eseguire le operazioni seguenti:
    
      - In un server front-end aprire Generatore di topologia. Espandere **pool di bordi**e quindi fare clic con il pulsante destro del mouse sull'Edge Server o sul pool di Edge Server attualmente configurato per la Federazione. Selezionare **modifica proprietà**.
    
      - In **modifica proprietà** in **generale**deselezionare **Abilita federazione per questo pool di bordi (porta 5061)**. Fare clic su **OK**.
    
      - Espandere **pool di bordi**e quindi fare clic con il pulsante destro del mouse sull'Edge Server o sul pool di Edge Server originale che si vuole usare per la Federazione. Selezionare **modifica proprietà**.
    
      - In **modifica proprietà** in **generale**Selezionare **Abilita federazione per questo pool di bordi (porta 5061)**. Fare clic su **OK**.
    
      - Fare clic su **azione**, selezionare **topologia**, quindi **pubblica**. Quando viene richiesto di **pubblicare la topologia**, fare clic su **Avanti**. Al termine della pubblicazione, fare clic su **fine**.
    
      - Nel server perimetrale aprire la distribuzione guidata di Skype for Business Server. Fare clic su **Installa o Aggiorna Skype for Business Server System**, quindi fare clic su **Imposta o Rimuovi componenti di Skype for Business Server**. Fare di nuovo clic su **Esegui**.
    
      - Fare clic su **Avanti**. La schermata di riepilogo mostrerà le azioni Man mano che vengono eseguite. Dopo aver completato la distribuzione, fare clic su **Visualizza log** per visualizzare i file di log disponibili. Fare clic su **fine** per completare la distribuzione.

3.  Se si vuole eseguire il failover della route federativa XMPP per usare il server perimetrale ripristinato, eseguire le operazioni seguenti:
    
      - Eseguire il cmdlet seguente per reindirizzare la route federativo XMPP al pool Edge che ora ospiterà la Federazione XMPP (in questo esempio, EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        In questo esempio, Microsoft1 è il sito che contiene il pool di bordi che ora ospiterà la route federativa XMPP e EdgeServer1.contoso.com è il nome di dominio completo di un server perimetrale in tale pool.
    
      - Se non si ha già un record SRV DNS per la Federazione XMPP che si risolve nel pool di Edge che ora ospiterà la Federazione XMPP, è necessario aggiungerlo, come nell'esempio seguente. Questo record SRV deve avere un valore di porta 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - Nel server DNS esterno modificare il record DNS per la Federazione XMPP in punti a EdgeServer2.contoso.com.
    
      - Verificare che il pool di Edge che ora ospita la Federazione XMPP contenga la porta 5269 aperta esternamente.

4.  Se i pool Front-End sono rimasti in uso nel sito che contiene il pool di bordi non riuscito ed è stato ripristinato, è necessario aggiornare il servizio di Web Conferencing e il servizio di conferenza telefonica a/V in questi pool di front-end per usare di nuovo i pool di bordi nel sito locale.

5.  Se il pool Front-end nello stesso sito del pool di Edge non è riuscito anche, è ora possibile usare Invoke-CsPoolFailback per non eseguire il backup del pool Front-end.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Cambiare il pool di bordi associato a un pool Front-End

Se un pool di bordi scende ma il pool Front-end nello stesso sito è ancora in corso, è necessario impostare il pool Front-end in modo da usare un pool di Edge in un sito diverso fino a quando non viene ripristinato il pool di Edge non riuscito.

1.  In Generatore di topologie passare al nome del pool Front-end che è necessario modificare.

2.  Fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.

3.  Nella sezione **associazioni** , in **associa Edge pool (per i componenti multimediali)**, usare la casella di controllo a discesa per selezionare il pool di bordi a cui si vuole associare questo pool Front-end.

4.  Fare clic su **OK**.
