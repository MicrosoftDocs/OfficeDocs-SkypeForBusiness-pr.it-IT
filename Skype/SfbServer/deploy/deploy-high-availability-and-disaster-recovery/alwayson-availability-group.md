---
title: Distribuire un gruppo di disponibilità sempre in un server back-end in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Distribuire (installare) un gruppo sempre disponibile nella distribuzione di Skype for Business Server.
ms.openlocfilehash: eadf3c67f5d2618d7070c2a3540c2a9ad08b5942
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002916"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a>Distribuire un gruppo di disponibilità sempre in un server back-end in Skype for Business Server
 
Deploy (Install) Always on Availability Group (AG) nella distribuzione di Skype for Business Server.
  
La modalità di distribuzione di un AG varia a seconda che la distribuzione venga distribuita in un nuovo pool, in un pool esistente che usa il mirroring o in un pool esistente che attualmente non ha una disponibilità elevata per il database back-end.
  
> [!NOTE]
> L'uso di un AG con un ruolo del server di chat persistente non è supportato. 
  
- [Distribuire un gruppo di disponibilità sempre in un nuovo pool Front-End](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Distribuire un gruppo di disponibilità sempre disponibile in un pool esistente che usa il mirroring del database](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Distribuire un gruppo di disponibilità sempre disponibile in un pool esistente che non usa il mirroring del database](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a>Distribuire un gruppo di disponibilità sempre in un nuovo pool Front-End
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Abilitare la caratteristica clustering di failover in tutti i server di database che faranno parte dell'AG. In ogni server eseguire le operazioni seguenti
    
   - Aprire Server Manager e fare clic su **Aggiungi ruoli e funzionalità**.
    
   - Fare clic su **Avanti** fino a raggiungere la casella **Seleziona funzionalità** . Selezionare la casella di controllo **clustering di failover** .
    
   - Nella casella **Aggiungi funzionalità necessarie per il clustering di failover** fare clic su **Aggiungi funzionalità**.
    
   - Fare clic su **Installa**.
    
2. Convalidare la configurazione del cluster.
    
   - In Server Manager fare clic sul menu **strumenti** e quindi su **Gestione cluster di failover**.
    
   - In **azioni** sul lato destro dello schermo fare clic su **Convalida configurazione**.
    
   - Nella pagina **prima di iniziare** fare clic su **Avanti**.
    
   - Selezionare i server da aggiungere al cluster e quindi fare clic su **Esegui tutti i test**.
    
   - Nella casella **Riepilogo** verificare gli eventuali errori segnalati dalla procedura guidata. Quindi fare clic su **fine** per completare la convalida.
    
     La procedura guidata riporterà probabilmente diversi avvisi, soprattutto se non si usa lo spazio di archiviazione condiviso. Non è necessario usare lo spazio di archiviazione condiviso. Tuttavia, se vengono visualizzati messaggi di **errore** , è necessario correggere questi problemi prima di continuare.
    
3. Creare il cluster di failover di Windows Server (WSFC).
    
   - Nella **Gestione guidata cluster di failover** fare clic con il pulsante destro del mouse su **Gestione cluster di failover**, quindi scegliere **Crea cluster**.
    
   - Nella pagina **prima di iniziare** fare clic su **Avanti**.
    
   - Aggiungere il nome del cluster e l'indirizzo IP. Dopo aver convalidato le impostazioni, fare clic su **Avanti**.
    
   - Nella pagina di conferma fare clic su **Avanti**.
    
   - Dopo aver creato il cluster, fare clic su **fine**.
    
4. È consigliabile configurare le impostazioni del quorum del cluster per l'uso di un witness di condivisione file. A questo scopo, eseguire la procedura seguente:
    
   - Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **altre azioni**e fare clic su **Configura impostazioni quorum cluster**.
    
   - Nella pagina **selezionare l'opzione di configurazione quorum** fare clic su **Seleziona il testimone quorum**.
    
   - Nella pagina **Select quorum Witness** fare clic su **configura un witness di condivisione file**.
    
   - Nella pagina **Configura il witness di condivisione file** Digitare il percorso della condivisione di file che si vuole usare e quindi fare clic su **Avanti**.
    
   - Nella pagina di **conferma** fare clic su **Avanti**.
    
5. In ogni server del cluster abilitare la caratteristica AG in Gestione configurazione SQL Server.
    
   - Aprire Gestione configurazione SQL Server. Nell'albero sul lato sinistro dello schermo fare clic su **servizi SQL Server**, quindi fare doppio clic sul servizio SQL Server. 
    
   - Nella casella **Proprietà** selezionare la scheda **AlwaysOn High Availability** . Selezionare la casella di controllo **Abilita gruppi di disponibilità AlwaysOn** . Riavviare il servizio SQL Server quando richiesto.
   
6. USA generatore di topologie per creare il pool Front-End, come spiegato in [creare e pubblicare una nuova topologia in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md). Quando si esegue questa operazione, specificare l'AG come SQL Store per il pool.
    
7. Creare il gruppo di disponibilità.
    
   - Aprire SQL Server Management Studio e connettersi all'istanza di SQL Server.
    
   - In Esplora oggetti Espandi la cartella **sempre in alta disponibilità** . Fare clic con il pulsante destro del mouse sulla cartella **gruppi** di disponibilità e scegliere **nuova creazione guidata gruppo di disponibilità**.
    
   - Se viene visualizzata la pagina **Introduzione** , fare clic su **Avanti**.
    
   - Nella pagina **specificare il nome del gruppo di disponibilità** Digitare il nome del gruppo di disponibilità e fare clic su **Avanti**.
    
   - Nella pagina Selezione database selezionare i database che si desidera includere nel gruppo di disponibilità AlwaysOn. Quindi fare clic su **Avanti**.
    
     Non includere i database **ReportServer**, **ReportServerTempDB**o Persistent Chat nel gruppo di disponibilità AlwaysOn, perché non sono supportati in questo scenario. Puoi includere tutti gli altri database di Skype for Business Server nel gruppo di disponibilità AlwaysOn.
    
   - Nella pagina **Specifica repliche** fare clic sulla scheda **repliche** . Fare quindi clic sul pulsante **Aggiungi repliche** e connettersi alle altre istanze di SQL aggiunte come nodi del cluster di failover di Windows Server.
    
   - Per ogni istanza, selezionare il **failover automatico** e le opzioni di **commit sincrono** . Non selezionare l'opzione **secondaria leggibile** .
    
   - Fare clic sulla scheda **endpoint** e verificare che il **numero di porta** sia impostato su 5022.
    
   - Fare clic sulla scheda **listener** e selezionare l'opzione **Crea un gruppo di disponibilità** . In tale opzione digitare un nome per il listener e impostare la **porta** su 1433 (le altre porte non sono supportate per questa opzione).
    
   - Fare clic su **Aggiungi**e quindi nella casella **indirizzo IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK**.
    
   - Nella pagina **Seleziona sincronizzazione dati iniziale** selezionare completo e specificare una cartella accessibile alle repliche e che l'account del servizio SQL Server usato da entrambe le repliche disponga delle autorizzazioni di scrittura per. Quindi fare clic su **Avanti**.
    
     Questa condivisione file verrà usata temporaneamente quando si inizializzano i database. Se si gestiscono database di grandi dimensioni, è consigliabile inizializzarli manualmente nel caso in cui la larghezza di banda della rete non possa contenere le dimensioni dei backup del database.
    
   - Nella pagina Convalida verificare che tutti i controlli di convalida abbiano esito positivo e quindi fare clic su **Avanti**.
    
   - Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su fine.
      
8. Dopo la distribuzione del pool e dell'AG, eseguire alcuni passaggi finali per verificare che gli accessi SQL si trovino in ognuna delle repliche del gruppo di disponibilità AlwaysOn. 
    
   - Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente**e fare clic su **OK**.
    
   - Espandi Skype for Business Server, Espandi la topologia ed Espandi gli **archivi di SQL Server**. Fare clic con il pulsante destro del mouse sull'archivio SQL del nuovo gruppo di disponibilità AlwaysOn e scegliere **modifica proprietà**.
    
     - Nella parte inferiore della pagina, nella casella **FQDN di SQL Server** , cambiare il valore con il nome di dominio completo del listener dell'AG.
    
   - Pubblicare la topologia. Nel menu **azioni** fare clic su **topologia** e quindi su **pubblica**. Nella pagina di conferma fare clic su **Avanti**. Attendere alcuni minuti per la replica della nuova topologia.
    
   - Aprire SQL Server Management Studio e passare all'AG. Fallire in una replica secondaria.
    
   - Aprire Skype for Business Server Management Shell e digitare il cmdlet seguente per creare gli account di accesso SQL in questa replica:
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria e quindi `Install-CsDatabase -Update`usare) per ogni replica del gruppo.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Distribuire un gruppo di disponibilità sempre disponibile in un pool esistente che usa il mirroring del database
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Se il pool in cui si esegue l'aggiornamento a un AG ospita l'Central Management store per l'organizzazione, è necessario prima di tutto trasferire il CMS in un altro pool prima di aggiornare questo pool. Usa il cmdlet Move-CsManagementServer per trasferire il pool. Se non si dispone di un altro pool nell'organizzazione, è possibile distribuire temporaneamente un server Standard Edition e trasferire il CMS in questo server prima di eseguire l'aggiornamento del pool all'AG. 
  
1. Non eseguire il failover di tutti i dati dal mirror al nodo Principal aprendo Skype for Business Server Management Shell e digitando il cmdlet seguente.
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    Ripetere questo cmdlet per ogni tipo di database nel pool. Puoi usare il cmdlet seguente per trovare tutti i tipi di database archiviati in questo pool.
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. USA generatore di topologia per rimuovere il mirroring del database dal pool.
    
   - Aprire Generatore di topologie. Nella topologia espandere **pool Enterprise Edition front-end**, fare clic con il pulsante destro del mouse sul nome del pool e scegliere **modifica proprietà**.
    
   - Per ogni tipo di archivio SQL nel pool, deselezionare la casella di controllo **Abilita mirroring di SQL Store** .
    
3. Pubblicare la topologia modificata. Nel menu **azioni** fare clic su **topologia** e quindi su **pubblica**. Nella pagina di conferma fare clic su **Avanti**
    
4. Usare SQL Server Management Studio per suddividere lo specchio.
    
   - Aprire SQL Server Management Studio, passare ai database, fare clic con il pulsante destro del mouse su **attività** e scegliere **Specchia**. Quindi fare clic su **Rimuovi mirroring** e fare clic su **OK**.
    
   - Ripetere questa operazione per tutti i database del pool che verranno convertiti in un AG.
    
5. Configurare la funzionalità di clustering di failover in tutti i server di database che faranno parte dell'AG. In ogni server eseguire le operazioni seguenti
    
   - Aprire Server Manager e fare clic su **Aggiungi ruoli e funzionalità**.
    
   - Fare clic su **Avanti** fino a raggiungere la casella **Seleziona funzionalità** . Selezionare la casella di controllo **clustering di failover** .
    
   - Nella casella **Aggiungi funzionalità necessarie per il clustering di failover** fare clic su **Aggiungi funzionalità**.
    
   - Fare clic su **Installa**.
    
6. Convalidare la configurazione del cluster.
    
   - In Server Manager fare clic sul menu **strumenti** e quindi su **Gestione cluster di failover**.
    
   - In **azioni** sul lato destro dello schermo fare clic su **Convalida configurazione**.
    
   - Nella pagina **prima di iniziare** fare clic su **Avanti**.
    
   - Selezionare i server da aggiungere al cluster e quindi fare clic su **Esegui tutti i test**.
    
   - Nella casella **Riepilogo** verificare gli eventuali errori segnalati dalla procedura guidata. Quindi fare clic su **fine** per completare la convalida.
    
     La procedura guidata riporterà probabilmente diversi avvisi, soprattutto se non si usa lo spazio di archiviazione condiviso. Non è necessario usare lo spazio di archiviazione condiviso. Tuttavia, se vengono visualizzati messaggi di **errore** , è necessario correggere questi problemi prima di continuare.
    
7. Creare il cluster di failover di Windows Server.
    
   - Nella **Gestione guidata cluster di failover** fare clic con il pulsante destro del mouse su **Gestione cluster di failover**, quindi scegliere **Crea cluster**.
    
   - Nella pagina **prima di iniziare** fare clic su **Avanti**.
    
   - Aggiungere il nome del cluster e l'indirizzo IP. Dopo aver convalidato le impostazioni, fare clic su **Avanti**.
    
   - Nella pagina di conferma fare clic su **Avanti**.
    
   - Dopo aver creato il cluster, fare clic su **fine**.
    
8. È consigliabile configurare le impostazioni del quorum del cluster per l'uso di un witness di condivisione file. A questo scopo, eseguire la procedura seguente:
    
   - Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **altre azioni**e fare clic su **Configura impostazioni quorum cluster**.
    
   - Nella pagina **selezionare l'opzione di configurazione quorum** fare clic su **Seleziona il testimone quorum**.
    
   - Nella pagina **Select quorum Witness** fare clic su **configura un witness di condivisione file**.
    
   - Nella pagina **Configura il witness di condivisione file** Digitare il percorso della condivisione di file che si vuole usare e quindi fare clic su **Avanti**.
    
   - Nella pagina di **conferma** fare clic su **Avanti**.
    
9. In ogni server del cluster abilitare la caratteristica AG in Gestione configurazione SQL Server.
    
   - Aprire Gestione configurazione SQL Server. Nell'albero sul lato sinistro dello schermo fare clic su **servizi SQL Server**, quindi fare doppio clic sul servizio SQL Server. 
    
   - Nella casella **Proprietà** selezionare la scheda **AlwaysOn High Availability** . Selezionare la casella di controllo **Abilita gruppi di disponibilità AlwaysOn** . Riavviare il servizio SQL Server quando richiesto.
    
10. Creare il gruppo di disponibilità.
    
    - Aprire SQL Server Management Studio e connettersi all'istanza di SQL Server.
    
    - In Esplora oggetti Espandi la cartella **sempre in alta disponibilità** . Fare clic con il pulsante destro del mouse sulla cartella **gruppi** di disponibilità e scegliere **nuova creazione guidata gruppo di disponibilità**.
    
    - Se viene visualizzata la pagina **Introduzione** , fare clic su **Avanti**.
    
    - Nella pagina **specificare il nome del gruppo di disponibilità** Digitare il nome del gruppo di disponibilità e fare clic su **Avanti**.
    
    - Nella pagina Selezione database selezionare i database che si desidera includere nel gruppo di disponibilità AlwaysOn. Quindi fare clic su **Avanti**.
    
    Non includere i database **ReportServer**, **ReportServerTempDB**o Persistent Chat nel gruppo di disponibilità AlwaysOn, perché non sono supportati in questo scenario. Puoi includere tutti gli altri database di Skype for Business Server nel gruppo di disponibilità AlwaysOn.
    
    - Nella pagina **Specifica repliche** fare clic sulla scheda **repliche** . Fare quindi clic sul pulsante **Aggiungi repliche** e connettersi alle altre istanze di SQL aggiunte come nodi del cluster di failover di Windows Server.
    
    - Per ogni istanza, selezionare il **failover automatico** e le opzioni di **commit sincrono** . Non selezionare l'opzione **secondaria leggibile** .
    
    - Fare clic sulla scheda **endpoint** e verificare che il **numero di porta** sia impostato su 5022.
    
      - Fare clic sulla scheda **listener** e selezionare l'opzione **Crea un gruppo di disponibilità** . In tale opzione digitare un nome per il listener e impostare la **porta** su 1433 (le altre porte non sono supportate per questa opzione).
    
    - Fare clic su **Aggiungi**e quindi nella casella **indirizzo IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK**.
    
    - Nella pagina **Seleziona sincronizzazione dati iniziale** selezionare completo e specificare una cartella accessibile alle repliche e che l'account del servizio SQL Server usato da entrambe le repliche disponga delle autorizzazioni di scrittura per. Quindi fare clic su **Avanti**.
    
    Questa condivisione file verrà usata temporaneamente quando si inizializzano i database. Se si gestiscono database di grandi dimensioni, è consigliabile inizializzarli manualmente nel caso in cui la larghezza di banda della rete non possa contenere le dimensioni dei backup del database.
    
    - Nella pagina Convalida verificare che tutti i controlli di convalida abbiano esito positivo e quindi fare clic su **Avanti**.
    
    - Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su fine.
    
11. Creare un nuovo archivio specificando il listener AG e specificando l'entità del mirror precedente come nodo principale dell'AG.
    
    - Aprire Generatore di topologie. Espandere **componenti condivisi**nella topologia, fare clic con il pulsante destro del mouse su **Archivi SQL Server**e scegliere **nuovo archivio SQL Server**.
    
    - Nella pagina **Definisci nuovo archivio SQL** selezionare la casella di controllo **impostazioni di disponibilità elevata** e quindi verificare che i gruppi di disponibilità di SQL AlwaysOn vengano visualizzati nella casella di selezione.
    
    - Nella casella **FQDN listener di disponibilità di SQL Server** Digitare il nome di dominio completo del listener creato quando è stato creato il gruppo di disponibilità.
    
    - Nella casella **FQDN di SQL Server** Digitare il nome di dominio completo del nodo principale dell'AG e quindi fare clic su **OK**. Dovrebbe essere l'entità del mirror precedente per questo archivio.
    
12. Associa la nuova AG al pool Front-end.
    
    - In Generatore di topologie fare clic con il pulsante destro del mouse sul pool da associare all'AG e scegliere **modifica proprietà**.
    
    - In **associazioni**selezionare l'AG nella casella **Archivio SQL Server** . Selezionare lo stesso gruppo per qualsiasi altro database nel pool che si vuole trasferire all'AG.
    
    - Quando si è certi che tutti i database necessari siano impostati su AG, fare clic su **OK**.
    
13. Pubblicare la topologia. Nel menu **azioni** fare clic su **topologia** e quindi su **pubblica**. Nella pagina di conferma fare clic su **Avanti**.
    
14. Eseguire alcuni passaggi finali per verificare che gli accessi SQL si trovino in ognuna delle repliche del gruppo di disponibilità AlwaysOn.
    
    - Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente**e fare clic su **OK**.
    
    - Espandi Skype for Business Server, Espandi la topologia ed Espandi gli **archivi di SQL Server**. Fare clic con il pulsante destro del mouse sull'SQL Store della nuova AG e scegliere **modifica proprietà**.
    
    - Nella parte inferiore della pagina, nella casella **FQDN di SQL Server** , cambiare il valore con il nome di dominio completo del listener dell'AG.
    
    - Pubblicare la topologia. Nel menu **azioni** fare clic su **topologia** e quindi su **pubblica**. Nella pagina di conferma fare clic su **Avanti**. Attendere alcuni minuti per la replica della nuova topologia.
    
    - Aprire SQL Server Management Studio e passare all'AG. Fallire in una replica secondaria.
    
    - Aprire Skype for Business Server Management Shell e digitare il cmdlet seguente per creare gli account di accesso SQL in questa replica:
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria e quindi `Install-CsDatabase -Update`usare) per ogni replica del gruppo.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Distribuire un gruppo di disponibilità sempre disponibile in un pool esistente che non usa il mirroring del database
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Se il pool in cui si esegue l'aggiornamento a un AG ospita l'Central Management store per l'organizzazione, è necessario prima di tutto trasferire il CMS in un altro pool prima di aggiornare questo pool. Usa il cmdlet Move-CsManagementServer per trasferire il pool. Se non si dispone di un altro pool nell'organizzazione, è possibile distribuire temporaneamente un server Standard Edition e trasferire il CMS in questo server prima di eseguire l'aggiornamento del pool all'AG. 
  
1. Configurare la funzionalità di clustering di failover in tutti i server di database che faranno parte dell'AG. In ogni server eseguire le operazioni seguenti
    
   - Aprire Server Manager e fare clic su **Aggiungi ruoli e funzionalità**.
    
   - Fare clic su **Avanti** fino a raggiungere la casella **Seleziona funzionalità** . Selezionare la casella di controllo **clustering di failover** .
    
   - Nella casella **Aggiungi funzionalità necessarie per il clustering di failover** fare clic su **Aggiungi funzionalità**.
    
   - Fare clic su **Installa**.
    
2. Convalidare la configurazione del cluster.
    
   - In Server Manager fare clic sul menu **strumenti** e quindi su **Gestione cluster di failover**.
    
   - In **azioni** sul lato destro dello schermo fare clic su **Convalida configurazione**.
    
   - Nella pagina **prima di iniziare** fare clic su **Avanti**.
    
   - Selezionare i server da aggiungere al cluster e quindi fare clic su **Esegui tutti i test**.
    
   - Nella casella **Riepilogo** verificare gli eventuali errori segnalati dalla procedura guidata. Quindi fare clic su **fine** per completare la convalida.
    
     La procedura guidata riporterà probabilmente diversi avvisi, soprattutto se non si usa lo spazio di archiviazione condiviso. Non è necessario usare lo spazio di archiviazione condiviso. Tuttavia, se vengono visualizzati messaggi di **errore** , è necessario correggere questi problemi prima di continuare.
    
3. Creare il cluster di failover di Windows Server (WSFC).
    
   - Nella **Gestione guidata cluster di failover** fare clic con il pulsante destro del mouse su **Gestione cluster di failover**, quindi scegliere **Crea cluster**.
    
   - Nella pagina **prima di iniziare** fare clic su **Avanti**.
    
   - Aggiungere il nome del cluster e l'indirizzo IP. Dopo aver convalidato le impostazioni, fare clic su **Avanti**.
    
   - Nella pagina di conferma fare clic su **Avanti**.
    
   - Dopo aver creato il cluster, fare clic su **fine**.
    
4. È consigliabile configurare le impostazioni del quorum del cluster per l'uso di un witness di condivisione file. A questo scopo, eseguire la procedura seguente:
    
   - Fare clic con il pulsante destro del mouse sul nome del cluster, scegliere **altre azioni**e fare clic su **Configura impostazioni quorum cluster**.
    
   - Nella pagina **selezionare l'opzione di configurazione quorum** fare clic su **Seleziona il testimone quorum**.
    
   - Nella pagina **Select quorum Witness** fare clic su **configura un witness di condivisione file**.
    
   - Nella pagina **Configura il witness di condivisione file** Digitare il percorso della condivisione di file che si vuole usare e quindi fare clic su **Avanti**.
    
   - Nella pagina di **conferma** fare clic su **Avanti**.
    
5. In ogni server del cluster abilitare AG in Gestione configurazione SQL Server.
    
   - Aprire Gestione configurazione SQL Server. Nell'albero sul lato sinistro dello schermo fare clic su **servizi SQL Server**, quindi fare doppio clic sul servizio SQL Server. 
    
   - Nella casella **Proprietà** selezionare la scheda **AlwaysOn High Availability** . Selezionare la casella di controllo **Abilita gruppi di disponibilità AlwaysOn** . Riavviare il servizio SQL Server quando richiesto.
    
6. Creare il gruppo di disponibilità.
    
   - Aprire SQL Server Management Studio e connettersi all'istanza di SQL Server.
    
   - In Esplora oggetti Espandi la cartella **sempre in alta disponibilità** . Fare clic con il pulsante destro del mouse sulla cartella **gruppi** di disponibilità e scegliere **nuova creazione guidata gruppo di disponibilità**.
    
   - Se viene visualizzata la pagina **Introduzione** , fare clic su **Avanti**.
    
   - Nella pagina **specificare il nome del gruppo di disponibilità** Digitare il nome del gruppo di disponibilità e fare clic su **Avanti**.
    
   - Nella pagina Selezione database selezionare i database che si desidera includere nell'AG. Quindi fare clic su **Avanti**.
    
     Non includere i database **ReportServer**, **ReportServerTempDB**o Persistent Chat nell'AG, perché non sono supportati in questo scenario. Puoi includere tutti gli altri database di Skype for Business Server nell'AG.
    
   - Nella pagina **Specifica repliche** fare clic sulla scheda **repliche** . Fare quindi clic sul pulsante **Aggiungi repliche** e connettersi alle altre istanze di SQL aggiunte come nodi di WSFC.
    
   - Per ogni istanza, selezionare il **failover automatico** e le opzioni di **commit sincrono** . Non selezionare l'opzione **secondaria leggibile** .
    
   - Fare clic sulla scheda **endpoint** e verificare che il **numero di porta** sia impostato su 5022.
    
   - Fare clic sulla scheda **listener** e selezionare l'opzione **Crea un gruppo di disponibilità** . In tale opzione digitare un nome per il listener e impostare la **porta** su 1433 (le altre porte non sono supportate per questa opzione).
    
   - Fare clic su **Aggiungi**e quindi nella casella **indirizzo IPv4** specificare l'indirizzo IP virtuale preferito e quindi fare clic su **OK**.
    
   - Nella pagina **Seleziona sincronizzazione dati iniziale** selezionare completo e specificare una cartella accessibile alle repliche e che l'account del servizio SQL Server usato da entrambe le repliche disponga delle autorizzazioni di scrittura per. Quindi fare clic su **Avanti**.
    
     Questa condivisione file verrà usata temporaneamente quando si inizializzano i database. Se si gestiscono database di grandi dimensioni, è consigliabile inizializzarli manualmente nel caso in cui la larghezza di banda della rete non possa contenere le dimensioni dei backup del database.
    
     - Nella pagina Convalida verificare che tutti i controlli di convalida abbiano esito positivo e quindi fare clic su **Avanti**.
    
   - Nella pagina **Riepilogo** verificare tutte le impostazioni e fare clic su fine.
    
7. Creare un nuovo archivio specificando il listener AG.
    
   - Aprire Generatore di topologie. Espandere **componenti condivisi**nella topologia, fare clic con il pulsante destro del mouse su **Archivi SQL Server**e scegliere **nuovo archivio SQL Server**.
    
   - Nella pagina **Definisci nuovo archivio SQL** selezionare la casella di controllo **impostazioni di disponibilità elevata** e quindi verificare che i gruppi di disponibilità di SQL AlwaysOn vengano visualizzati nella casella di selezione.
    
   - Nella casella **FQDN listener di disponibilità di SQL Server** Digitare il nome di dominio completo del listener creato quando è stato creato il gruppo di disponibilità.
    
   - Nella casella **FQDN di SQL Server** Digitare il nome di dominio completo del nodo principale dell'AG e quindi fare clic su **OK**.
    
8. Associa il nuovo gruppo di disponibilità sempre con il pool Front-end.
    
   - In Generatore di topologie fare clic con il pulsante destro del mouse sul pool da associare all'AG e scegliere **modifica proprietà**.
    
   - In **associazioni**selezionare l'AG nella casella **Archivio SQL Server** . Selezionare lo stesso gruppo per qualsiasi altro database nel pool che si vuole trasferire all'AG.
    
   - Quando si è certi che tutti i database necessari siano impostati su AG, fare clic su **OK**.
    
9. Pubblicare la topologia. Nel menu **azioni** fare clic su **topologia** e quindi su **pubblica**. Nella pagina di conferma fare clic su **Avanti**.
    
10. Eseguire alcuni passaggi finali per verificare che gli accessi SQL si trovino in ognuna delle repliche dell'AG.
    
    - Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente**e fare clic su **OK**.
    
    - Espandi Skype for Business Server, Espandi la topologia ed Espandi gli **archivi di SQL Server**. Fare clic con il pulsante destro del mouse sull'SQL Store della nuova AG e scegliere **modifica proprietà**.
    
    - Nella parte inferiore della pagina, nella casella **FQDN di SQL Server** , cambiare il valore con il nome di dominio completo del listener dell'AG.
    
    - Pubblicare la topologia. Nel menu **azioni** fare clic su **topologia** e quindi su **pubblica**. Nella pagina di conferma fare clic su **Avanti**. Attendere alcuni minuti per la replica della nuova topologia.
    
    - Aprire SQL Server Management Studio e passare all'AG. Fallire in una replica secondaria.
    
    - Aprire Skype for Business Server Management Shell e digitare il cmdlet seguente per creare gli account di accesso SQL in questa replica:
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - Ripetere i due passaggi precedenti (eseguire il failover del gruppo in una replica secondaria e quindi `Install-CsDatabase -Update`usare) per ogni replica del gruppo.
