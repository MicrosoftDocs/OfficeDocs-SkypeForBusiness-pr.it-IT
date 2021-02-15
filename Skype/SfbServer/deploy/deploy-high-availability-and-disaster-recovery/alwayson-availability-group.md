---
title: Distribuire un gruppo di disponibilità Always On in un server back-end in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Distribuire (installare) un gruppo di disponibilità Always On nella distribuzione di Skype for Business Server.
ms.openlocfilehash: 83565efe850570ac5ab9a0695757e708f3eae566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830656"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a>Distribuire un gruppo di disponibilità Always On in un server back-end in Skype for Business Server
 
Distribuire (installare) un gruppo di disponibilità Always On nella distribuzione di Skype for Business Server.
  
La modalità di distribuzione di un gruppo di disponibilità varia a seconda che si distribuisca in un nuovo pool, in un pool esistente che utilizza il mirroring o in un pool esistente che attualmente non dispone di disponibilità elevata per il database back-end.
  
> [!NOTE]
> L'utilizzo di un gruppo di disponibilità con un ruolo del server Chat persistente non è supportato. 
  
- [Distribuire un gruppo di disponibilità Always On in un nuovo pool Front End](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Distribuire un gruppo di disponibilità Always On in un pool esistente che utilizza il mirroring del database](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Distribuire un gruppo di disponibilità Always On in un pool esistente che non utilizza il mirroring del database](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a>Distribuire un gruppo di disponibilità Always On in un nuovo pool Front End
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Abilitare la funzionalità Clustering di failover in tutti i server di database che fanno parte del gruppo di disponibilità. In ogni server eseguire le operazioni seguenti
    
   - Aprire Server Manager e fare clic **su Aggiungi ruoli e funzionalità.**
    
   - Fare **clic su** Avanti fino a raggiungere la casella **Seleziona** funzionalità. In questo caso, selezionare la **casella di controllo Clustering** di failover.
    
   - Nella casella **Add features that are required for Failover Clustering?** fare clic su Add **Features.**
    
   - Fare clic su **Installa**.
    
2. Convalidare la configurazione del cluster.
    
   - In Server Manager scegliere Gestione **cluster** di failover dal menu **Strumenti.**
    
   - In **Azioni sul** lato destro dello schermo fare clic su Convalida **configurazione.**
    
   - Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.
    
   - Selezionare i server da aggiungere al cluster e quindi fare clic **su Esegui tutti i test.**
    
   - Nella casella **Riepilogo** controllare gli eventuali errori rilevati dalla procedura guidata. Fare quindi **clic su Fine** per completare la convalida.
    
     La procedura guidata probabilmente segnala diversi avvisi, soprattutto se non si utilizza l'archiviazione condivisa. Non è necessario utilizzare l'archiviazione condivisa. Tuttavia, se vengono visualizzati messaggi **di** errore, è necessario risolvere tali problemi prima di continuare.
    
3. Creare il cluster di failover di Windows Server (WSFC).
    
   - Nella procedura **guidata Gestione cluster di failover** fare clic con il pulsante destro del mouse su Gestione cluster di **failover** e quindi scegliere **Crea cluster.**
    
   - Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.
    
   - Aggiungere il nome del cluster e l'indirizzo IP. Dopo la convalida delle impostazioni, fare clic su **Avanti.**
    
   - Nella pagina Conferma, fare clic su **Avanti**.
    
   - Dopo aver creato il cluster, fare clic su **Fine.**
    
4. È consigliabile configurare le impostazioni del quorum del cluster per l'utilizzo di un controllo della condivisione file. A tale scopo, eseguire la procedura seguente:
    
   - Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **Altre azioni** e fare clic su Configura impostazioni **quorum cluster.**
    
   - Nella pagina **Selezione opzione di configurazione quorum** fare clic su Seleziona il controllo del **quorum.**
    
   - Nella pagina **Selezione quorum di controllo** fare clic su Configura un controllo della condivisione **file.**
    
   - Nella pagina **Configura condivisione file di controllo** digitare il percorso della condivisione file che si desidera utilizzare e quindi fare clic su **Avanti.**
    
   - Nella pagina **Conferma**, fare clic su **Avanti**.
    
5. In ogni server del cluster abilitare la funzionalità Di gruppo di disponibilità in SQL Server Configuration Manager.
    
   - Aprire Gestione configurazione SQL Server. Nell'albero sul lato sinistro dello schermo fare clic su **SQL Server Servizi** e quindi fare doppio clic sul SQL Server servizio. 
    
   - Nella casella **Proprietà** selezionare la **scheda Disponibilità elevata AlwaysOn.** Selezionare la **casella di controllo Abilita gruppi di disponibilità AlwaysOn.** Riavviare SQL Server servizio quando richiesto.
   
6. Utilizzare Generatore di topologie per creare il pool Front End, come illustrato in Creare e pubblicare una nuova topologia [in Skype for Business Server.](../../deploy/install/create-and-publish-new-topology.md) In questo caso, specificare il gruppo di disponibilità come SQL per il pool.
    
7. Creare il gruppo di disponibilità.
    
   - Apri SQL Server Management Studio e connettiti all'SQL Server istanza.
    
   - In Esplora oggetti espandere la **cartella Disponibilità elevata Always On.** Fare clic con il pulsante destro **del** mouse sulla cartella Gruppi di disponibilità e scegliere **Creazione guidata nuovo gruppo di disponibilità.**
    
   - Se viene **visualizzata la** pagina Introduzione, fare clic su **Avanti.**
    
   - Nella pagina **Specifica nome gruppo di** disponibilità digitare il nome del gruppo di disponibilità e fare clic su **Avanti.**
    
   - Nella pagina Selezione database selezionare i database che si desidera includere nel gruppo di disponibilità AlwaysOn. Scegliere il pulsante **Avanti**.
    
     Non includere i **database ReportServer,** **ReportServerTempDB** o Persistent Chat nel gruppo di disponibilità AlwaysOn, in quanto non sono supportati in questo scenario. È possibile includere tutti gli altri database di Skype for Business Server nel gruppo di disponibilità AlwaysOn.
    
   - Nella pagina **Specifica repliche** fare clic sulla **scheda** Repliche. Fare quindi clic **sul pulsante Aggiungi** repliche e connettersi alle altre istanze SQL unite come nodi del cluster di failover di Windows Server.
    
   - Per ogni istanza, selezionare le **opzioni Failover automatico** e **Commit** sincrono. Non selezionare **l'opzione Secondaria leggibile.**
    
   - Fare clic **sulla scheda Endpoint** e verificare che il numero di **porta** sia impostato su 5022.
    
   - Fare clic **sulla scheda Listener** e selezionare l'opzione Crea listener del gruppo **di** disponibilità. In tale opzione digitare un nome per il listener e impostare **la** porta su 1433 (altre porte non sono supportate per questa opzione).
    
   - Fare **clic su** Aggiungi e quindi nella casella Indirizzo **IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK.**
    
   - Nella **pagina** Selezione sincronizzazione dati iniziale selezionare Completo e specificare una cartella accessibile alle repliche e per cui l'account di servizio SQL Server utilizzato da entrambe le repliche dispone delle autorizzazioni di scrittura. Scegliere il pulsante **Avanti**.
    
     Questa condivisione file verrà utilizzata temporaneamente quando si inizializzano i database. Se si gestiscono database di grandi dimensioni, è consigliabile inizializzarli manualmente nel caso in cui la larghezza di banda di rete non possa contenere le dimensioni dei backup dei database.
    
   - Nella pagina Convalida verificare che tutti i controlli di convalida siano stati eseguiti correttamente e quindi fare clic su **Avanti.**
    
   - Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su Fine.
      
8. Dopo aver distribuito il pool e il gruppo di disponibilità del gruppo di disponibilità, eseguire alcuni passaggi finali per assicurarsi che gli account di accesso SQL siano presenti in ognuna delle repliche nel gruppo di disponibilità AlwaysOn. 
    
   - Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente** e fare clic su **OK.**
    
   - Espandere Skype for Business Server, espandere la topologia ed espandere SQL Server **store.** Fare clic con il pulsante destro SQL'archivio del nuovo gruppo di disponibilità AlwaysOn e scegliere **Modifica proprietà.**
    
     - Nella parte inferiore della pagina, nella casella **SQL Server FQDN,** modificare il valore in FQDN del listener del gruppo di disponibilità.
    
   - Pubblicare la topologia. Scegliere **Topologia** dal menu Azione **e** quindi **Pubblica.** Nella pagina di conferma fare clic su **Avanti.** Attendere quindi alcuni minuti per la replica della nuova topologia.
    
   - Apri SQL Server Management Studio e passa al gruppo di disponibilità. Eseguire il failover su una replica secondaria.
    
   - Aprire Skype for Business Server Management Shell e digitare il cmdlet seguente per creare SQL account di accesso in questa replica:
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria, quindi utilizzare ) per  `Install-CsDatabase -Update` ogni replica del gruppo.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Distribuire un gruppo di disponibilità Always On in un pool esistente che utilizza il mirroring del database
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Se il pool che si sta aggiornando a un gruppo di disponibilità ospita l'archivio di gestione centrale per l'organizzazione, è necessario spostare il Servizio di gestione catalogo in un altro pool prima di aggiornare il pool. Utilizzare il cmdlet Move-CsManagementServer per spostare il pool. Se nell'organizzazione non è presente un altro pool, è possibile distribuire temporaneamente un server Standard Edition e spostare il server CMS in questo server prima di aggiornare il pool al gruppo di disponibilità. 
  
1. Eseguire il failover di tutti i dati dal mirror al nodo principale aprendo Skype for Business Server Management Shell e digitando il cmdlet seguente.
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    Ripetere questo cmdlet per ogni tipo di database nel pool. È possibile utilizzare il cmdlet seguente per trovare tutti i tipi di database archiviati nel pool.
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. Utilizzare Generatore di topologie per rimuovere il mirroring del database dal pool.
    
   - Apre lo strumento di generazione topologia Nella topologia espandere Pool **Enterprise Edition Front End,** fare clic con il pulsante destro del mouse sul nome del pool e scegliere **Modifica proprietà.**
    
   - Per ogni tipo di SQL di archiviazione nel pool, deselezionare la casella di controllo **SQL mirroring dello Store.**
    
3. Pubblicare la topologia modificata. Scegliere **Topologia** dal menu Azione **e** quindi **Pubblica.** Nella pagina di conferma fare clic su **Avanti**
    
4. Usa SQL Server Management Studio per interrompere il mirroring.
    
   - Aprire SQL Server Management Studio, accedere ai database, fare clic con il pulsante destro del mouse su **Attività** e scegliere **Mirror.** Fare clic **su Rimuovi mirroring** e quindi su **OK.**
    
   - Ripetere questa operazione per tutti i database del pool che verranno convertiti in un gruppo di disponibilità.
    
5. Configurare la funzionalità Clustering di failover in tutti i server di database che fanno parte del gruppo di disponibilità. In ogni server eseguire le operazioni seguenti
    
   - Aprire Server Manager e fare clic **su Aggiungi ruoli e funzionalità.**
    
   - Fare **clic su** Avanti fino a raggiungere la casella **Seleziona** funzionalità. In questo caso, selezionare la **casella di controllo Clustering** di failover.
    
   - Nella casella **Add features that are required for Failover Clustering?** fare clic su Add **Features.**
    
   - Fare clic su **Installa**.
    
6. Convalidare la configurazione del cluster.
    
   - In Server Manager scegliere Gestione **cluster** di failover dal menu **Strumenti.**
    
   - In **Azioni sul** lato destro dello schermo fare clic su Convalida **configurazione.**
    
   - Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.
    
   - Selezionare i server da aggiungere al cluster e quindi fare clic **su Esegui tutti i test.**
    
   - Nella casella **Riepilogo** controllare gli eventuali errori rilevati dalla procedura guidata. Fare quindi **clic su Fine** per completare la convalida.
    
     La procedura guidata probabilmente segnala diversi avvisi, soprattutto se non si utilizza l'archiviazione condivisa. Non è necessario utilizzare l'archiviazione condivisa. Tuttavia, se vengono visualizzati messaggi **di** errore, è necessario risolvere tali problemi prima di continuare.
    
7. Creare il cluster di failover di Windows Server.
    
   - Nella procedura **guidata Gestione cluster di failover** fare clic con il pulsante destro del mouse su Gestione cluster di **failover** e quindi scegliere **Crea cluster.**
    
   - Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.
    
   - Aggiungere il nome del cluster e l'indirizzo IP. Dopo la convalida delle impostazioni, fare clic su **Avanti.**
    
   - Nella pagina Conferma, fare clic su **Avanti**.
    
   - Dopo aver creato il cluster, fare clic su **Fine.**
    
8. È consigliabile configurare le impostazioni del quorum del cluster per l'utilizzo di un controllo della condivisione file. A tale scopo, eseguire la procedura seguente:
    
   - Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **Altre azioni** e fare clic su Configura impostazioni **quorum cluster.**
    
   - Nella pagina **Selezione opzione di configurazione quorum** fare clic su Seleziona il controllo del **quorum.**
    
   - Nella pagina **Selezione quorum di controllo** fare clic su Configura un controllo della condivisione **file.**
    
   - Nella pagina **Configura condivisione file di controllo** digitare il percorso della condivisione file che si desidera utilizzare e quindi fare clic su **Avanti.**
    
   - Nella pagina **Conferma**, fare clic su **Avanti**.
    
9. In ogni server del cluster abilitare la funzionalità Di gruppo di disponibilità in SQL Server Configuration Manager.
    
   - Aprire Gestione configurazione SQL Server. Nell'albero sul lato sinistro dello schermo fare clic su **SQL Server Servizi** e quindi fare doppio clic sul SQL Server servizio. 
    
   - Nella casella **Proprietà** selezionare la **scheda Disponibilità elevata AlwaysOn.** Selezionare la **casella di controllo Abilita gruppi di disponibilità AlwaysOn.** Riavviare SQL Server servizio quando richiesto.
    
10. Creare il gruppo di disponibilità.
    
    - Apri SQL Server Management Studio e connettiti all'SQL Server istanza.
    
    - In Esplora oggetti espandere la **cartella Disponibilità elevata Always On.** Fare clic con il pulsante destro **del** mouse sulla cartella Gruppi di disponibilità e scegliere **Creazione guidata nuovo gruppo di disponibilità.**
    
    - Se viene **visualizzata la** pagina Introduzione, fare clic su **Avanti.**
    
    - Nella pagina **Specifica nome gruppo di** disponibilità digitare il nome del gruppo di disponibilità e fare clic su **Avanti.**
    
    - Nella pagina Selezione database selezionare i database che si desidera includere nel gruppo di disponibilità AlwaysOn. Scegliere il pulsante **Avanti**.
    
    Non includere i **database ReportServer,** **ReportServerTempDB** o Persistent Chat nel gruppo di disponibilità AlwaysOn, in quanto non sono supportati in questo scenario. È possibile includere tutti gli altri database di Skype for Business Server nel gruppo di disponibilità AlwaysOn.
    
    - Nella pagina **Specifica repliche** fare clic sulla **scheda** Repliche. Fare quindi clic **sul pulsante Aggiungi** repliche e connettersi alle altre istanze SQL unite come nodi del cluster di failover di Windows Server.
    
    - Per ogni istanza, selezionare le **opzioni Failover automatico** e **Commit** sincrono. Non selezionare **l'opzione Secondaria leggibile.**
    
    - Fare clic **sulla scheda Endpoint** e verificare che il numero di **porta** sia impostato su 5022.
    
      - Fare clic **sulla scheda Listener** e selezionare l'opzione Crea listener del gruppo **di** disponibilità. In tale opzione digitare un nome per il listener e impostare **la** porta su 1433 (altre porte non sono supportate per questa opzione).
    
    - Fare **clic su** Aggiungi e quindi nella casella Indirizzo **IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK.**
    
    - Nella **pagina** Selezione sincronizzazione dati iniziale selezionare Completo e specificare una cartella accessibile alle repliche e per cui l'account di servizio SQL Server utilizzato da entrambe le repliche dispone delle autorizzazioni di scrittura. Scegliere il pulsante **Avanti**.
    
    Questa condivisione file verrà utilizzata temporaneamente quando si inizializzano i database. Se si gestiscono database di grandi dimensioni, è consigliabile inizializzarli manualmente nel caso in cui la larghezza di banda di rete non possa contenere le dimensioni dei backup dei database.
    
    - Nella pagina Convalida verificare che tutti i controlli di convalida siano stati eseguiti correttamente e quindi fare clic su **Avanti.**
    
    - Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su Fine.
    
11. Creare un nuovo archivio specificando il listener del gruppo di disponibilità del gruppo e specificare l'entità del mirror precedente come nodo primario del gruppo di disponibilità.
    
    - Apre lo strumento di generazione topologia Nella topologia espandere Componenti **condivisi,** fare clic con il pulsante destro **del mouse** su SQL Server archivi e scegliere Nuovo **SQL Server Store.**
    
    - Nella pagina Definisci nuovo **SQL Store** selezionare  innanzitutto la casella di controllo Impostazioni disponibilità elevata e quindi verificare che i gruppi di disponibilità AlwaysOn SQL siano visualizzati nella casella di riepilogo a discesa.
    
    - Nella casella **SQL Server FQDN listener** disponibilità digitare il nome di dominio completo del listener creato al momento della creazione del gruppo di disponibilità.
    
    - Nella casella **SQL Server FQDN** digitare l'FQDN del nodo primario del gruppo di disponibilità e quindi fare clic su **OK.** Deve essere l'entità del mirror precedente per questo archivio.
    
12. Associare il nuovo gruppo di disponibilità al pool Front End.
    
    - In Generatore di topologie fare clic con il pulsante destro del mouse sul pool da associare al gruppo di disponibilità e scegliere **Modifica proprietà.**
    
    - In **Associazioni,** nella casella SQL Server **Store,** selezionare il gruppo di disponibilità. Selezionare lo stesso gruppo per tutti gli altri database del pool che si desidera spostare nel gruppo di disponibilità.
    
    - Quando si è certi che tutti i database necessari siano impostati sul gruppo di disponibilità, fare clic su **OK.**
    
13. Pubblicare la topologia. Scegliere **Topologia** dal menu Azione **e** quindi **Pubblica.** Nella pagina di conferma fare clic su **Avanti.**
    
14. Eseguire alcuni passaggi finali per verificare che gli account SQL account di accesso siano presenti in ognuna delle repliche nel gruppo di disponibilità AlwaysOn.
    
    - Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente** e fare clic su **OK.**
    
    - Espandere Skype for Business Server, espandere la topologia ed espandere SQL Server **store.** Fare clic con il pulsante SQL'archivio del nuovo gruppo di disponibilità e scegliere **Modifica proprietà.**
    
    - Nella parte inferiore della pagina, nella casella **SQL Server FQDN,** modificare il valore in FQDN del listener del gruppo di disponibilità.
    
    - Pubblicare la topologia. Scegliere **Topologia** dal menu Azione **e** quindi **Pubblica.** Nella pagina di conferma fare clic su **Avanti.** Attendere quindi alcuni minuti per la replica della nuova topologia.
    
    - Apri SQL Server Management Studio e passa al gruppo di disponibilità. Eseguire il failover su una replica secondaria.
    
    - Aprire Skype for Business Server Management Shell e digitare il cmdlet seguente per creare SQL account di accesso in questa replica:
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria, quindi utilizzare ) per  `Install-CsDatabase -Update` ogni replica del gruppo.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Distribuire un gruppo di disponibilità Always On in un pool esistente che non utilizza il mirroring del database
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Se il pool che si sta aggiornando a un gruppo di disponibilità ospita l'archivio di gestione centrale per l'organizzazione, è necessario spostare il Servizio di gestione catalogo in un altro pool prima di aggiornare il pool. Utilizzare il cmdlet Move-CsManagementServer per spostare il pool. Se nell'organizzazione non è presente un altro pool, è possibile distribuire temporaneamente un server Standard Edition e spostare il server CMS in questo server prima di aggiornare il pool al gruppo di disponibilità. 
  
1. Configurare la funzionalità Clustering di failover in tutti i server di database che fanno parte del gruppo di disponibilità. In ogni server eseguire le operazioni seguenti
    
   - Aprire Server Manager e fare clic **su Aggiungi ruoli e funzionalità.**
    
   - Fare **clic su** Avanti fino a raggiungere la casella **Seleziona** funzionalità. In questo caso, selezionare la **casella di controllo Clustering** di failover.
    
   - Nella casella **Add features that are required for Failover Clustering?** fare clic su Add **Features.**
    
   - Fare clic su **Installa**.
    
2. Convalidare la configurazione del cluster.
    
   - In Server Manager scegliere Gestione **cluster** di failover dal menu **Strumenti.**
    
   - In **Azioni sul** lato destro dello schermo fare clic su Convalida **configurazione.**
    
   - Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.
    
   - Selezionare i server da aggiungere al cluster e quindi fare clic **su Esegui tutti i test.**
    
   - Nella casella **Riepilogo** controllare gli eventuali errori rilevati dalla procedura guidata. Fare quindi **clic su Fine** per completare la convalida.
    
     La procedura guidata probabilmente segnala diversi avvisi, soprattutto se non si utilizza l'archiviazione condivisa. Non è necessario utilizzare l'archiviazione condivisa. Tuttavia, se vengono visualizzati messaggi **di** errore, è necessario risolvere tali problemi prima di continuare.
    
3. Creare il cluster di failover di Windows Server (WSFC).
    
   - Nella procedura **guidata Gestione cluster di failover** fare clic con il pulsante destro del mouse su Gestione cluster di **failover** e quindi scegliere **Crea cluster.**
    
   - Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.
    
   - Aggiungere il nome del cluster e l'indirizzo IP. Dopo la convalida delle impostazioni, fare clic su **Avanti.**
    
   - Nella pagina Conferma, fare clic su **Avanti**.
    
   - Dopo aver creato il cluster, fare clic su **Fine.**
    
4. È consigliabile configurare le impostazioni del quorum del cluster per l'utilizzo di un controllo della condivisione file. A tale scopo, eseguire la procedura seguente:
    
   - Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **Altre azioni** e fare clic su Configura impostazioni **quorum cluster.**
    
   - Nella pagina **Selezione opzione di configurazione quorum** fare clic su Seleziona il controllo del **quorum.**
    
   - Nella pagina **Selezione quorum di controllo** fare clic su Configura un controllo della condivisione **file.**
    
   - Nella pagina **Configura condivisione file di controllo** digitare il percorso della condivisione file che si desidera utilizzare e quindi fare clic su **Avanti.**
    
   - Nella pagina **Conferma**, fare clic su **Avanti**.
    
5. In ogni server del cluster, abilitare Il gruppo di disponibilità in SQL Server Configuration Manager.
    
   - Aprire Gestione configurazione SQL Server. Nell'albero sul lato sinistro dello schermo fare clic su **SQL Server Servizi** e quindi fare doppio clic sul SQL Server servizio. 
    
   - Nella casella **Proprietà** selezionare la **scheda Disponibilità elevata AlwaysOn.** Selezionare la **casella di controllo Abilita gruppi di disponibilità AlwaysOn.** Riavviare SQL Server servizio quando richiesto.
    
6. Creare il gruppo di disponibilità.
    
   - Apri SQL Server Management Studio e connettiti all'SQL Server istanza.
    
   - In Esplora oggetti espandere la **cartella Disponibilità elevata Always On.** Fare clic con il pulsante destro **del** mouse sulla cartella Gruppi di disponibilità e scegliere **Creazione guidata nuovo gruppo di disponibilità.**
    
   - Se viene **visualizzata la** pagina Introduzione, fare clic su **Avanti.**
    
   - Nella pagina **Specifica nome gruppo di** disponibilità digitare il nome del gruppo di disponibilità e fare clic su **Avanti.**
    
   - Nella pagina Selezione database selezionare i database che si desidera includere nel gruppo di disponibilità. Scegliere il pulsante **Avanti**.
    
     Non includere i **database ReportServer,** **ReportServerTempDB** o Persistent Chat nel gruppo di disponibilità, in quanto non sono supportati in questo scenario. È possibile includere tutti gli altri database di Skype for Business Server nel gruppo di disponibilità.
    
   - Nella pagina **Specifica repliche** fare clic sulla **scheda** Repliche. Fare quindi clic **sul pulsante Aggiungi** repliche e connettersi alle altre istanze SQL unite come nodi di WSFC.
    
   - Per ogni istanza, selezionare le **opzioni Failover automatico** e **Commit** sincrono. Non selezionare **l'opzione Secondaria leggibile.**
    
   - Fare clic **sulla scheda Endpoint** e verificare che il numero di **porta** sia impostato su 5022.
    
   - Fare clic **sulla scheda Listener** e selezionare l'opzione Crea listener del gruppo **di** disponibilità. In tale opzione digitare un nome per il listener e impostare **la** porta su 1433 (altre porte non sono supportate per questa opzione).
    
   - Fare **clic su** Aggiungi e quindi nella casella Indirizzo **IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK.**
    
   - Nella **pagina** Selezione sincronizzazione dati iniziale selezionare Completo e specificare una cartella accessibile alle repliche e per cui l'account di servizio SQL Server utilizzato da entrambe le repliche dispone delle autorizzazioni di scrittura. Scegliere il pulsante **Avanti**.
    
     Questa condivisione file verrà utilizzata temporaneamente quando si inizializzano i database. Se si gestiscono database di grandi dimensioni, è consigliabile inizializzarli manualmente nel caso in cui la larghezza di banda di rete non possa contenere le dimensioni dei backup dei database.
    
     - Nella pagina Convalida verificare che tutti i controlli di convalida siano stati eseguiti correttamente e quindi fare clic su **Avanti.**
    
   - Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su Fine.
    
7. Creare un nuovo archivio specificando il listener di criteri di gruppo.
    
   - Apre lo strumento di generazione topologia Nella topologia espandere Componenti **condivisi,** fare clic con il pulsante destro **del mouse** su SQL Server archivi e scegliere Nuovo **SQL Server Store.**
    
   - Nella pagina Definisci nuovo **SQL Store** selezionare  innanzitutto la casella di controllo Impostazioni disponibilità elevata e quindi verificare che i gruppi di disponibilità AlwaysOn SQL siano visualizzati nella casella di riepilogo a discesa.
    
   - Nella casella **SQL Server FQDN listener** disponibilità digitare il nome di dominio completo del listener creato al momento della creazione del gruppo di disponibilità.
    
   - Nella casella **SQL Server FQDN** digitare l'FQDN del nodo primario del gruppo di disponibilità e quindi fare clic su **OK.**
    
8. Associare il nuovo gruppo di disponibilità Always On al pool Front End.
    
   - In Generatore di topologie fare clic con il pulsante destro del mouse sul pool da associare al gruppo di disponibilità e scegliere **Modifica proprietà.**
    
   - In **Associazioni,** nella casella SQL Server **Store,** selezionare il gruppo di disponibilità. Selezionare lo stesso gruppo per tutti gli altri database del pool che si desidera spostare nel gruppo di disponibilità.
    
   - Quando si è certi che tutti i database necessari siano impostati sul gruppo di disponibilità, fare clic su **OK.**
    
9. Pubblicare la topologia. Scegliere **Topologia** dal menu Azione **e** quindi **Pubblica.** Nella pagina di conferma fare clic su **Avanti.**
    
10. Eseguire alcuni passaggi finali per verificare che gli account SQL account di accesso siano presenti in ognuna delle repliche nel gruppo di disponibilità.
    
    - Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente** e fare clic su **OK.**
    
    - Espandere Skype for Business Server, espandere la topologia ed espandere SQL Server **store.** Fare clic con il pulsante SQL'archivio del nuovo gruppo di disponibilità e scegliere **Modifica proprietà.**
    
    - Nella parte inferiore della pagina, nella casella **SQL Server FQDN,** modificare il valore in FQDN del listener del gruppo di disponibilità.
    
    - Pubblicare la topologia. Scegliere **Topologia** dal menu Azione **e** quindi **Pubblica.** Nella pagina di conferma fare clic su **Avanti.** Attendere quindi alcuni minuti per la replica della nuova topologia.
    
    - Apri SQL Server Management Studio e passa al gruppo di disponibilità. Eseguire il failover su una replica secondaria.
    
    - Aprire Skype for Business Server Management Shell e digitare il cmdlet seguente per creare SQL account di accesso in questa replica:
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria, quindi utilizzare ) per  `Install-CsDatabase -Update` ogni replica del gruppo.
