---
title: Distribuire il mirroring SQL per l'elevata disponibilità del server back-end in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Per poter distribuire il mirroring SQL, è necessario che i server eseguano un minimo di SQL Server 2008 R2. Questa versione deve essere eseguita su tutti i server coinvolti: il principale, il mirror e il witness. Per informazioni dettagliate, vedere pacchetto di aggiornamento cumulativo 9 per SQL Server 2008 Service Pack 1.'
ms.openlocfilehash: 19f315d643ea5b9379445bf7571e49e7d658f5ab
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003586"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>Distribuire il mirroring SQL per l'elevata disponibilità del server back-end in Skype for Business Server 2015


Per poter distribuire il mirroring SQL, è necessario che i server eseguano un minimo di SQL Server 2008 R2. Questa versione deve essere eseguita su tutti i server coinvolti: il principale, il mirror e il witness. Per informazioni dettagliate, vedere [pacchetto di aggiornamento cumulativo 9 per SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).

In generale, la configurazione del mirroring SQL tra i due server back-end con un testimone richiede quanto segue:

- La versione del server primario di SQL Server deve supportare il mirroring SQL.

- Il principale, il mirror e il Witness (se distribuiti) devono avere la stessa versione di SQL Server.

- Il principale e lo specchio devono avere la stessa edizione di SQL Server. Il testimone può avere una versione diversa.

Per le procedure consigliate SQL in termini di supporto delle versioni SQL per un ruolo di testimone, vedere [mirroring del database](https://go.microsoft.com/fwlink/p/?LinkId=247345).

Puoi usare generatore di topologia per distribuire il mirroring SQL. È possibile selezionare un'opzione in Generatore di topologia per eseguire il mirroring dei database e generatore di topologia configura il mirroring, inclusa la configurazione di un testimone, se si vuole, quando si pubblica la topologia. Tieni presente che hai configurato o rimosso il testimone contemporaneamente alla configurazione o alla rimozione dello specchio. Non esiste un comando separato per distribuire o rimuovere solo un testimone.

Per configurare il mirroring del server, è prima necessario configurare le autorizzazioni di database SQL in modo corretto. Per informazioni dettagliate, vedere [configurare gli account di accesso per il mirroring del database o i gruppi di disponibilità AlwaysOn (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).

Con il mirroring SQL, la modalità di ripristino del database è sempre impostata su **completo**, pertanto è necessario monitorare in modo regolare le dimensioni del log delle transazioni e il backup dei log delle transazioni per evitare di esaurire lo spazio su disco nei server back-end. La frequenza dei backup del log delle transazioni dipende dalla velocità di crescita del log, che a sua volta dipende dalle transazioni di database sostenute dalle attività degli utenti nel pool Front-end. È consigliabile determinare la quantità di crescita del log delle transazioni prevista per il carico di lavoro di distribuzione, in modo da poter eseguire la pianificazione di conseguenza. Gli articoli seguenti contengono informazioni aggiuntive su backup e gestione dei log di SQL:

- [Modelli di ripristino di database](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [Panoramica del backup](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [Log delle transazioni di backup](https://go.microsoft.com/fwlink/p/?LinkId=268452)

Con il mirroring SQL è possibile configurare la topologia per il mirroring quando si creano i pool o quando i pool sono già stati creati.

> [!IMPORTANT]
> L'uso di generatore di topologie o cmdlet per configurare e rimuovere il mirroring SQL è supportato solo quando i server primari, mirror e Witness (se necessario) appartengono tutti allo stesso dominio. Se si vuole configurare il mirroring SQL tra server in diversi domini, vedere la documentazione di SQL Server.

> [!IMPORTANT]
> Ogni volta che si apporta una modifica a una relazione di mirroring del database back-end, è necessario riavviare tutti i server front-end nel pool. > per una modifica del mirroring, ad esempio la modifica della posizione di un mirror, è necessario usare generatore di topologie per eseguire questi tre passaggi:

1. Rimuovere il mirroring dal server mirror precedente.

2. Aggiungere il mirroring al nuovo server mirror.

3. Pubblicare la topologia.

> [!NOTE]
> È necessario creare una condivisione file per la scrittura dei file mirror e il servizio di SQL Server e agente SQL in uso richiede l'accesso in lettura/scrittura. Se il servizio SQL Server è in uso nel contesto del servizio di rete, è possibile \<aggiungere\> \\ il dominio<SqlServerName\>$ sia del server principale che di quello mirror per le autorizzazioni di condivisione. Il $ è importante per identificare che si tratta di un account di computer.

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>Per configurare il mirroring SQL durante la creazione di un pool in Generatore di topologia

1. Nella pagina **Definisci l'archivio SQL** fare clic su **nuovo** accanto alla casella **Archivio SQL** .

2. Nella pagina **Definisci nuovo archivio SQL** specificare l'archivio principale, selezionare **questa istanza SQL è in relazione speculare**, specificare il numero di porta di mirroring SQL (il valore predefinito è 5022) e quindi fare clic su **OK**.

3. Nella pagina **Definisci l'archivio SQL** selezionare **Abilita mirroring di SQL Store**.

4. Nella pagina **Definisci nuovo archivio SQL** specificare l'archivio SQL da usare come mirror. Selezionare **questa istanza SQL in relazione speculare**, specificare il numero di porta (il valore predefinito è 5022) e quindi fare clic su **OK**.

5. Se si vuole un testimone per questo mirror, eseguire le operazioni seguenti:

    un. Selezionare **USA witness di mirroring SQL per abilitare il failover automatico**.

    b. Nella pagina **Definisci l'archivio SQL** selezionare **USA mirroring di SQL per abilitare il failover automatico**e specificare l'SQL Store da usare come witness.

    c. Specificare il numero di porta (il valore predefinito è 7022) e fare clic su **OK**.

6. Dopo aver definito il pool Front-end e tutti gli altri ruoli nella topologia, usare generatore di topologie per pubblicare la topologia. Quando la topologia viene pubblicata, se il pool Front-end che ospita Central Management store ha attivato il mirroring SQL, verrà visualizzata un'opzione per creare database di SQL Store primari e speculari.

    Fare clic su **Impostazioni**e digitare il percorso da usare come condivisione file per il backup del mirroring.

    Fare clic su **OK** e quindi su **Avanti** per creare i database e pubblicare la topologia. Il mirroring e il Witness (se specificato) verranno distribuiti.

Puoi usare generatore di topologie per modificare le proprietà di un pool già esistente per abilitare il mirroring SQL.

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>Per aggiungere il mirroring SQL a un pool Front-end esistente in Generatore di topologie

1. In Generatore di topologie fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.

2. Selezionare **Abilita mirroring di SQL Store**e quindi fare clic su **nuovo** accanto a **mirroring SQL Store**.

3. Specificare l'archivio SQL che si vuole usare come mirror.

4. Selezionare **questa istanza SQL è in relazione speculare**, specificare il numero della porta di mirroring SQL la porta predefinita è 5022) e quindi fare clic su **OK**.

5. Se si vuole configurare un testimone, selezionare **USA Witness mirroring SQL per abilitare il failover automatico**e fare clic su **nuovo**.

6. Specificare l'archivio SQL che si vuole usare come witness.

7. Selezionare **questa istanza SQL è in relazione speculare**, specificare il numero di porta di mirroring SQL (la porta predefinita è 7022) e quindi fare clic su **OK**.

8. Fare clic su **OK**.

9. Pubblicare la topologia. Quando si esegue questa operazione, verrà richiesto di installare il database.

    Durante il processo di pubblicazione della topologia verrà richiesto di definire un percorso di condivisione file. I server SQL che partecipano al mirroring devono avere accesso in lettura/scrittura alla condivisione file per il mirror da stabilire.

Devi quindi installare il database prima di passare alla procedura successiva.

Quando si configura il mirroring SQL, è consigliabile tenersi in considerazione quanto segue:

- Se un endpoint di mirroring esiste già, verrà riutilizzato con le porte definite in tale posizione e ignorerà quelle specificate nella topologia.

- Qualsiasi porta già allocata per altre applicazioni nello stesso server, inclusi quelli per altre istanze SQL, non deve essere usata per le istanze SQL installate a mano. Questo implica che se sono installate più istanze di SQL nello stesso server, non devono usare la stessa porta per il mirroring. Per informazioni dettagliate, vedere gli articoli seguenti:

  - [Specificare un indirizzo di rete del server (mirroring del database)](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [Endpoint del mirroring del database (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Uso dei cmdlet di Skype for Business Server 2015 Management Shell per configurare il mirroring SQL

Il modo più semplice per configurare il mirroring consiste nell'usare generatore di topologia, ma è anche possibile usare i cmdlet.

1. Aprire una finestra di Management Shell di Skype for Business Server 2015 ed eseguire il cmdlet seguente:

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    Ad esempio:

   ```powershell
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    Verranno visualizzate le operazioni seguenti:

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

2. Verificare quanto segue:

    - La porta 5022 è accessibile tramite il firewall se Windows Firewall è abilitato nel E04 SQL Server principale-OCS. los_a. lsipt. local\rtc.

    - La porta 5022 è accessibile tramite il firewall se Windows Firewall è abilitato nello specchio SQL Server K16-OCS. los_a. lsipt. local\rtc.

    - La porta 7022 è accessibile tramite il firewall se Windows Firewall è abilitato nella finestra di controllo di SQL Server AB14-LCT. los_a. lsipt. local\rtc.

   - Gli account che utilizzano i server SQL in tutti i server SQL primari e mirror hanno l'autorizzazione di lettura/ \\scrittura per la condivisione file E04-OCS\csdatabackup

   - Verificare che il provider di Strumentazione gestione Windows (WMI) sia in uso in tutti questi server. Il cmdlet usa questo provider per trovare le informazioni sull'account per i servizi SQL Server in uso in tutti i server primari, mirror e Witness.

   - Verificare che l'account che utilizza questo cmdlet disponga delle autorizzazioni necessarie per creare le cartelle per i dati e i file di log per tutti i server mirror.

   - Tieni presente che l'account utente usato dall'istanza SQL per l'esecuzione deve avere l'autorizzazione di lettura/scrittura per la condivisione file. Se la condivisione file si trova in un server diverso e l'istanza SQL esegue un account di sistema locale, è necessario concedere le autorizzazioni di condivisione file al server che ospita l'istanza SQL.

3. Digitare A e premere INVIO.

    Verrà configurato il mirroring.

    **Install-CsMirrorDatabase** installa il mirror e configura il mirroring per tutti i database presenti nell'archivio SQL principale. Se si vuole configurare il mirroring solo per database specifici, è possibile usare l'opzione-DatabaseType oppure se si vuole configurare il mirroring per tutti i database, ad eccezione di pochi, è possibile usare l'opzione-ExcludeDatabaseList insieme a un elenco di database delimitato da virgole nomi da escludere.

    Ad esempio, se si aggiunge l'opzione seguente a **Install-CsMirrorDatabase**, tutti i database eccetto RTCAb e rtcxds verranno speculati.

    `-ExcludeDatabaseList rtcab,rtcxds`

   Ad esempio, se si aggiunge l'opzione seguente a **Install-CsMirrorDatabase**, verranno rispecchiati solo i database RTCAb, rtcshared e rtcxds.

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a>Rimozione o modifica del mirroring SQL

Per rimuovere il mirroring SQL di un pool in Generatore di topologia, è necessario prima di tutto usare un cmdlet per rimuovere il mirror in SQL Server. Puoi quindi usare generatore di topologia per rimuovere il mirror dalla topologia. Per rimuovere il mirror in SQL Server, usare il cmdlet seguente:

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

Ad esempio, per rimuovere il mirroring e rilasciare i database per i database degli utenti, digitare quanto segue:

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

L' `-DropExistingDatabasesOnMirror` opzione fa sì che i database interessati vengano eliminati dallo specchio.

Quindi, per rimuovere il mirror dalla topologia, eseguire le operazioni seguenti:

1. In Generatore di topologie fare clic con il pulsante destro del mouse sul pool e scegliere **modifica proprietà**.

2. Deselezionare **Abilita mirroring di SQL Store** e fare clic su **OK**.

3. Pubblicare la topologia.

## <a name="removing-a-mirroring-witness"></a>Rimozione di un witness di mirroring

Usare questa procedura se si vuole rimuovere il testimone da una configurazione di mirroring del server back-end.

1. In Generatore di topologie fare clic con il pulsante destro del mouse sul pool e scegliere **modifica proprietà**.

2. Deselezionare **USA mirroring di SQL Server per abilitare il failover automatico** e fare clic su **OK**.

3. Pubblicare la topologia.

    Dopo aver pubblicato la topologia, generatore di topologie verrà visualizzato un messaggio che include le operazioni seguenti

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    Tuttavia, non seguire questo passaggio e non digitare `Uninstall-CsMirrorDatabase` in modo da disinstallare l'intera configurazione di mirroring.

4. Per rimuovere solo il testimone dalla configurazione di SQL Server, seguire le istruzioni in [rimuovere il testimone da una sessione di mirroring del database (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).


