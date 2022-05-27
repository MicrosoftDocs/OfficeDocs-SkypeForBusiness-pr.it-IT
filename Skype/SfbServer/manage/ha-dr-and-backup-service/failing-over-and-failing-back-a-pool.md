---
title: Eseguire failover e failback di un pool
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: .
ms.openlocfilehash: 0b1f79ff40584c82d6da603ede49004f3c0c8968
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675038"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Failover e failback di un pool in Skype for Business Server

Usare le procedure seguenti se un singolo pool di Front-End ha avuto esito negativo e deve essere eseguito il failover oppure il pool che ha riscontrato l'emergenza è di nuovo online ed è necessario ripristinare lo stato di lavoro normale della distribuzione. Informazioni su come eseguire il failover e il failback del pool di server perimetrali usato per Skype for Business federazione o per la federazione XMPP oppure modificare il pool di server perimetrali associato a un pool di Front-End.

- [Failover di un pool Front End](#fail-over-a-front-end-pool)
- [Eseguire il failback di un pool](#fail-back-a-pool)
- [Eseguire il failover del pool di server perimetrali usato per la federazione Skype for Business Server](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Eseguire il failover del pool di server perimetrali usato per la federazione XMPP in Skype for Business Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Eseguire il failback del pool di server perimetrali usato per la federazione Skype for Business Server o XMPP](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Modificare il pool di server perimetrali associato a un pool Front End](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Eseguire il failover di un pool di Front-End

Datacenter1 contiene Pool1 e Pool1 non è riuscito. Si sta eseguendo il failover in Pool2 che si trova in Datacenter2.

La maggior parte delle operazioni per il failover del pool comporta il failover dell'archivio di gestione centrale, se necessario. L'archivio di gestione centrale deve essere funzionante quando viene eseguito il failover degli utenti del pool.

Se un pool di Front-End ha esito negativo, ma il pool di server perimetrali in tale sito è ancora in esecuzione, è necessario sapere se il pool di server perimetrali usa il pool non riuscito come pool di hop successivo. In caso affermativo, è necessario modificare il pool di server perimetrali per usare un pool di Front-End diverso prima di eseguire il failover del pool di Front-End non riuscito. La modifica dell'impostazione relativa all'hop successivo varia a seconda che sia utilizzato un pool che si trova nello stesso sito o in un sito diverso.

**Per impostare un pool di server perimetrali per l'uso di un pool di hop successivo nello stesso sito**

1. Aprire Generatore di topologie, fare clic con il pulsante destro del mouse sul pool di server perimetrali che deve essere modificato e scegliere **Modifica proprietà**.

2. Selezionare **Hop successivo**. Nell'elenco **Pool hop successivo** selezionare il pool che verrà ora usato come pool hop successivo.

3. Selezionare **OK** e quindi pubblicare le modifiche.

**Per impostare un pool di server perimetrali per l'uso di un pool di hop successivo in un sito diverso**

1. Aprire una finestra Skype for Business Server Management Shell e digitare il cmdlet seguente:

    ```powershell
    Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>
    ```

**Per eseguire il failover di un pool in un'emergenza**

1. Trovare il pool di host per il server di gestione centrale digitando il cmdlet seguente in un server Front-End in Pool2:

    ```powershell
    Invoke-CsManagementServerFailover -Whatif
    ```

    I risultati di questo cmdlet mostrano quale pool ospita attualmente il server di gestione centrale. Nella parte restante di questa procedura, questo pool è noto come pool cms\_.

2. Usare Generatore di topologie per trovare la versione di Skype for Business Server in esecuzione nel pool cms\_. Se è in esecuzione Skype for Business Server, usare il cmdlet seguente per trovare il pool di backup del pool 1.

    ```powershell
    Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    ```

    Lasciare Backup\_ Pool come pool di backup.

3. Controllare lo stato dell'archivio di gestione centrale con il cmdlet seguente:

    ```powershell
    Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
    ```

    Questo cmdlet deve indicare che sia ActiveMasterFQDN che ActiveFileTransferAgent puntano al nome di dominio completo del pool cms\_. Se sono vuoti, il server di gestione centrale non è disponibile ed è necessario eseguirne il failover.

4.  Se l'archivio di gestione centrale non è disponibile o se l'archivio di gestione centrale era in esecuzione in Pool1(ovvero il pool non riuscito), è necessario eseguire il failover del server di gestione centrale prima di eseguire il failover del pool. Se è necessario eseguire il failover del server di gestione centrale ospitato in un pool che esegue Skype for Business Server, usare il cmdlet nel passaggio 5 di questa procedura. Se non è necessario eseguire il failover del server di gestione centrale, passare al passaggio 7 di questa procedura.

5.  Per eseguire il failover dell'archivio di gestione centrale in un pool in esecuzione Skype for Business Server, eseguire le operazioni seguenti:

    1. Prima di tutto, controllare quale Back-End Server in Backup\_ Pool esegue l'istanza principale dell'archivio di gestione centrale digitando quanto segue:

        ```powershell
        Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
        ```
    
    1. Se il server Back-End primario in Backup\_ Pool è l'entità, digitare:

        ```powershell        
        Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        ```
        
    1. Se il server mirror Back-End in Backup\_ Pool è l'entità, digitare:
    
        ```powershell
        Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
        ```
    
    1. Verificare che il failover del server di gestione centrale sia completo. Digitare il comando seguente:
    
        ```powershell    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        Verificare che ActiveMasterFQDN e ActiveFileTransferAgents puntino al nome di dominio completo di Backup\_ Pool.
    
    1. Controllare infine lo stato della replica per tutti i server Front-End digitando quanto segue:
        
        ```powershell
        Get-CsManagementStoreReplicationStatus 
        ```
        
        Verificare che il valore di tutte le repliche sia True.
        
        Passare al passaggio 7 di questa procedura.

6.  Installare l'archivio di gestione centrale nel server back-end di Backup\_ Pool.
    
    1. Prima di tutto, eseguire il comando seguente:

        ```powershell
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
    1. Eseguire il comando successivo in uno dei Front End Server di Backup\_ Pool per forzare lo spostamento dell'archivio di gestione centrale:

        ```powershell
        Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force
        ```
    
    1. Verificare che lo spostamento sia stato completato:

        ```powershell
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        Verificare che ActiveMasterFQDN e ActiveFileTransferAgents puntino al nome di dominio completo di Backup\_ Pool.
    
    1. Controllare lo stato della replica per tutti i Front End Server digitando quanto segue:

        ```powershell
        Get-CsManagementStoreReplicationStatus
        ```
        
        Verificare che il valore di tutte le repliche sia True.
    
    1. Installare il servizio Server di gestione centrale nel resto dei front-end server in Backup\_ Pool. A tale scopo, eseguire il comando seguente in tutti i Front End Server, ad eccezione di quello usato per forzare lo spostamento dell'archivio di gestione centrale in precedenza in questa procedura:

        ```console
        Bootstrapper /Setup
        ```

7.  Eseguire il failover degli utenti da Pool1 a Pool2 eseguendo il cmdlet seguente in una finestra Skype for Business Server Management Shell:

    ```powershell
    Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    ```
    
    Poiché i passaggi eseguiti nelle parti precedenti di questa procedura per controllare lo stato dell'archivio di gestione centrale non sono universali, è comunque possibile che questo cmdlet non riesca perché l'archivio di gestione centrale non ha ancora eseguito il failover completo. In questo caso, è necessario correggere l'archivio di gestione centrale in base ai messaggi di errore visualizzati e quindi eseguire di nuovo questo cmdlet.
    
    Se viene visualizzato il seguente messaggio di errore, è necessario impostare il pool di server perimetrali di questo sito in modo che utilizzi un pool diverso come hop successivo prima di eseguire il failover del pool. Per informazioni dettagliate, vedere la procedura all'inizio di questo argomento.
    
    ```console
    Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
    topology as the next hop for the Edge server. Failing over this pool may cause External
    access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
    change the Edge internal next hop setting to point to a different Front-end pool,  before you
    proceed.
    ```


## <a name="fail-back-a-pool"></a>Eseguire il failback di un pool

Dopo aver riportato online il pool in cui si è verificata la situazione di emergenza (ovvero Pool1 in questo esempio), eseguire le operazioni seguenti per ripristinare uno stato di funzionamento regolare per la distribuzione.

Il completamento del processo di failback richiede alcuni minuti. Per riferimento, sono previsti fino a 60 minuti per un pool di 20.000 utenti.

Eseguire il failback degli utenti ospitati in origine in Pool1 e di cui è stato eseguito il failover in Pool2 digitando il comando di cmdlet seguente:

```powershell
Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose
```

Non sono necessari altri passaggi. Se è stato eseguito il failover del server di gestione centrale, è possibile lasciarlo in Pool2.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Eseguire il failover del pool di server perimetrali usato per la federazione Skype for Business Server 

Se il pool di server perimetrali in cui è stata configurata Skype for Business Server federazione viene disattivato, è necessario modificare la federazione per usare un pool di server perimetrali diverso per consentire il funzionamento della federazione.

1.  In un server Front End aprire il Generatore di topologie. Espandere **Pool di server perimetrali** e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali attualmente configurato per la federazione. Scegliere **Modifica proprietà**.

2.  In **Modifica proprietà** in **Generale** deselezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Selezionare **OK**.

3.  Espandere **Pool di server perimetrali** e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali che si vuole usare per la federazione. Scegliere **Modifica proprietà**

4.  In **Modifica proprietà** in **Generale** selezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Selezionare **OK**.

5.  Selezionare **Azione**, selezionare **Topologia** e quindi **Pubblica**. Quando richiesto in **Pubblicare la topologia**, selezionare **Avanti**. Al termine della pubblicazione, selezionare **Fine**.

6.  Nel server Perimetrale aprire la distribuzione guidata Skype for Business Server. Selezionare **Install or Update Skype for Business Server System (Installa o aggiorna Skype for Business Server sistema**) e quindi selezionare **Setup (Installazione) o Remove Skype for Business Server Components (Rimuovi componenti Skype for Business Server).** Selezionare **Esegui di nuovo**.

7.  Selezionare **Avanti**. Nella schermata di riepilogo sono mostrate le azioni che vengono eseguite. Al termine della distribuzione, selezionare **Visualizza log** per visualizzare i file di log disponibili. Selezionare **Fine** per completare la distribuzione.
    
    Se il sito contenente il pool edge non riuscito contiene Front End Server che sono ancora in esecuzione, è necessario aggiornare il servizio Web Conferencing e il servizio A/V Conferencing in questi pool di Front-End per usare un pool edge in un sito remoto ancora in esecuzione. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Eseguire il failover del pool di server perimetrali usato per la federazione XMPP in Skype for Business Server 

All'interno dell'organizzazione un solo pool di server perimetrali è designato come pool da usare per la federazione XMPP. Se questo pool non è disponibile, per consentire il funzionamento della federazione XMPP è necessario eseguire il failover di questa a un altro pool di server perimetrali.

Quando si installano i pool di server perimetrali e si abilita la federazione XMPP per la prima volta, per semplificare il processo di ripristino di emergenza della federazione XMPP è possibile impostare record DNS SRV esterni per tutti i pool di server perimetrali, invece che per uno solo. Per ciascuno di questi record SRV deve essere impostata una priorità diversa. Tutto il traffico di federazione XMPP passa per il pool con il record SRV con la priorità più alta. 

Nella procedura seguente EdgePool1 è il pool, che originariamente ospitava la federazione XMPP, e EdgePool2 è il pool che ora ospiterà la federazione XMPP.
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>Per eseguire il failover del pool di server perimetrali usato per la federazione XMPP

1.  Se non è già stato distribuito un altro pool di server perimetrali (oltre a quello attualmente inattivo), distribuire tale pool. 

2.  In ogni server perimetrale del nuovo pool di server perimetrali che ora ospita la federazione XMPP (EdgePool2) eseguire il cmdlet seguente:

    ```powershell
    Stop-CsWindowsService
    ```

3.  Eseguire il cmdlet seguente per puntare la route della federazione XMPP a EdgePool2:

    ```powershell
    Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    ```
    
    In questo esempio, Site2 è il sito che contiene il pool di server perimetrali che ospiterà la route della federazione XMPP ed EdgeServer2.contoso.com è l'FQDN di un server perimetrale del pool.

4.  Nel server DNS esterno modificare il record DNS A in modo che la federazione XMPP punti a EdgeServer2.contoso.com.

5.  Se per la federazione XMPP non è disponibile un record DNS SRV corrispondente al pool di server perimetrali che ospiterà la federazione XMPP, è necessario aggiungerlo così com'è illustrato nell'esempio seguente. Il valore della porta del record SRV deve essere 5269.

    ```console
    _xmpp-server._tcp.contoso.com
    ```

6.  Verificare che il pool di server perimetrali che ospiterà la federazione XMPP abbia la porta 5269 aperta verso l'esterno.

7.  Avviare i servizi in tutti i server perimetrali del pool che ospiterà la federazione XMPP:

    ```powershell
    Start-CsWindowsService
    ```

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Eseguire il failback del pool di server perimetrali usato per la federazione Skype for Business Server o XMPP 

Dopo aver riportato online un pool di server perimetrali non riuscito usato per ospitare la federazione, usare questa procedura per eseguire il failback della route di federazione Skype for Business Server e/o della route federativa XMPP per usare di nuovo questo pool perimetrale ripristinato.

1.  Avviare i servizi Edge nel pool di server perimetrali che è nuovamente disponibile.

2.  Se si vuole eseguire il failback della route federativa Skype for Business Server per usare il server perimetrale ripristinato, eseguire le operazioni seguenti:
    
    1. In un server Front End aprire il Generatore di topologie. Espandere **Pool di server perimetrali**, quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali attualmente configurato per la federazione. Scegliere **Modifica proprietà**.
    
    1. In **Modifica proprietà** in **Generale** deselezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Selezionare **OK**.
    
    1. Espandere **Pool di edge**, quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali originale che si vuole usare di nuovo per la federazione. Scegliere **Modifica proprietà**
    
    1. In **Modifica proprietà** in **Generale** selezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Selezionare **OK**.
    
    1. Selezionare **Azione**, selezionare **Topologia** e quindi **Pubblica**. Quando richiesto in **Pubblicare la topologia**, selezionare **Avanti**. Al termine della pubblicazione, selezionare **Fine**.
    
    1. Nel server Perimetrale aprire la distribuzione guidata Skype for Business Server. Selezionare **Install or Update Skype for Business Server System (Installa o aggiorna sistema Skype for Business Server**), quindi selezionare **Setup (Installazione) o Remove Skype for Business Server Components (Rimuovi componenti Skype for Business Server).** Selezionare **Esegui di nuovo**.
    
    1. Selezionare **Avanti**. Nella schermata di riepilogo sono mostrate le azioni che vengono eseguite. Al termine della distribuzione, selezionare **Visualizza log** per visualizzare i file di log disponibili. Selezionare **Fine** per completare la distribuzione.

3.  Se si desidera eseguire il failback della route di federazione XMPP per l'utilizzo del server perimetrale ripristinato, eseguire le operazioni seguenti:
    
    1. Eseguire il cmdlet seguente in modo che la route di federazione XMPP punti di nuovo al pool di server perimetrali che ospiterà la federazione XMPP, in questo esempio EdgeServer1:
  
        ```powershell
        Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        ```
        
        In questo esempio Site1 indica il sito contenente il pool di server perimetrali che ospiterà ora la route di federazione XMPP, mentre EdgeServer1.contoso.com indica l'FQDN di un server perimetrale del pool.
    
    1. Se non si dispone già di un record SRV DNS per la federazione XMPP che viene risolto nel pool di server perimetrali che ospiterà ora la federazione XMPP, aggiungerlo come indicato nell'esempio seguente. Il valore di porta del record SRV deve essere 5269.

        ```console
        _xmpp-server._tcp.contoso.com
        ```
    
    1. Nel server DNS esterno modificare il record A DNS della federazione XMPP in modo che punti a EdgeServer2.contoso.com.
    
    1. Verificare che la porta 5269 del pool di server perimetrali che ora ospita la federazione XMPP sia aperta esternamente.

4.  Se i pool Front End sono rimasti in esecuzione nel sito contenente il pool di server perimetrali in cui si è verificato l'errore e che è stato ripristinato, aggiornare il servizio Web Conferencing e il servizio A/V Conferencing in questi pool Front End in modo che riutilizzino i pool di server perimetrali nel sito locale.

5.  Se si era verificato un errore anche nel pool Front End nello stesso sito del pool di server perimetrali con errore, è ora possibile utilizzare Invoke–CsPoolFailback per eseguire il failback del pool Front End.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Modificare il pool di server perimetrali associato a un pool Front End

Se si verifica un'interruzione di un pool di server perimetrali di un sito, ma il pool Front End dello stesso sito è ancora in esecuzione, sarà necessario impostare il pool Front End in modo che venga utilizzato un pool di server perimetrali di un altro sito fino a quando il pool di server perimetrali non viene ripristinato.

1.  Nel Generatore di topologie individuare il nome del pool Front End che si vuole modificare.

2.  Fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica proprietà**.

3.  Nella sezione **Associazioni**, in **Associa pool di server perimetrali (per componenti multimediali)**, usare la casella di riepilogo a discesa per selezionare il pool di server perimetrali a cui si vuole associare il pool Front End.

4.  Selezionare **OK**.
