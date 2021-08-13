---
title: Eseguire failover e failback di un pool
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: 55dd80e5c71dd52dacd82f3fb12e1141a8bff470000280b582eccde7581231b1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336666"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Failover e failback di un pool in Skype for Business Server

Utilizzare le procedure seguenti se un singolo pool di Front-End ha avuto esito negativo ed è necessario eseguire il backup oppure se il pool in cui si è verificata l'emergenza è di nuovo online ed è necessario ripristinare lo stato normale della distribuzione. Informazioni su come eseguire il failover e il fail back del pool di server perimetrali utilizzato per la federazione di Skype for Business o XMPP oppure modificare il pool di server perimetrali associato a un pool Front-End server.

- [Eseguire il failover di un pool Front End](#fail-over-a-front-end-pool)
- [Eseguire il fail back di un pool](#fail-back-a-pool)
- [Eseguire il failover del pool di server perimetrali utilizzato per Skype for Business Server federazione](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Eseguire il failover del pool di server perimetrali utilizzato per la federazione XMPP in Skype for Business Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Fail back del pool di server perimetrali utilizzato per Skype for Business Server o federazione XMPP](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Modificare il pool di server perimetrali associato a un pool Front End](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Eseguire il failover di Front-End pool

Datacenter1 contiene Pool1 e Pool1 non riuscito. Si sta per eseguire il failover a Pool2 che si trova in Datacenter2.

La maggior parte del lavoro per il failover del pool implica il failover dell'archivio di gestione centrale, se necessario. L'archivio di gestione centrale deve essere funzionante quando si esegue il failed over degli utenti del pool.

Se un pool Front-End ha esito negativo, ma il pool di server perimetrali in tale sito è ancora in esecuzione, è necessario sapere se il pool di server perimetrali utilizza il pool con errori come pool hop successivo. In caso contrario, è necessario modificare il pool di server perimetrali per usare un pool di Front-End diverso prima di eseguire il failover del pool Front-End non riuscito. La modifica dell'impostazione relativa all'hop successivo varia a seconda che sia utilizzato un pool che si trova nello stesso sito o in un sito diverso.

**Per impostare un pool di server perimetrali per l'utilizzo di un pool di hop successivo nello stesso sito**

1. Aprire Generatore di topologie, fare clic con il pulsante destro del mouse sul pool di server perimetrali da modificare e scegliere **Modifica proprietà**.

2. Selezionare **Hop successivo**. **Nell'elenco Pool hop successivo:** selezionare il pool che verrà ora utilizzato come pool hop successivo.

3. Selezionare **OK** e quindi pubblicare le modifiche.

**Per impostare un pool di server perimetrali per l'utilizzo di un pool di hop successivo in un sito diverso**

1. Aprire una Skype for Business Server Management Shell e digitare il cmdlet seguente:

        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Per eseguire il failover di un pool in caso di emergenza**

1. Trovare il pool di host per il server di gestione centrale digitando il cmdlet seguente in un server Front-End in Pool2:

        Invoke-CsManagementServerFailover -Whatif

    I risultati di questo cmdlet mostrano quale pool ospita attualmente il server di gestione centrale. Nel resto di questa procedura, questo pool è noto come pool \_ CMS.

2. Utilizzare Generatore di topologie per trovare la versione di Skype for Business Server in esecuzione nel \_ pool cms. Se è in esecuzione Skype for Business Server, utilizzare il cmdlet seguente per trovare il pool di backup del pool 1.

        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>

    Consenti pool \_ di backup come pool di backup.

3. Controllare lo stato dell'archivio di gestione centrale con il cmdlet seguente:

        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 

    Questo cmdlet dovrebbe mostrare che sia ActiveMasterFQDN che ActiveFileTransferAgents puntano al nome di dominio completo del \_ pool CMS. Se sono vuoti, il server di gestione centrale non è disponibile ed è necessario eseguire il failover.

4.  Se l'archivio di gestione centrale non è disponibile o se l'archivio di gestione centrale era in esecuzione su Pool1 (ovvero il pool che ha avuto esito negativo), è necessario eseguire il failover del server di gestione centrale prima di eseguire il failover del pool. Se è necessario eseguire il failover del server di gestione centrale ospitato in un pool che esegue Skype for Business Server, utilizzare il cmdlet nel passaggio 5 di questa procedura. Se non è necessario eseguire il failover del server di gestione centrale, andare al passaggio 7 di questa procedura.

5.  Per eseguire il failover dell'archivio di gestione centrale in un pool Skype for Business Server, eseguire le operazioni seguenti:

      - Verificare innanzitutto quale Back-End Server nel pool di backup esegue l'istanza principale dell'archivio di gestione \_ centrale digitando quanto segue:

            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Se il server Back-End principale nel pool di backup \_ è l'entità, digitare:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Se il server mirror Back-End server nel pool di backup \_ è l'entità, digitare:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Verificare che il failover del server di gestione centrale sia stato completato. Digitare il comando seguente:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Verificare che ActiveMasterFQDN e ActiveFileTransferAgents puntino al nome di dominio completo del pool di \_ backup.
    
      - Infine, controllare lo stato della replica per tutti Front-End server digitando quanto segue:
        
            Get-CsManagementStoreReplicationStatus 
        
        Verificare che il valore di tutte le repliche sia True.
        
        Passare al passaggio 7 di questa procedura.

6.  Installare l'archivio di gestione centrale nel server back-end del pool di \_ backup.
    
      - Prima di tutto, eseguire il comando seguente:
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Eseguire il comando successivo in uno dei Front End Server del pool di backup per forzare lo \_ spostamento dell'archivio di gestione centrale:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Verificare che lo spostamento sia stato completato:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Verificare che ActiveMasterFQDN e ActiveFileTransferAgents puntino al nome di dominio completo del pool di \_ backup.
    
      - Controllare lo stato della replica per tutti i Front End Server digitando quanto segue:
        
            Get-CsManagementStoreReplicationStatus 
        
        Verificare che il valore di tutte le repliche sia True.
    
      - Installare il servizio Server di gestione centrale nel resto dei Front End Server nel pool di \_ backup. A tale scopo, eseguire il comando seguente in tutti i Front End Server, ad eccezione di quello utilizzato per forzare lo spostamento dell'archivio di gestione centrale in precedenza in questa procedura:
        
            Bootstrapper /Setup 

7.  Eseguire il failover degli utenti da Pool1 a Pool2 eseguendo il cmdlet seguente in una finestra Skype for Business Server Management Shell:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Poiché i passaggi evasi nelle parti precedenti di questa procedura per verificare lo stato dell'archivio di gestione centrale non sono universali, è comunque possibile che il cmdlet non riesca perché non è ancora stato eseguito il failover completo dell'archivio di gestione centrale. In questo caso, è necessario correggere l'archivio di gestione centrale in base ai messaggi di errore visualizzati e quindi eseguire di nuovo questo cmdlet.
    
    Se viene visualizzato il seguente messaggio di errore, è necessario impostare il pool di server perimetrali di questo sito in modo che utilizzi un pool diverso come hop successivo prima di eseguire il failover del pool. Per informazioni dettagliate, vedere la procedura all'inizio di questo argomento.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>Eseguire il fail back di un pool

Dopo aver riportato online il pool in cui si è verificata la situazione di emergenza (ovvero Pool1 in questo esempio), eseguire le operazioni seguenti per ripristinare uno stato di funzionamento regolare per la distribuzione.

Il completamento del processo di failback richiede alcuni minuti. Per riferimento, sono previsti fino a 60 minuti per un pool di 20.000 utenti.

Eseguire il failback degli utenti ospitati in origine in Pool1 e di cui è stato eseguito il failover in Pool2 digitando il comando di cmdlet seguente:
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Non sono necessari altri passaggi. Se è stato superato il server di gestione centrale, è possibile lasciarlo in Pool2.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Eseguire il failover del pool di server perimetrali utilizzato per Skype for Business Server federazione 

Se il pool di server perimetrali in cui è stata configurata Skype for Business Server federazione non funziona, è necessario modificare la federazione per utilizzare un pool di server perimetrali diverso per il corretto funzionamento della federazione.

1.  In un server Front End aprire il Generatore di topologie. Espandere **Pool di server** perimetrali e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali attualmente configurato per la federazione. Scegliere **Modifica proprietà**.

2.  In **Modifica proprietà** in **Generale** deselezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Selezionare **OK**.

3.  Espandere **Pool di server** perimetrali e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali che si desidera utilizzare per la federazione. Scegliere **Modifica proprietà**

4.  In **Modifica proprietà** in **Generale** selezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Selezionare **OK**.

5.  Selezionare **Azione,** selezionare **Topologia,** quindi **Pubblica.** Quando viene richiesto di **pubblicare la topologia,** selezionare **Avanti**. Al termine della pubblicazione, selezionare **Fine.**

6.  Nel server perimetrale aprire la procedura guidata Skype for Business Server distribuzione. Selezionare **Install or Update Skype for Business Server System** e quindi selezionare Setup o Remove Skype for Business Server **Components**. Selezionare **Esegui di nuovo**.

7.  Selezionare **Avanti**. Nella schermata di riepilogo sono mostrate le azioni che vengono eseguite. Al termine della distribuzione, selezionare **Visualizza registro per** visualizzare i file di registro disponibili. Selezionare **Fine** per completare la distribuzione.
    
    Se il sito contenente il pool di server perimetrali con problemi contiene Front End Server ancora in esecuzione, è necessario aggiornare il Servizio Web Conferencing e il Servizio A/V Conferencing in questi pool di Front-End per utilizzare un pool di server perimetrali in un sito remoto ancora in esecuzione. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Eseguire il failover del pool di server perimetrali utilizzato per la federazione XMPP in Skype for Business Server 

All'interno dell'organizzazione un solo pool di server perimetrali è designato come pool da usare per la federazione XMPP. Se questo pool non è disponibile, per consentire il funzionamento della federazione XMPP è necessario eseguire il failover di questa a un altro pool di server perimetrali.

Quando si installano i pool di server perimetrali e si abilita la federazione XMPP per la prima volta, per semplificare il processo di ripristino di emergenza della federazione XMPP è possibile impostare record DNS SRV esterni per tutti i pool di server perimetrali, invece che per uno solo. Per ciascuno di questi record SRV deve essere impostata una priorità diversa. Tutto il traffico di federazione XMPP passa per il pool con il record SRV con la priorità più alta. 

Nella procedura seguente EdgePool1 è il pool, che originariamente ospitava la federazione XMPP, e EdgePool2 è il pool che ospiterà la federazione XMPP.
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>Per eseguire il failover del pool di server perimetrali utilizzato per la federazione XMPP

1.  Se non è già stato distribuito un altro pool di server perimetrali (oltre a quello attualmente in esecuzione), distribuire tale pool. 

2.  In ogni server perimetrale del nuovo pool di server perimetrali che ora ospita la federazione XMPP (EdgePool2) eseguire il cmdlet seguente:
    
        Stop-CsWindowsService

3.  Eseguire il cmdlet seguente per puntare la route della federazione XMPP a EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    In questo esempio, Site2 è il sito che contiene il pool di server perimetrali che ospiterà la route della federazione XMPP ed EdgeServer2.contoso.com è l'FQDN di un server perimetrale del pool.

4.  Nel server DNS esterno modificare il record DNS A in modo che la federazione XMPP punti a EdgeServer2.contoso.com.

5.  Se per la federazione XMPP non è disponibile un record DNS SRV corrispondente al pool di server perimetrali che ospiterà la federazione XMPP, è necessario aggiungerlo così com'è illustrato nell'esempio seguente. Il valore della porta del record SRV deve essere 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Verificare che il pool di server perimetrali che ospiterà la federazione XMPP abbia la porta 5269 aperta verso l'esterno.

7.  Avviare i servizi in tutti i server perimetrali del pool che ospiterà la federazione XMPP:
    
        Start-CsWindowsService

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Fail back del pool di server perimetrali utilizzato per Skype for Business Server o federazione XMPP 

Dopo che un pool di server perimetrali non riuscito utilizzato per ospitare la federazione è stato riportato online, utilizzare questa procedura per eseguire il fail back della route di federazione di Skype for Business Server e/o della route di federazione XMPP per utilizzare di nuovo questo pool di server perimetrali ripristinato.

1.  Avviare i servizi Edge nel pool di server perimetrali che è nuovamente disponibile.

2.  Se si desidera eseguire il fail back della route Skype for Business Server federazione per utilizzare il server perimetrale ripristinato, eseguire le operazioni seguenti:
    
      - In un server Front End aprire il Generatore di topologie. Espandere **Pool di server** perimetrali, quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali attualmente configurato per la federazione. Scegliere **Modifica proprietà**.
    
      - In **Modifica proprietà** in **Generale** deselezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Selezionare **OK**.
    
      - Espandere **Pool di server** perimetrali, quindi fare clic con il pulsante destro del mouse sul server perimetrale originale o sul pool di server perimetrali che si desidera utilizzare di nuovo per la federazione. Scegliere **Modifica proprietà**
    
      - In **Modifica proprietà** in **Generale** selezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Selezionare **OK**.
    
      - Selezionare **Azione,** selezionare **Topologia,** quindi **Pubblica.** Quando viene richiesto di **pubblicare la topologia,** selezionare **Avanti**. Al termine della pubblicazione, selezionare **Fine.**
    
      - Nel server perimetrale aprire la procedura guidata Skype for Business Server distribuzione. Seleziona **Installa o Aggiorna Skype for Business Server sistema**, quindi seleziona Installazione o Rimuovi Skype for Business Server **componenti**. Selezionare **Esegui di nuovo**.
    
      - Selezionare **Avanti**. Nella schermata di riepilogo sono mostrate le azioni che vengono eseguite. Al termine della distribuzione, selezionare **Visualizza registro per** visualizzare i file di registro disponibili. Selezionare **Fine** per completare la distribuzione.

3.  Se si desidera eseguire il failback della route di federazione XMPP per l'utilizzo del server perimetrale ripristinato, eseguire le operazioni seguenti:
    
      - Eseguire il cmdlet seguente in modo che la route di federazione XMPP punti di nuovo al pool di server perimetrali che ospiterà la federazione XMPP, in questo esempio EdgeServer1:
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        In questo esempio Site1 indica il sito contenente il pool di server perimetrali che ospiterà ora la route di federazione XMPP, mentre EdgeServer1.contoso.com indica l'FQDN di un server perimetrale del pool.
    
      - Se non si dispone già di un record SRV DNS per la federazione XMPP che viene risolto nel pool di server perimetrali che ospiterà ora la federazione XMPP, aggiungerlo come indicato nell'esempio seguente. Il valore di porta del record SRV deve essere 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - Nel server DNS esterno modificare il record A DNS della federazione XMPP in modo che punti a EdgeServer2.contoso.com.
    
      - Verificare che la porta 5269 del pool di server perimetrali che ora ospita la federazione XMPP sia aperta esternamente.

4.  Se i pool Front End sono rimasti in esecuzione nel sito contenente il pool di server perimetrali in cui si è verificato l'errore e che è stato ripristinato, aggiornare il servizio Web Conferencing e il servizio A/V Conferencing in questi pool Front End in modo che riutilizzino i pool di server perimetrali nel sito locale.

5.  Se si era verificato un errore anche nel pool Front End nello stesso sito del pool di server perimetrali con errore, è ora possibile utilizzare Invoke–CsPoolFailback per eseguire il failback del pool Front End.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Modificare il pool di server perimetrali associato a un pool Front End

Se si verifica un'interruzione di un pool di server perimetrali di un sito, ma il pool Front End dello stesso sito è ancora in esecuzione, sarà necessario impostare il pool Front End in modo che venga utilizzato un pool di server perimetrali di un altro sito fino a quando il pool di server perimetrali non viene ripristinato.

1.  Nel Generatore di topologie individuare il nome del pool Front End che si vuole modificare.

2.  Fare clic con il pulsante destro del mouse sul pool e **quindi scegliere Modifica proprietà.**

3.  Nella sezione **Associazioni**, in **Associa pool di server perimetrali (per componenti multimediali)**, usare la casella di riepilogo a discesa per selezionare il pool di server perimetrali a cui si vuole associare il pool Front End.

4.  Selezionare **OK**.
