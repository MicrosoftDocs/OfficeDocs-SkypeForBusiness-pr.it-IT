---
title: Distribuire il mirroring di SQL per la disponibilità elevata del server back-end in Skype for Business Server 2015
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
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Per distribuire il mirroring SQL, i server devono eseguire almeno SQL Server 2008 R2. Questa versione deve essere eseguita da tutti i server coinvolti: il server primario, mirror, e di controllo. Per informazioni dettagliate, vedere pacchetto di aggiornamento cumulativo 9 per SQL Server 2008 Service Pack 1.'
ms.openlocfilehash: 8a546f65d8ad5c701eea20fb2c9c3bf0e026ff1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830556"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>Distribuire il mirroring di SQL per la disponibilità elevata del server back-end in Skype for Business Server 2015


Per distribuire il mirroring SQL, i server devono eseguire almeno SQL Server 2008 R2. Questa versione deve essere eseguita da tutti i server coinvolti: il server primario, mirror, e di controllo. Per informazioni dettagliate, vedere [pacchetto di aggiornamento cumulativo 9 per SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).

In generale, la configurazione del mirroring SQL tra due server di back-end con un server di controllo richiede che:

- La versione del server primario di SQL Server deve supportare il mirroring SQL.

- I server primario, mirror e di controllo (se distribuito) abbiano la stessa versione di SQL Server.

- Il server primario e mirror abbiano la stessa edizione di SQL Server. Il server di controllo può avere un'edizione diversa.

Per le procedure consigliate SQL in termini di supporto delle versioni SQL per un ruolo di controllo, vedere [database mirroring witness](https://go.microsoft.com/fwlink/p/?LinkId=247345).

È possibile utilizzare Generatore di topologie per distribuire il mirroring SQL. È possibile selezionare un'opzione in Generatore di topologie per il mirroring dei database e il generatore di topologie configura il mirroring, inclusa la configurazione di un controllo, se si desidera, quando si pubblica la topologia. Il server di controllo viene rimosso o configurato contemporaneamente alla rimozione o configurazione del mirror. Non esiste un comando separato che consente di distribuire o rimuovere unicamente un server di controllo.

Per configurare il mirroring del server, è prima necessario configurare correttamente le autorizzazioni del database SQL. Per informazioni dettagliate, vedere [configurare gli account di accesso per il mirroring del database o i gruppi di disponibilità AlwaysOn (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).

Con il mirroring SQL, la modalità di ripristino del database è sempre impostata su **full**, il che significa che è necessario monitorare attentamente le dimensioni dei registri delle transazioni e il backup dei log delle transazioni su base regolare per evitare di esaurire lo spazio su disco nei server back-end. La frequenza dei backup del log delle transazioni dipende dalla frequenza di crescita del registro, che dipende dalle transazioni di database sostenute dalle attività degli utenti nel pool Front end. È consigliabile determinare la quantità di sviluppo del registro delle transazioni previsto per il carico di lavoro di distribuzione, in modo che sia possibile eseguire la pianificazione di conseguenza. Negli articoli seguenti vengono fornite informazioni aggiuntive su backup SQL e gestione dei log:

- [Modelli di ripristino del database](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [Panoramica del backup](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [Log delle transazioni di backup](https://go.microsoft.com/fwlink/p/?LinkId=268452)

Nel mirroring SQL è possibile configurare la topologia per il mirroring al momento della creazione dei pool, o in seguito.

> [!IMPORTANT]
> L'utilizzo di generatore di topologie o cmdlet per configurare e rimuovere il mirroring SQL è supportato solo quando i server primari, mirror e Witness (se necessario) appartengono tutti allo stesso dominio. Per configurare il mirroring SQL tra server su domini diversi, vedere la documentazione relativa a SQL Server.

> [!IMPORTANT]
> Quando si apportano modifiche a una relazione di mirroring di un database di back end, è necessario riavviare tutti i Front End Server nel pool. > per una modifica del mirroring, ad esempio la modifica del percorso di un mirror, è necessario utilizzare Generatore di topologie per eseguire questi tre passaggi:

1. Rimuovere il mirroring dal server mirror meno recente.

2. Aggiungere il mirroring al nuovo server mirror.

3. Pubblicare la topologia.

> [!NOTE]
> È necessario creare una condivisione file per la scrittura dei file mirror e il servizio in cui SQL Server e SQL Agent sono in esecuzione in accesso in lettura/scrittura. Se il servizio SQL Server è in esecuzione nel contesto di servizio di rete, è possibile aggiungere \<Domain\> \\<SqlServerName \> $ dei server SQL Principal e mirror alle autorizzazioni di condivisione. $ È importante per identificare che si tratta di un account computer.

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>Per configurare il mirroring SQL durante la creazione di un pool in Generatore di topologie

1. Nella pagina **Definisci archivio SQL**, fare clic su **Nuovo** accanto alla casella **Archivio SQL**.

2. Nella pagina **Definisci nuovo archivio SQL**, specificare l'archivio primario, selezionare **L'istanza SQL è in relazione di mirroring**, specificare il numero di porta del mirroring SQL (il valore predefinito è 5022), quindi fare clic su **OK**.

3. Nella pagina **Definisci archivio SQL**, selezionare **Abilita archivio mirroring SQL**.

4. Nella pagina **Definisci nuovo archivio SQL**, specificare l'archivio SQL da utilizzare come mirror. Selezionare **L'istanza SQL è in relazione di mirroring**, specificare il numero di porta (il valore predefinito è 5022), quindi fare clic su **OK**.

5. Se si desidera un'istanza di controllo per il mirror, effettuare le operazioni seguenti:

    a. Selezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico**.

    b. Nella pagina **Definisci archivio SQL**, selezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** e specificare l'archivio SQL da utilizzare per il controllo.

    c. Specificare il numero di porta (il valore predefinito è 7022) e fare clic su **OK**

6. Dopo aver completato la definizione del pool Front end e di tutti gli altri ruoli nella topologia, utilizzare Generatore di topologie per pubblicare la topologia. Quando la topologia viene pubblicata, se il pool Front end che ospita l'archivio di gestione centrale dispone del mirroring SQL abilitato, verrà visualizzata un'opzione per creare i database dell'archivio SQL primario e del mirror.

    Fare clic su **Impostazioni** e digitare il percorso da utilizzare come condivisione file per il backup del mirroring.

    Fare clic su **OK** e **Avanti** per creare i database e pubblicare la topologia. I server di mirroring e di controllo (se specificato) saranno così distribuiti.

È possibile utilizzare Generatore di topologie per modificare le proprietà di un pool già esistente per abilitare il mirroring SQL.

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>Per aggiungere il mirroring SQL a un pool Front end esistente in Generatore di topologie

1. In Generatore di topologie fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.

2. Selezionare **Abilita mirroring dell'archivio SQL**, quindi fare clic su **Nuovo** accanto a **Mirroring dell'archivio SQL**.

3. Specificare l'archivio SQL che si desidera utilizzare come mirror.

4. Selezionare **L'istanza SQL è in relazione di mirroring**, specificare il numero di porta per il mirroring SQL (il valore predefinito è 5022), quindi fare clic su **OK**.

5. Per configurare un'istanza di controllo, selezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** e fare clic su **Nuovo**.

6. Specificare l'archivio SQL che si desidera utilizzare come istanza di controllo.

7. Selezionare **L'istanza SQL è in relazione di mirroring**, specificare il numero di porta per il mirroring SQL (il valore predefinito è 7022), quindi fare clic su **OK**.

8. Fare clic su **OK**.

9. Pubblicare la topologia. Verrà richiesto di installare il database.

    Durante il processo di pubblicazione della topologia verrà richiesto di definire un percorso di condivisione file. I server SQL che partecipano al mirroring devono disporre dell'accesso in lettura/scrittura alla condivisione file per il mirror da stabilire.

A questo punto è necessario installare il database prima di passare alla procedura successiva.

Quando si configura il mirroring SQL, è necessario tenere a mente alcuni punti:

- Se esiste già un endpoint del mirroring, sarà riutilizzato insieme alle porte definite qui, e saranno ignorate quelle specificate nella topologia.

- Le porte già allocate ad altre applicazioni sullo stesso server, comprese quelle allocate ad altre istanze di SQL, non devono essere utilizzate per le nuove istanze di SQL installate. Pertanto, se si ha più di una istanza SQL installata sullo stesso server, queste devono utilizzare porte differenti per il mirroring. Per ulteriori dettagli, vedere:

  - [Specificare un indirizzo di rete del server (mirroring del database)](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [Endpoint del mirroring del database (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Utilizzo dei cmdlet di Skype for Business Server 2015 Management Shell per configurare il mirroring SQL

Il modo più semplice per configurare il mirroring consiste nell'utilizzo di generatore di topologie, ma è possibile farlo anche utilizzando i cmdlet.

1. Aprire una finestra di gestione di Skype for Business Server 2015 ed eseguire il cmdlet seguente:

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    Ad esempio:

   ```powershell
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    Verrà visualizzato quanto segue:

   <pre>
   Database Name:rtcxds
        Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf
         Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:rtcshared
        Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf
         Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:rtcab
        Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf
         Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:rgsconfig
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:rgsdyn
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:cpsdyn
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:xds
        Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf
         Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:lis
        Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf
         Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
   [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
   </pre>

2. Verificare che:

    - La Porta 5022 sia accessibile attraverso il firewall se Windows Firewall è abilitato sel server SQL primario e04-ocs.los_a.lsipt.local\rtc.

    - La Porta 5022 sia accessibile attraverso il firewall se Windows Firewall è abilitato sel server SQL mirror K16-ocs.los_a.lsipt.local\rtc.

    - La Porta 7022 sia accessibile attraverso il firewall se Windows Firewall è abilitato sel server SQL di controllo AB14-lct.los_a.lsipt.local\rtc.

   - Gli account che eseguono i server SQL su tutti i server SQL primario e mirror dispongono dell'autorizzazione di lettura/scrittura per la condivisione file \\ E04-OCS\csdatabackup

   - Verificare che il provider della Strumentazione gestione Windows (WMI) sia eseguito su tutti questi server. Il cmdlet si serve di questo provider per trovare le informazioni sull'account relative ai servizi di SQL Server eseguiti su tutti i server primari, mirror e di controllo.

   - Verificare che l'account sul quale è eseguito il cmdlet abbia le autorizzazioni necessarie per creare le cartelle per i dati e i file dei log per tutti i server mirror.

   - Si noti che l'account utente utilizzato dall'istanza SQL per la propria esecuzione deve essere dotato di autorizzazioni di lettura e scrittura per la condivisione file. Se la condivisione file si trova su un server diverso e l'istanza SQL esegue un account di sistema locale, è necessario concedere autorizzazioni per la condivisione file al server che ospita l'istanza SQL.

3. Digitare A e premere INVIO.

    Sarà configurato il mirroring.

    **Install-CsMirrorDatabase** installa il mirror e configura il mirroring per tutti i database presenti nell'archivio SQL primario. Se si desidera configurare il mirroring solo per database specifici, è possibile utilizzare l'opzione-DatabaseType oppure se si desidera configurare il mirroring per tutti i database ad eccezione di alcuni, è possibile utilizzare l'opzione-ExcludeDatabaseList, insieme a un elenco separato da virgole di nomi di database da escludere.

    Ad esempio, se si aggiunge l'opzione seguente a **Install-CsMirrorDatabase**, si eseguirà il mirroring per tutti i database ad eccezione di rtcab e rtcxds.

    `-ExcludeDatabaseList rtcab,rtcxds`

   Ad esempio, se si aggiunge l'opzione seguente a **Install-CsMirrorDatabase**, si eseguirà il mirroring unicamente per i database rtcab e rtcxds.

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a>Rimozione o modifica del mirroring SQL

Per rimuovere il mirroring SQL da un pool in Generatore di topologie, è prima necessario utilizzare un cmdlet per la rimozione del mirror in SQL Server. È quindi possibile utilizzare Generatore di topologie per rimuovere il mirror dalla topologia. Per rimuovere il mirror in SQL Server, utilizzare il cmdlet seguente:

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

Ad esempio, per rimuovere il mirroring ed eliminare i database degli utenti, digitare:

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

L'  `-DropExistingDatabasesOnMirror` opzione fa in modo che i database danneggiati vengano eliminati dal mirror.

Per rimuovere il mirror dalla topology, eseguire le operazioni seguenti:

1. In Generatore di topologie, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica proprietà**.

2. Deselezionare **Abilita archivio mirroring SQL** e fare clic su **OK**.

3. Pubblicare la topologia.

## <a name="removing-a-mirroring-witness"></a>Rimozione di un Server di controllo del mirroring

Utilizzare questa procedura se è necessario rimuovere il controllo da una configurazione del mirroring del server back-end.

1. In Generatore di topologie, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica proprietà**.

2. Deselezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** e fare clic su **OK**.

3. Pubblicare la topologia.

    Dopo aver pubblicato la topologia, generatore di topologie verrà visualizzato un messaggio che include gli elementi seguenti:

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    Tuttavia, non seguire questo passaggio e non digitare  `Uninstall-CsMirrorDatabase` come che disinstalli l'intera configurazione del mirroring.

4. Per rimuovere solo il controllo dalla configurazione di SQL Server, seguire le istruzioni riportate in [Remove the Witness from a database mirroring Session (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).


