---
title: Distribuzione del mirroring di SQL per la disponibilità elevata del server back-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb8c9647c24f326b1a2a51c99e7fa4ee5eafa23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a>Distribuzione del mirroring di SQL per la disponibilità elevata del server back-end in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-01-08_

Per poter distribuire il mirroring SQL, è necessario che i server eseguano un minimo di SQL Server 2008 R2. Questa versione deve essere eseguita su tutti i server coinvolti: il principale, il mirror e il witness. Per informazioni dettagliate, [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921)vedere.

In generale, la configurazione del mirroring SQL tra i due server back-end con un testimone richiede quanto segue:

  - La versione del server primario di SQL Server deve supportare il mirroring SQL.

  - Il principale, il mirror e il Witness (se distribuiti) devono avere la stessa versione di SQL Server.

  - Il principale e lo specchio devono avere la stessa edizione di SQL Server. Il testimone può avere una versione diversa.

Per le procedure consigliate SQL in termini di supporto delle versioni SQL per un ruolo di testimone, vedere "mirroring del database" in MSDN Library [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345)all'indirizzo.

Puoi usare generatore di topologia per distribuire il mirroring SQL. È possibile selezionare un'opzione in Generatore di topologia per eseguire il mirroring dei database e generatore di topologia configura il mirroring, inclusa la configurazione di un testimone, se si vuole, quando si pubblica la topologia. Tieni presente che hai configurato o rimosso il testimone contemporaneamente alla configurazione o alla rimozione dello specchio. Non esiste un comando separato per distribuire o rimuovere solo un testimone.

Per configurare il mirroring del server, è prima necessario configurare le autorizzazioni di database SQL in modo corretto. Per informazioni dettagliate, vedere "configurare gli account di accesso per il mirroring del database o i gruppi di disponibilità AlwaysOn [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454)(SQL Server)" at.

Con il mirroring SQL, la modalità di ripristino del database è sempre impostata su **completo**, pertanto è necessario monitorare in modo regolare le dimensioni del log delle transazioni e il backup dei log delle transazioni per evitare di esaurire lo spazio su disco nei server back-end. La frequenza dei backup del log delle transazioni dipende dalla velocità di crescita del log, che a sua volta dipende dalle transazioni di database sostenute dalle attività degli utenti nel pool Front-end. È consigliabile determinare la quantità di crescita del log delle transazioni prevista per il carico di lavoro di distribuzione di Lync in modo da poter eseguire la pianificazione di conseguenza. Gli articoli seguenti contengono informazioni aggiuntive su backup e gestione dei log di SQL:

  - Modelli di ripristino di database: "modelli di ripristino (SQL Server)" in[http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)

  - Panoramica del backup: "Panoramica del backup (SQL Server)" all'indirizzo[http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)

  - Log delle transazioni di backup: "eseguire il backup di un log delle transazioni (SQL Server)" in[http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)

Con il mirroring SQL è possibile configurare la topologia per il mirroring quando si creano i pool o quando i pool sono già stati creati.



> [!IMPORTANT]
> L'uso di generatore di topologie o cmdlet per configurare e rimuovere il mirroring SQL è supportato solo quando i server primari, mirror e Witness (se necessario) appartengono tutti allo stesso dominio. Se si vuole configurare il mirroring SQL tra server in diversi domini, vedere la documentazione di SQL Server.





> [!IMPORTANT]
> Ogni volta che si apporta una modifica a una relazione di mirroring del database back-end, è necessario riavviare tutti i server front-end nel pool.<BR>Per una modifica del mirroring, ad esempio la modifica della posizione di un mirror, è necessario usare generatore di topologie per eseguire questi tre passaggi: 
> <OL>
> <LI>
> <P>Rimuovere il mirroring dal server mirror precedente.</P>
> <LI>
> <P>Aggiungere il mirroring al nuovo server mirror.</P>
> <LI>
> <P>Pubblicare la topologia.</P></LI></OL>




> [!NOTE]
> È necessario creare una condivisione file per la scrittura dei file mirror e il servizio di SQL Server e agente SQL in uso richiede l'accesso in lettura/scrittura. Se il servizio SQL Server è in uso nel contesto del servizio di rete, è possibile &lt;aggiungere&gt; il &lt;dominio&#92;SqlServerName&gt;$ sia del server principale che di quello mirror per le autorizzazioni di condivisione. Il $ è importante per identificare che si tratta di un account di computer.


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>Per configurare il mirroring SQL durante la creazione di un pool in Generatore di topologia

1.  Nella pagina **Definisci l'archivio SQL** fare clic su **nuovo** accanto alla casella **Archivio SQL** .

2.  Nella pagina **Definisci nuovo archivio SQL** specificare l'archivio principale, selezionare **questa istanza SQL è in relazione speculare**, specificare il numero di porta di mirroring SQL (il valore predefinito è 5022) e quindi fare clic su **OK**.

3.  Nella pagina **Definisci l'archivio SQL** selezionare **Abilita mirroring di SQL Store**.

4.  Nella pagina **Definisci nuovo archivio SQL** specificare l'archivio SQL da usare come mirror. Selezionare **questa istanza SQL in relazione speculare**, specificare il numero di porta (il valore predefinito è 5022) e quindi fare clic su **OK**.

5.  Se si vuole un testimone per questo mirror, eseguire le operazioni seguenti:
    
    1.  Selezionare **USA witness di mirroring SQL per abilitare il failover automatico**.
    
    2.  Nella pagina **Definisci l'archivio SQL** selezionare **USA mirroring di SQL per abilitare il failover automatico**e specificare l'SQL Store da usare come witness.
    
    3.  Specificare il numero di porta (il valore predefinito è 7022) e fare clic su **OK**.

6.  Dopo aver definito il pool Front-end e tutti gli altri ruoli nella topologia, usare generatore di topologie per pubblicare la topologia. Quando la topologia viene pubblicata, se il pool Front-end che ospita Central Management store ha attivato il mirroring SQL, verrà visualizzata un'opzione per creare database di SQL Store primari e speculari.
    
    Fare clic su **Impostazioni**e digitare il percorso da usare come condivisione file per il backup del mirroring.
    
    Fare clic su **OK** e quindi su **Avanti** per creare i database e pubblicare la topologia. Il mirroring e il Witness (se specificato) verranno distribuiti.

Puoi usare generatore di topologie per modificare le proprietà di un pool già esistente per abilitare il mirroring SQL.

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>Per aggiungere il mirroring SQL a un pool Front-end esistente in Generatore di topologie

1.  In Generatore di topologie fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.

2.  Selezionare **Abilita mirroring di SQL Store**e quindi fare clic su **nuovo** accanto a **mirroring SQL Store**.

3.  Specificare l'archivio SQL che si vuole usare come mirror.

4.  Selezionare **questa istanza SQL è in relazione speculare**, specificare il numero della porta di mirroring SQL la porta predefinita è 5022) e quindi fare clic su **OK**.

5.  Se si vuole configurare un testimone, selezionare **USA Witness mirroring SQL per abilitare il failover automatico**e fare clic su **nuovo**.

6.  Specificare l'archivio SQL che si vuole usare come witness.

7.  Selezionare **questa istanza SQL è in relazione speculare**, specificare il numero di porta di mirroring SQL (la porta predefinita è 7022) e quindi fare clic su **OK**.

8.  Fare clic su **OK**.

9.  Pubblicare la topologia. Quando si esegue questa operazione, verrà richiesto di installare il database.
    
    Durante il processo di pubblicazione della topologia verrà richiesto di definire un percorso di condivisione file. I server SQL che partecipano al mirroring devono avere accesso in lettura/scrittura alla condivisione file per il mirror da stabilire.

Devi quindi installare il database prima di passare alla procedura successiva.

Quando si configura il mirroring SQL, è consigliabile tenersi in considerazione quanto segue:

  - Se un endpoint di mirroring esiste già, verrà riutilizzato con le porte definite in tale posizione e ignorerà quelle specificate nella topologia.

  - Qualsiasi porta già allocata per altre applicazioni nello stesso server, inclusi quelli per altre istanze SQL, non deve essere usata per le istanze SQL installate a mano. Questo implica che se sono installate più istanze di SQL nello stesso server, non devono usare la stessa porta per il mirroring. Per informazioni dettagliate, vedere gli articoli seguenti:
    
      - "Specificare un indirizzo di rete del server (mirroring del database)" in MSDN Library all'[http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)
    
      - "Endpoint del mirroring del database (SQL Server)" in[http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Uso dei cmdlet di Lync Server Management Shell per configurare il mirroring SQL

Il modo più semplice per configurare il mirroring consiste nell'usare generatore di topologia, ma è anche possibile usare i cmdlet.

1.  Aprire una finestra di Lync Server Management Shell ed eseguire il cmdlet seguente:
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    Ad esempio:
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    Verranno visualizzate le operazioni seguenti:
    
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

2.  Verificare quanto segue:
    
      - La porta 5022 è accessibile tramite il firewall se Windows Firewall è abilitato nell'RTC principale di SQL Server E04-OCS\_. Los a. lsipt\\. local.
    
      - La porta 5022 è accessibile tramite il firewall se Windows Firewall è abilitato nell'RTC di SQL Server K16-OCS.\_Los a. lsipt.\\local.
    
      - La porta 7022 è accessibile tramite il firewall se Windows Firewall è abilitato nell'RTC di SQL Server AB14-lct.\_Los a. lsipt.\\local.
    
      - Gli account che utilizzano i server SQL in tutti i server SQL primari e mirror hanno l'autorizzazione di lettura/ \\ \\scrittura per la\\condivisione file E04-OCS csdatabackup
    
      - Verificare che il provider di Strumentazione gestione Windows (WMI) sia in uso in tutti questi server. Il cmdlet usa questo provider per trovare le informazioni sull'account per i servizi SQL Server in uso in tutti i server primari, mirror e Witness.
    
      - Verificare che l'account che utilizza questo cmdlet disponga delle autorizzazioni necessarie per creare le cartelle per i dati e i file di log per tutti i server mirror.
    
      - Tieni presente che l'account utente usato dall'istanza SQL per l'esecuzione deve avere l'autorizzazione di lettura/scrittura per la condivisione file. Se la condivisione file si trova in un server diverso e l'istanza SQL esegue un account di sistema locale, è necessario concedere le autorizzazioni di condivisione file al server che ospita l'istanza SQL.

3.  Digitare A e premere INVIO.
    
    Verrà configurato il mirroring.

**Install-CsMirrorDatabase** installa il mirror e configura il mirroring per tutti i database presenti nell'archivio SQL principale. Se si vuole configurare il mirroring solo per database specifici, è possibile usare l'opzione – DatabaseType o se si vuole configurare il mirroring per tutti i database tranne che per pochi, è possibile usare l'opzione-ExcludeDatabaseList, insieme a un elenco di database delimitato da virgole nomi da escludere.

Ad esempio, se si aggiunge l'opzione seguente a **Install-CsMirrorDatabase**, tutti i database eccetto RTCAb e rtcxds verranno speculati.

`-ExcludeDatabaseList rtcab,rtcxds`

Ad esempio, se si aggiunge l'opzione seguente a **Install-CsMirrorDatabase**, verranno rispecchiati solo i database RTCAb, rtcshared e rtcxds.

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a>Rimozione o modifica del mirroring SQL

Per rimuovere il mirroring SQL di un pool in Generatore di topologia, è necessario prima di tutto usare un cmdlet per rimuovere il mirror in SQL Server. Puoi quindi usare generatore di topologia per rimuovere il mirror dalla topologia. Per rimuovere il mirror in SQL Server, usare il cmdlet seguente:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Ad esempio, per rimuovere il mirroring e rilasciare i database per i database degli utenti, digitare quanto segue:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

L' `-DropExistingDatabasesOnMirror` opzione fa sì che i database interessati vengano eliminati dallo specchio.

Quindi, per rimuovere il mirror dalla topologia, eseguire le operazioni seguenti:

1.  In Generatore di topologie fare clic con il pulsante destro del mouse sul pool e scegliere **modifica proprietà**.

2.  Deselezionare **Abilita mirroring di SQL Store** e fare clic su **OK**.

3.  Pubblicare la topologia.

</div>

<div>

## <a name="removing-a-mirroring-witness"></a>Rimozione di un witness di mirroring

Usare questa procedura se si vuole rimuovere il testimone da una configurazione di mirroring del server back-end.

1.  In Generatore di topologie fare clic con il pulsante destro del mouse sul pool e scegliere **modifica proprietà**.

2.  Deselezionare **USA mirroring di SQL Server per abilitare il failover automatico** e fare clic su **OK**.

3.  Pubblicare la topologia.
    
    Dopo aver pubblicato la topologia, generatore di topologie verrà visualizzato un messaggio che include le operazioni seguenti
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    Tuttavia, non seguire questo passaggio e non digitare `Uninstall-CsMirrorDatabase` in modo da disinstallare l'intera configurazione di mirroring.

4.  Per rimuovere solo il testimone dalla configurazione di SQL Server, seguire le istruzioni in "rimuovere il testimone da una sessione di mirroring del database (SQL Server) [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456)" at.

</div>

</div>

<span> </span>

</div>

</div>

</div>

