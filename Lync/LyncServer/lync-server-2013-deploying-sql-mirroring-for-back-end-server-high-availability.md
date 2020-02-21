---
title: Distribuzione del mirroring di SQL per la disponibilità elevata del server back-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 577d6bb312ae2b31f96fed5f3e5b02e84844adf6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a>Distribuzione del mirroring di SQL per la disponibilità elevata del server back-end in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-01-08_

Per distribuire il mirroring SQL, i server devono eseguire almeno SQL Server 2008 R2. Questa versione deve essere eseguita da tutti i server coinvolti: il server primario, mirror, e di controllo. Per informazioni dettagliate, [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921)vedere.

In generale, la configurazione del mirroring SQL tra due server di back-end con un server di controllo richiede che:

  - La versione di SQL Server del server primario supporti il mirroring SQL.

  - I server primario, mirror e di controllo (se distribuito) abbiano la stessa versione di SQL Server.

  - Il server primario e mirror abbiano la stessa edizione di SQL Server. Il server di controllo può avere un'edizione diversa.

Per le procedure consigliate SQL in termini di supporto per le versioni di SQL per un ruolo di controllo, vedere "database mirroring witness" in [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345)MSDN Library all'indirizzo.

È possibile utilizzare Generatore di topologie per distribuire il mirroring SQL. È possibile selezionare un'opzione in Generatore di topologie per il mirroring dei database e il generatore di topologie configura il mirroring, inclusa la configurazione di un controllo, se si desidera, quando si pubblica la topologia. Il server di controllo viene rimosso o configurato contemporaneamente alla rimozione o configurazione del mirror. Non esiste un comando separato che consente di distribuire o rimuovere unicamente un server di controllo.

Per configurare il mirroring del server, è prima necessario configurare correttamente le autorizzazioni del database SQL. Per informazioni dettagliate, vedere "configurare gli account di accesso per il mirroring del database o i gruppi di disponibilità AlwaysOn [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454)(SQL Server)" all'indirizzo.

Con il mirroring SQL, la modalità di recupero del database è impostata sempre su **Completa**. Ciò significa che è necessario monitorare le dimensioni del log delle transizioni ed eseguire regolarmente il backup dei log più grandi, per evitare che la memoria del disco dei server di back-end si riempia. La frequenza dei backup dei log delle transizioni dipende dal tasso di crescita dei log, che a sua volta dipende dalle transazioni del database relative alle attività degli utenti nel pool Front End. Per pianificare correttamente, è consigliabile determinare il tasso di crescita stimato del log delle transazioni per il carico di lavoro della distribuzione di Lync. I seguenti articoli contengono informazioni aggiuntive sul backup SQL e la gestione dei log:

  - Modelli di ripristino di database: "modelli di ripristino (SQL Server)" all'indirizzo[https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)

  - Panoramica del backup: "Panoramica del backup (SQL Server)" all'indirizzo[https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)

  - Log delle transazioni di backup: "eseguire il backup di un log delle transazioni (SQL Server)" all'indirizzo[https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)

Nel mirroring SQL è possibile configurare la topologia per il mirroring al momento della creazione dei pool, o in seguito.



> [!IMPORTANT]
> L'utilizzo di generatore di topologie o cmdlet per configurare e rimuovere il mirroring SQL è supportato solo quando i server primari, mirror e Witness (se necessario) appartengono tutti allo stesso dominio. Per configurare il mirroring SQL tra server su domini diversi, vedere la documentazione relativa a SQL Server.





> [!IMPORTANT]
> Quando si apportano modifiche a una relazione di mirroring di un database di back end, è necessario riavviare tutti i Front End Server nel pool.<BR>Per una modifica del mirroring, ad esempio la modifica del percorso di un mirror, è necessario utilizzare Generatore di topologie per eseguire questi tre passaggi: 
> <OL>
> <LI>
> <P>Rimuovere il mirroring dal server mirror meno recente.</P>
> <LI>
> <P>Aggiungere il mirroring al nuovo server mirror.</P>
> <LI>
> <P>Pubblicare la topologia.</P></LI></OL>




> [!NOTE]
> È necessario creare una condivisione file per la scrittura dei file mirror e il servizio in cui SQL Server e SQL Agent sono in esecuzione in accesso in lettura/scrittura. Se il servizio SQL Server è in esecuzione nel contesto di servizio di rete, è possibile &lt;aggiungere&gt; il &lt;dominio&#92;SqlServerName&gt;$ dei server SQL Principal e mirror alle autorizzazioni di condivisione. $ È importante per identificare che si tratta di un account computer.


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>Per configurare il mirroring SQL durante la creazione di un pool in Generatore di topologie

1.  Nella pagina **Definisci archivio SQL**, fare clic su **Nuovo** accanto alla casella **Archivio SQL**.

2.  Nella pagina **Definisci nuovo archivio SQL**, specificare l'archivio primario, selezionare **L'istanza SQL è in relazione di mirroring**, specificare il numero di porta del mirroring SQL (il valore predefinito è 5022), quindi fare clic su **OK**.

3.  Nella pagina **Definisci archivio SQL**, selezionare **Abilita archivio mirroring SQL**.

4.  Nella pagina **Definisci nuovo archivio SQL**, specificare l'archivio SQL da utilizzare come mirror. Selezionare **L'istanza SQL è in relazione di mirroring**, specificare il numero di porta (il valore predefinito è 5022), quindi fare clic su **OK**.

5.  Se si desidera un'istanza di controllo per il mirror, effettuare le operazioni seguenti:
    
    1.  Selezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico**.
    
    2.  Nella pagina **Definisci archivio SQL**, selezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** e specificare l'archivio SQL da utilizzare per il controllo.
    
    3.  Specificare il numero di porta (il valore predefinito è 7022) e fare clic su **OK**

6.  Dopo aver completato la definizione del pool Front end e di tutti gli altri ruoli nella topologia, utilizzare Generatore di topologie per pubblicare la topologia. Quando la topologia viene pubblicata, se il pool Front end che ospita l'archivio di gestione centrale dispone del mirroring SQL abilitato, verrà visualizzata un'opzione per creare i database dell'archivio SQL primario e del mirror.
    
    Fare clic su **Impostazioni** e digitare il percorso da utilizzare come condivisione file per il backup del mirroring.
    
    Fare clic su **OK** e **Avanti** per creare i database e pubblicare la topologia. I server di mirroring e di controllo (se specificato) saranno così distribuiti.

È possibile utilizzare Generatore di topologie per modificare le proprietà di un pool già esistente per abilitare il mirroring SQL.

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>Per aggiungere il mirroring SQL a un pool Front end esistente in Generatore di topologie

1.  In Generatore di topologie fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.

2.  Selezionare **Abilita mirroring dell'archivio SQL**, quindi fare clic su **Nuovo** accanto a **Mirroring dell'archivio SQL**.

3.  Specificare l'archivio SQL che si desidera utilizzare come mirror.

4.  Selezionare **L'istanza SQL è in relazione di mirroring**, specificare il numero di porta per il mirroring SQL (il valore predefinito è 5022), quindi fare clic su **OK**.

5.  Per configurare un'istanza di controllo, selezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** e fare clic su **Nuovo**.

6.  Specificare l'archivio SQL che si desidera utilizzare come istanza di controllo.

7.  Selezionare **L'istanza SQL è in relazione di mirroring**, specificare il numero di porta per il mirroring SQL (il valore predefinito è 7022), quindi fare clic su **OK**.

8.  Fare clic su **OK**.

9.  Pubblicare la topologia. Verrà richiesto di installare il database.
    
    Durante il processo di pubblicazione della topologia verrà richiesto di definire un percorso di condivisione file. I server SQL che partecipano al mirroring devono disporre dell'accesso in lettura/scrittura alla condivisione file per il mirror da stabilire.

A questo punto è necessario installare il database prima di passare alla procedura successiva.

Quando si configura il mirroring SQL, è necessario tenere a mente alcuni punti:

  - Se esiste già un endpoint del mirroring, sarà riutilizzato insieme alle porte definite qui, e saranno ignorate quelle specificate nella topologia.

  - Le porte già allocate ad altre applicazioni sullo stesso server, comprese quelle allocate ad altre istanze di SQL, non devono essere utilizzate per le nuove istanze di SQL installate. Pertanto, se si ha più di una istanza SQL installata sullo stesso server, queste devono utilizzare porte differenti per il mirroring. Per ulteriori dettagli, vedere:
    
      - "Specificare un indirizzo di rete del server (mirroring del database)" in MSDN Library all'[https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)
    
      - "Endpoint del mirroring del database (SQL Server)" all'indirizzo[https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Utilizzo dei cmdlet di Lync Server Management Shell per configurare il mirroring SQL

Il modo più semplice per configurare il mirroring consiste nell'utilizzo di generatore di topologie, ma è possibile farlo anche utilizzando i cmdlet.

1.  Aprire una finestra di Lync Server Management Shell ed eseguire il cmdlet seguente:
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    Ad esempio:
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    Verrà visualizzato quanto segue:
    
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

2.  Verificare che:
    
      - La porta 5022 è accessibile tramite il firewall se Windows Firewall è abilitato nell'RTC SQL Server E04-OCS. Los\_a. OCS. local\\primario.
    
      - La porta 5022 è accessibile tramite il firewall se Windows Firewall è abilitato nell'RTC SQL Server K16-OCS. Los\_a. OCS. local\\del mirror.
    
      - La porta 7022 è accessibile tramite il firewall se Windows Firewall è abilitato nell'RTC SQL Server AB14-lct. Los\_a. OCS. local\\di controllo.
    
      - Gli account che eseguono i server SQL su tutti i server SQL primario e mirror dispongono dell'autorizzazione di lettura/ \\ \\scrittura per la\\condivisione file E04-OCS csdatabackup
    
      - Verificare che il provider della Strumentazione gestione Windows (WMI) sia eseguito su tutti questi server. Il cmdlet si serve di questo provider per trovare le informazioni sull'account relative ai servizi di SQL Server eseguiti su tutti i server primari, mirror e di controllo.
    
      - Verificare che l'account sul quale è eseguito il cmdlet abbia le autorizzazioni necessarie per creare le cartelle per i dati e i file dei log per tutti i server mirror.
    
      - Si noti che l'account utente utilizzato dall'istanza SQL per la propria esecuzione deve essere dotato di autorizzazioni di lettura e scrittura per la condivisione file. Se la condivisione file si trova su un server diverso e l'istanza SQL esegue un account di sistema locale, è necessario concedere autorizzazioni per la condivisione file al server che ospita l'istanza SQL.

3.  Digitare A e premere INVIO.
    
    Sarà configurato il mirroring.

**Install-CsMirrorDatabase** installa il mirror e configura il mirroring per tutti i database presenti nell'archivio SQL primario. Se si desidera configurare il mirroring solo per database specifici, è possibile utilizzare l'opzione – DatabaseType oppure se si desidera configurare il mirroring per tutti i database ad eccezione di alcuni, è possibile utilizzare l'opzione-ExcludeDatabaseList, insieme a un elenco di database separato da virgole. nomi da escludere.

Ad esempio, se si aggiunge l'opzione seguente a **Install-CsMirrorDatabase**, si eseguirà il mirroring per tutti i database ad eccezione di rtcab e rtcxds.

`-ExcludeDatabaseList rtcab,rtcxds`

Ad esempio, se si aggiunge l'opzione seguente a **Install-CsMirrorDatabase**, si eseguirà il mirroring unicamente per i database rtcab e rtcxds.

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a>Rimozione o modifica del mirroring SQL

Per rimuovere il mirroring SQL da un pool in Generatore di topologie, è prima necessario utilizzare un cmdlet per la rimozione del mirror in SQL Server. È quindi possibile utilizzare Generatore di topologie per rimuovere il mirror dalla topologia. Per rimuovere il mirror in SQL Server, utilizzare il cmdlet seguente:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Ad esempio, per rimuovere il mirroring ed eliminare i database degli utenti, digitare:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

L' `-DropExistingDatabasesOnMirror` opzione fa in modo che i database danneggiati vengano eliminati dal mirror.

Per rimuovere il mirror dalla topology, eseguire le operazioni seguenti:

1.  In Generatore di topologie, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica proprietà**.

2.  Deselezionare **Abilita archivio mirroring SQL** e fare clic su **OK**.

3.  Pubblicare la topologia.

</div>

<div>

## <a name="removing-a-mirroring-witness"></a>Rimozione di un Server di controllo del mirroring

Utilizzare questa procedura se è necessario rimuovere il controllo da una configurazione del mirroring del server back-end.

1.  In Generatore di topologie, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica proprietà**.

2.  Deselezionare **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** e fare clic su **OK**.

3.  Pubblicare la topologia.
    
    Dopo aver pubblicato la topologia, generatore di topologie verrà visualizzato un messaggio che include gli elementi seguenti:
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    Tuttavia, non seguire questo passaggio e non digitare `Uninstall-CsMirrorDatabase` come che disinstalli l'intera configurazione del mirroring.

4.  Per rimuovere solo il controllo dalla configurazione di SQL Server, seguire le istruzioni riportate in "rimuovere il controllo da una sessione di mirroring del database ( [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456)SQL Server)" all'indirizzo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

