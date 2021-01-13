---
title: Distribuire un gruppo di disponibilità sempre su un server back-end in Skype for Business Server
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
description: Distribuire (installare) un gruppo di disponibilità sempre presente nella distribuzione di Skype for Business Server.
ms.openlocfilehash: 83565efe850570ac5ab9a0695757e708f3eae566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830656"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a>Distribuire un gruppo di disponibilità sempre su un server back-end in Skype for Business Server
 
Distribuire (installare) un gruppo di disponibilità sempre disponibile (AG) nella distribuzione di Skype for Business Server.
  
La modalità di distribuzione di un AG varia a seconda che la distribuzione venga distribuita in un nuovo pool, in un pool esistente che utilizza il mirroring o in un pool esistente che attualmente non dispone di disponibilità elevata per il database back-end.
  
> [!NOTE]
> L'utilizzo di un componente AG con un ruolo del server Chat persistente non è supportato. 
  
- [Distribuire un gruppo di disponibilità sempre su un nuovo pool Front End](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Distribuire un gruppo di disponibilità sempre su un pool esistente che utilizza il mirroring del database](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Distribuire un gruppo di disponibilità sempre su un pool esistente che non utilizza il mirroring del database](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a>Distribuire un gruppo di disponibilità sempre su un nuovo pool Front End
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Abilitare la funzionalità di clustering di failover in tutti i server di database che faranno parte dell'AG. In ogni server, eseguire le operazioni seguenti:
    
   - Aprire Server Manager e fare clic su **Aggiungi ruoli e funzionalità**.
    
   - Fare clic su **Avanti** fino a raggiungere la casella **Seleziona funzionalità** . Selezionare la casella di controllo **clustering di failover** .
    
   - Nella casella **Aggiungi funzionalità necessarie per il clustering di failover** fare clic su **Aggiungi funzionalità**.
    
   - Fare clic su **Installa**.
    
2. Convalidare la configurazione del cluster.
    
   - In Server Manager, fare clic sul menu **strumenti** , quindi fare clic su **Gestione cluster di failover**.
    
   - In **azioni** nella parte destra dello schermo fare clic su **Convalida configurazione**.
    
   - Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.
    
   - Selezionare i server da aggiungere al cluster e quindi fare clic su **Esegui tutti i test**.
    
   - Nella casella **Riepilogo** controllare gli eventuali errori segnalati dalla procedura guidata. Quindi fare clic su **fine** per completare la convalida.
    
     La procedura guidata riporterà probabilmente diversi avvisi, soprattutto se non si utilizza l'archiviazione condivisa. Non è necessario utilizzare l'archiviazione condivisa. Tuttavia, se vengono visualizzati messaggi di **errore** , è necessario correggere tali problemi prima di continuare.
    
3. Creare il cluster di failover di Windows Server (WSFC).
    
   - Nella procedura guidata **Gestione cluster di failover** fare clic con il pulsante destro del mouse su **Gestione cluster di failover** e quindi scegliere **Crea cluster**.
    
   - Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.
    
   - Aggiungere il nome del cluster e l'indirizzo IP. Quando le impostazioni vengono convalidate, fare clic su **Avanti**.
    
   - Nella pagina Conferma, fare clic su **Avanti**.
    
   - Dopo aver creato il cluster, fare clic su **fine**.
    
4. Si consiglia di configurare le impostazioni di quorum del cluster per l'utilizzo di un witness di condivisione file. A tale scopo, eseguire la procedura seguente:
    
   - Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **altre azioni** e quindi **configurare le impostazioni di quorum del cluster**.
    
   - Nella pagina **Seleziona opzione di configurazione quorum** fare clic su **Seleziona il controllo quorum**.
    
   - Nella pagina **Seleziona controllo quorum** fare clic su **configura un witness di condivisione file**.
    
   - Nella pagina **Configura testimone condivisione file** Digitare il percorso della condivisione di file che si desidera utilizzare e quindi fare clic su **Avanti**.
    
   - Nella pagina **Conferma**, fare clic su **Avanti**.
    
5. In ogni server del cluster abilitare la funzionalità AG in Gestione configurazione SQL Server.
    
   - Aprire Gestione configurazione SQL Server. Nell'albero a sinistra dello schermo fare clic su **servizi SQL Server** e quindi fare doppio clic sul servizio SQL Server. 
    
   - Nella casella **Proprietà** selezionare la scheda **disponibilità elevata AlwaysOn** . Selezionare la casella di controllo **Abilita gruppi di disponibilità AlwaysOn** . Quando richiesto, riavviare il servizio SQL Server.
   
6. Utilizzare Generatore di topologie per creare il pool Front End, come spiegato in [creare e pubblicare una nuova topologia in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md). Quando si esegue questa operazione, specificare l'AG come archivio SQL per il pool.
    
7. Creare il gruppo di disponibilità.
    
   - Aprire SQL Server Management Studio e connettersi all'istanza di SQL Server.
    
   - In Esplora oggetti espandere la cartella **Always on High Availability** . Fare clic con il pulsante destro del mouse sulla cartella **gruppi di disponibilità** e scegliere **nuova procedura guidata gruppo di disponibilità**.
    
   - Se viene visualizzata la pagina **Introduzione** , fare clic su **Avanti**.
    
   - Nella pagina **specificare il nome del gruppo di disponibilità** , digitare il nome del gruppo di disponibilità e fare clic su **Avanti**.
    
   - Nella pagina Seleziona database selezionare i database che si desidera includere nel gruppo di disponibilità AlwaysOn. Scegliere il pulsante **Avanti**.
    
     Non includere i database **ReportServer**, **ReportServerTempDB** o Persistent Chat nel gruppo di disponibilità AlwaysOn, in quanto questi non sono supportati in questo scenario. È possibile includere tutti gli altri database di Skype for Business Server nel gruppo di disponibilità AlwaysOn.
    
   - Nella pagina **Specifica repliche** fare clic sulla scheda **repliche** . Fare quindi clic sul pulsante **Aggiungi repliche** e connettersi alle altre istanze di SQL aggiunte come nodi del cluster di failover di Windows Server.
    
   - Per ogni istanza, selezionare il **failover automatico** e le opzioni di **commit sincrono** . Non selezionare l'opzione **secondaria leggibile** .
    
   - Fare clic sulla scheda **endpoint** e verificare che il **numero di porta** sia impostato su 5022.
    
   - Fare clic sulla scheda **listener** e selezionare l'opzione **Crea un listener del gruppo di disponibilità** . In tale opzione digitare un nome per il listener e impostare la **porta** su 1433 (altre porte non sono supportate per questa opzione).
    
   - Fare clic su **Aggiungi**, quindi nella casella **indirizzo IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK**.
    
   - Nella pagina **Seleziona sincronizzazione dati iniziale** selezionare completo e specificare una cartella accessibile alle repliche e che l'account di servizio di SQL Server utilizzato da entrambe le repliche disponga delle autorizzazioni di scrittura per. Scegliere il pulsante **Avanti**.
    
     Questa condivisione file verrà utilizzata temporaneamente quando si inizializzano i database. Se si ha a che fare con database di grandi dimensioni, è consigliabile inizializzarli manualmente se la larghezza di banda di rete non è in grado di soddisfare le dimensioni dei backup del database.
    
   - Nella pagina Convalida verificare che tutti i controlli di convalida siano stati eseguiti correttamente e quindi fare clic su **Avanti**.
    
   - Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su fine.
      
8. Dopo che il pool e l'AG sono stati distribuiti, eseguire alcuni passaggi finali per assicurarsi che gli account di accesso di SQL siano su ognuna delle repliche del gruppo di disponibilità AlwaysOn. 
    
   - Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente** e fare clic su **OK**.
    
   - Espandi Skype for Business Server, Espandi la topologia ed Espandi gli **archivi di SQL Server**. Fare clic con il pulsante destro del mouse sull'archivio SQL del nuovo gruppo di disponibilità AlwaysOn e scegliere **modifica proprietà**.
    
     - Nella parte inferiore della pagina, nella casella **FQDN di SQL Server** , impostare il valore sul nome di dominio completo del listener dell'AG.
    
   - Pubblicare la topologia. Dal menu **azione** fare clic su **topologia** e quindi su **pubblica**. Nella pagina di conferma fare clic su **Avanti**. Attendere quindi alcuni minuti per la replica della nuova topologia.
    
   - Aprire SQL Server Management Studio e passare all'AG. Eseguire il failover su una replica secondaria.
    
   - Aprire Skype for Business Server Management Shell e digitare il seguente cmdlet per creare gli account di accesso di SQL in questa replica:
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria e quindi utilizzare  `Install-CsDatabase -Update` ) per ogni replica del gruppo.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Distribuire un gruppo di disponibilità sempre su un pool esistente che utilizza il mirroring del database
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Se il pool in cui si esegue l'aggiornamento a un AG ospita l'archivio di gestione centrale per l'organizzazione, è necessario prima di tutto spostare il CMS in un altro pool prima di aggiornare questo pool. Utilizzare il cmdlet Move-CsManagementServer per spostare il pool. Se non si dispone di un altro pool nell'organizzazione, è possibile distribuire temporaneamente un server Standard Edition e spostare il CMS in questo server prima di eseguire l'aggiornamento del pool all'AG. 
  
1. Eseguire il failover di tutti i dati dal mirror al nodo principale aprendo Skype for Business Server Management Shell e digitando il cmdlet seguente.
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    Ripetere questo cmdlet per ogni tipo di database del pool. È possibile utilizzare il cmdlet seguente per individuare tutti i tipi di database archiviati in questo pool.
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. Utilizzare Generatore di topologie per rimuovere il mirroring del database dal pool.
    
   - Apre lo strumento di generazione topologia Nella topologia espandere **pool Enterprise Edition front end**, fare clic con il pulsante destro del mouse sul nome del pool e quindi scegliere **modifica proprietà**.
    
   - Per ogni tipo di archivio SQL nel pool, deselezionare la casella di controllo **Abilita mirroring dell'archivio SQL** .
    
3. Pubblicare la topologia modificata. Dal menu **azione** fare clic su **topologia** e quindi su **pubblica**. Quindi nella pagina di conferma fare clic su **Avanti**
    
4. Utilizzare SQL Server Management Studio per interrompere il mirroring.
    
   - Aprire SQL Server Management Studio, accedere ai database, fare clic con il pulsante destro del mouse su **attività** e scegliere **mirror**. Quindi fare clic su **Rimuovi mirroring** e fare clic su **OK**.
    
   - Ripetere questa operazione per tutti i database del pool che verranno convertiti in un AG.
    
5. Configurare la funzionalità di clustering di failover in tutti i server di database che faranno parte dell'AG. In ogni server, eseguire le operazioni seguenti:
    
   - Aprire Server Manager e fare clic su **Aggiungi ruoli e funzionalità**.
    
   - Fare clic su **Avanti** fino a raggiungere la casella **Seleziona funzionalità** . Selezionare la casella di controllo **clustering di failover** .
    
   - Nella casella **Aggiungi funzionalità necessarie per il clustering di failover** fare clic su **Aggiungi funzionalità**.
    
   - Fare clic su **Installa**.
    
6. Convalidare la configurazione del cluster.
    
   - In Server Manager, fare clic sul menu **strumenti** , quindi fare clic su **Gestione cluster di failover**.
    
   - In **azioni** nella parte destra dello schermo fare clic su **Convalida configurazione**.
    
   - Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.
    
   - Selezionare i server da aggiungere al cluster e quindi fare clic su **Esegui tutti i test**.
    
   - Nella casella **Riepilogo** controllare gli eventuali errori segnalati dalla procedura guidata. Quindi fare clic su **fine** per completare la convalida.
    
     La procedura guidata riporterà probabilmente diversi avvisi, soprattutto se non si utilizza l'archiviazione condivisa. Non è necessario utilizzare l'archiviazione condivisa. Tuttavia, se vengono visualizzati messaggi di **errore** , è necessario correggere tali problemi prima di continuare.
    
7. Creare il cluster di failover di Windows Server.
    
   - Nella procedura guidata **Gestione cluster di failover** fare clic con il pulsante destro del mouse su **Gestione cluster di failover** e quindi scegliere **Crea cluster**.
    
   - Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.
    
   - Aggiungere il nome del cluster e l'indirizzo IP. Quando le impostazioni vengono convalidate, fare clic su **Avanti**.
    
   - Nella pagina Conferma, fare clic su **Avanti**.
    
   - Dopo aver creato il cluster, fare clic su **fine**.
    
8. Si consiglia di configurare le impostazioni di quorum del cluster per l'utilizzo di un witness di condivisione file. A tale scopo, eseguire la procedura seguente:
    
   - Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **altre azioni** e quindi **configurare le impostazioni di quorum del cluster**.
    
   - Nella pagina **Seleziona opzione di configurazione quorum** fare clic su **Seleziona il controllo quorum**.
    
   - Nella pagina **Seleziona controllo quorum** fare clic su **configura un witness di condivisione file**.
    
   - Nella pagina **Configura testimone condivisione file** Digitare il percorso della condivisione di file che si desidera utilizzare e quindi fare clic su **Avanti**.
    
   - Nella pagina **Conferma**, fare clic su **Avanti**.
    
9. In ogni server del cluster abilitare la funzionalità AG in Gestione configurazione SQL Server.
    
   - Aprire Gestione configurazione SQL Server. Nell'albero a sinistra dello schermo fare clic su **servizi SQL Server** e quindi fare doppio clic sul servizio SQL Server. 
    
   - Nella casella **Proprietà** selezionare la scheda **disponibilità elevata AlwaysOn** . Selezionare la casella di controllo **Abilita gruppi di disponibilità AlwaysOn** . Quando richiesto, riavviare il servizio SQL Server.
    
10. Creare il gruppo di disponibilità.
    
    - Aprire SQL Server Management Studio e connettersi all'istanza di SQL Server.
    
    - In Esplora oggetti espandere la cartella **Always on High Availability** . Fare clic con il pulsante destro del mouse sulla cartella **gruppi di disponibilità** e scegliere **nuova procedura guidata gruppo di disponibilità**.
    
    - Se viene visualizzata la pagina **Introduzione** , fare clic su **Avanti**.
    
    - Nella pagina **specificare il nome del gruppo di disponibilità** , digitare il nome del gruppo di disponibilità e fare clic su **Avanti**.
    
    - Nella pagina Seleziona database selezionare i database che si desidera includere nel gruppo di disponibilità AlwaysOn. Scegliere il pulsante **Avanti**.
    
    Non includere i database **ReportServer**, **ReportServerTempDB** o Persistent Chat nel gruppo di disponibilità AlwaysOn, in quanto questi non sono supportati in questo scenario. È possibile includere tutti gli altri database di Skype for Business Server nel gruppo di disponibilità AlwaysOn.
    
    - Nella pagina **Specifica repliche** fare clic sulla scheda **repliche** . Fare quindi clic sul pulsante **Aggiungi repliche** e connettersi alle altre istanze di SQL aggiunte come nodi del cluster di failover di Windows Server.
    
    - Per ogni istanza, selezionare il **failover automatico** e le opzioni di **commit sincrono** . Non selezionare l'opzione **secondaria leggibile** .
    
    - Fare clic sulla scheda **endpoint** e verificare che il **numero di porta** sia impostato su 5022.
    
      - Fare clic sulla scheda **listener** e selezionare l'opzione **Crea un listener del gruppo di disponibilità** . In tale opzione digitare un nome per il listener e impostare la **porta** su 1433 (altre porte non sono supportate per questa opzione).
    
    - Fare clic su **Aggiungi**, quindi nella casella **indirizzo IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK**.
    
    - Nella pagina **Seleziona sincronizzazione dati iniziale** selezionare completo e specificare una cartella accessibile alle repliche e che l'account di servizio di SQL Server utilizzato da entrambe le repliche disponga delle autorizzazioni di scrittura per. Scegliere il pulsante **Avanti**.
    
    Questa condivisione file verrà utilizzata temporaneamente quando si inizializzano i database. Se si ha a che fare con database di grandi dimensioni, è consigliabile inizializzarli manualmente se la larghezza di banda di rete non è in grado di soddisfare le dimensioni dei backup del database.
    
    - Nella pagina Convalida verificare che tutti i controlli di convalida siano stati eseguiti correttamente e quindi fare clic su **Avanti**.
    
    - Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su fine.
    
11. Creare un nuovo archivio specificando il listener AG e specificando il principale del mirror precedente come nodo primario dell'AG.
    
    - Apre lo strumento di generazione topologia Nella topologia espandere **componenti condivisi**, fare clic con il pulsante destro del mouse su **Archivi SQL Server** e scegliere **nuovo archivio SQL Server**.
    
    - Nella pagina **Definisci nuovo archivio SQL** selezionare la casella di controllo **Impostazioni disponibilità elevata** e quindi verificare che nella casella a discesa vengano visualizzati i gruppi di disponibilità di SQL AlwaysOn.
    
    - Nella casella **nome di dominio completo listener di disponibilità di SQL Server** Digitare il nome di dominio completo del listener creato durante la creazione del gruppo di disponibilità.
    
    - Nella casella **FQDN di SQL Server** , digitare il nome di dominio completo del nodo primario dell'AG, quindi fare clic su **OK**. Questo dovrebbe essere l'entità del mirror precedente per questo archivio.
    
12. Associare la nuova AG al pool Front end.
    
    - In Generatore di topologie fare clic con il pulsante destro del mouse sul pool da associare all'AG e quindi scegliere **modifica proprietà**.
    
    - In **associazioni**, nella casella **Archivio SQL Server** Selezionare l'AG. Selezionare lo stesso gruppo per qualsiasi altro database del pool che si desidera spostare nell'AG.
    
    - Quando si è certi che tutti i database necessari sono impostati sull'AG, fare clic su **OK**.
    
13. Pubblicare la topologia. Dal menu **azione** fare clic su **topologia** e quindi su **pubblica**. Nella pagina di conferma fare clic su **Avanti**.
    
14. Eseguire alcuni passaggi finali per assicurarsi che gli account di accesso di SQL siano su ognuna delle repliche del gruppo di disponibilità AlwaysOn.
    
    - Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente** e fare clic su **OK**.
    
    - Espandi Skype for Business Server, Espandi la topologia ed Espandi gli **archivi di SQL Server**. Fare clic con il pulsante destro del mouse sull'archivio SQL della nuova AG e scegliere **modifica proprietà**.
    
    - Nella parte inferiore della pagina, nella casella **FQDN di SQL Server** , impostare il valore sul nome di dominio completo del listener dell'AG.
    
    - Pubblicare la topologia. Dal menu **azione** fare clic su **topologia** e quindi su **pubblica**. Nella pagina di conferma fare clic su **Avanti**. Attendere quindi alcuni minuti per la replica della nuova topologia.
    
    - Aprire SQL Server Management Studio e passare all'AG. Eseguire il failover su una replica secondaria.
    
    - Aprire Skype for Business Server Management Shell e digitare il seguente cmdlet per creare gli account di accesso di SQL in questa replica:
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria e quindi utilizzare  `Install-CsDatabase -Update` ) per ogni replica del gruppo.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Distribuire un gruppo di disponibilità sempre su un pool esistente che non utilizza il mirroring del database
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Se il pool in cui si esegue l'aggiornamento a un AG ospita l'archivio di gestione centrale per l'organizzazione, è necessario prima di tutto spostare il CMS in un altro pool prima di aggiornare questo pool. Utilizzare il cmdlet Move-CsManagementServer per spostare il pool. Se non si dispone di un altro pool nell'organizzazione, è possibile distribuire temporaneamente un server Standard Edition e spostare il CMS in questo server prima di eseguire l'aggiornamento del pool all'AG. 
  
1. Configurare la funzionalità di clustering di failover in tutti i server di database che faranno parte dell'AG. In ogni server, eseguire le operazioni seguenti:
    
   - Aprire Server Manager e fare clic su **Aggiungi ruoli e funzionalità**.
    
   - Fare clic su **Avanti** fino a raggiungere la casella **Seleziona funzionalità** . Selezionare la casella di controllo **clustering di failover** .
    
   - Nella casella **Aggiungi funzionalità necessarie per il clustering di failover** fare clic su **Aggiungi funzionalità**.
    
   - Fare clic su **Installa**.
    
2. Convalidare la configurazione del cluster.
    
   - In Server Manager, fare clic sul menu **strumenti** , quindi fare clic su **Gestione cluster di failover**.
    
   - In **azioni** nella parte destra dello schermo fare clic su **Convalida configurazione**.
    
   - Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.
    
   - Selezionare i server da aggiungere al cluster e quindi fare clic su **Esegui tutti i test**.
    
   - Nella casella **Riepilogo** controllare gli eventuali errori segnalati dalla procedura guidata. Quindi fare clic su **fine** per completare la convalida.
    
     La procedura guidata riporterà probabilmente diversi avvisi, soprattutto se non si utilizza l'archiviazione condivisa. Non è necessario utilizzare l'archiviazione condivisa. Tuttavia, se vengono visualizzati messaggi di **errore** , è necessario correggere tali problemi prima di continuare.
    
3. Creare il cluster di failover di Windows Server (WSFC).
    
   - Nella procedura guidata **Gestione cluster di failover** fare clic con il pulsante destro del mouse su **Gestione cluster di failover** e quindi scegliere **Crea cluster**.
    
   - Sulla pagina **Informazioni preliminari**, fare clic su **Avanti**.
    
   - Aggiungere il nome del cluster e l'indirizzo IP. Quando le impostazioni vengono convalidate, fare clic su **Avanti**.
    
   - Nella pagina Conferma, fare clic su **Avanti**.
    
   - Dopo aver creato il cluster, fare clic su **fine**.
    
4. Si consiglia di configurare le impostazioni di quorum del cluster per l'utilizzo di un witness di condivisione file. A tale scopo, eseguire la procedura seguente:
    
   - Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **altre azioni** e quindi **configurare le impostazioni di quorum del cluster**.
    
   - Nella pagina **Seleziona opzione di configurazione quorum** fare clic su **Seleziona il controllo quorum**.
    
   - Nella pagina **Seleziona controllo quorum** fare clic su **configura un witness di condivisione file**.
    
   - Nella pagina **Configura testimone condivisione file** Digitare il percorso della condivisione di file che si desidera utilizzare e quindi fare clic su **Avanti**.
    
   - Nella pagina **Conferma**, fare clic su **Avanti**.
    
5. In ogni server del cluster abilitare l'AG in Gestione configurazione SQL Server.
    
   - Aprire Gestione configurazione SQL Server. Nell'albero a sinistra dello schermo fare clic su **servizi SQL Server** e quindi fare doppio clic sul servizio SQL Server. 
    
   - Nella casella **Proprietà** selezionare la scheda **disponibilità elevata AlwaysOn** . Selezionare la casella di controllo **Abilita gruppi di disponibilità AlwaysOn** . Quando richiesto, riavviare il servizio SQL Server.
    
6. Creare il gruppo di disponibilità.
    
   - Aprire SQL Server Management Studio e connettersi all'istanza di SQL Server.
    
   - In Esplora oggetti espandere la cartella **Always on High Availability** . Fare clic con il pulsante destro del mouse sulla cartella **gruppi di disponibilità** e scegliere **nuova procedura guidata gruppo di disponibilità**.
    
   - Se viene visualizzata la pagina **Introduzione** , fare clic su **Avanti**.
    
   - Nella pagina **specificare il nome del gruppo di disponibilità** , digitare il nome del gruppo di disponibilità e fare clic su **Avanti**.
    
   - Nella pagina Seleziona database selezionare i database che si desidera includere nell'AG. Scegliere il pulsante **Avanti**.
    
     Non includere i database **ReportServer**, **ReportServerTempDB** o Persistent Chat nell'AG, in quanto questi non sono supportati in questo scenario. È possibile includere tutti gli altri database di Skype for Business Server nell'AG.
    
   - Nella pagina **Specifica repliche** fare clic sulla scheda **repliche** . Fare quindi clic sul pulsante **Aggiungi repliche** e connettersi alle altre istanze di SQL aggiunte come nodi di WSFC.
    
   - Per ogni istanza, selezionare il **failover automatico** e le opzioni di **commit sincrono** . Non selezionare l'opzione **secondaria leggibile** .
    
   - Fare clic sulla scheda **endpoint** e verificare che il **numero di porta** sia impostato su 5022.
    
   - Fare clic sulla scheda **listener** e selezionare l'opzione **Crea un listener del gruppo di disponibilità** . In tale opzione digitare un nome per il listener e impostare la **porta** su 1433 (altre porte non sono supportate per questa opzione).
    
   - Fare clic su **Aggiungi**, quindi nella casella **indirizzo IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK**.
    
   - Nella pagina **Seleziona sincronizzazione dati iniziale** selezionare completo e specificare una cartella accessibile alle repliche e che l'account di servizio di SQL Server utilizzato da entrambe le repliche disponga delle autorizzazioni di scrittura per. Scegliere il pulsante **Avanti**.
    
     Questa condivisione file verrà utilizzata temporaneamente quando si inizializzano i database. Se si ha a che fare con database di grandi dimensioni, è consigliabile inizializzarli manualmente se la larghezza di banda di rete non è in grado di soddisfare le dimensioni dei backup del database.
    
     - Nella pagina Convalida verificare che tutti i controlli di convalida siano stati eseguiti correttamente e quindi fare clic su **Avanti**.
    
   - Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su fine.
    
7. Creare un nuovo archivio che specifichi il listener AG.
    
   - Apre lo strumento di generazione topologia Nella topologia espandere **componenti condivisi**, fare clic con il pulsante destro del mouse su **Archivi SQL Server** e scegliere **nuovo archivio SQL Server**.
    
   - Nella pagina **Definisci nuovo archivio SQL** selezionare la casella di controllo **Impostazioni disponibilità elevata** e quindi verificare che nella casella a discesa vengano visualizzati i gruppi di disponibilità di SQL AlwaysOn.
    
   - Nella casella **nome di dominio completo listener di disponibilità di SQL Server** Digitare il nome di dominio completo del listener creato durante la creazione del gruppo di disponibilità.
    
   - Nella casella **FQDN di SQL Server** , digitare il nome di dominio completo del nodo primario dell'AG, quindi fare clic su **OK**.
    
8. Associare il nuovo gruppo di disponibilità sempre con il pool Front end.
    
   - In Generatore di topologie fare clic con il pulsante destro del mouse sul pool da associare all'AG e quindi scegliere **modifica proprietà**.
    
   - In **associazioni**, nella casella **Archivio SQL Server** Selezionare l'AG. Selezionare lo stesso gruppo per qualsiasi altro database del pool che si desidera spostare nell'AG.
    
   - Quando si è certi che tutti i database necessari sono impostati sull'AG, fare clic su **OK**.
    
9. Pubblicare la topologia. Dal menu **azione** fare clic su **topologia** e quindi su **pubblica**. Nella pagina di conferma fare clic su **Avanti**.
    
10. Eseguire alcuni passaggi finali per assicurarsi che gli account di accesso di SQL siano su ognuna delle repliche nell'AG.
    
    - Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente** e fare clic su **OK**.
    
    - Espandi Skype for Business Server, Espandi la topologia ed Espandi gli **archivi di SQL Server**. Fare clic con il pulsante destro del mouse sull'archivio SQL della nuova AG e scegliere **modifica proprietà**.
    
    - Nella parte inferiore della pagina, nella casella **FQDN di SQL Server** , impostare il valore sul nome di dominio completo del listener dell'AG.
    
    - Pubblicare la topologia. Dal menu **azione** fare clic su **topologia** e quindi su **pubblica**. Nella pagina di conferma fare clic su **Avanti**. Attendere quindi alcuni minuti per la replica della nuova topologia.
    
    - Aprire SQL Server Management Studio e passare all'AG. Eseguire il failover su una replica secondaria.
    
    - Aprire Skype for Business Server Management Shell e digitare il seguente cmdlet per creare gli account di accesso di SQL in questa replica:
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria e quindi utilizzare  `Install-CsDatabase -Update` ) per ogni replica del gruppo.
