---
title: "Lync Server 2013: ripristino del server che ospita l'Central Management store"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95696c682e7acfba32e4f9a2bfd71ba988f22243
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>Ripristino del server che ospita l'archivio di gestione centrale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Una distribuzione di Lync Server ha un unico Central Management store, una copia di cui viene replicata in ogni server che ha un ruolo di server Lync Server. Questo argomento descrive come ripristinare un server di back-end o un server Standard Edition che ospita l'Central Management store.

Per trovare il pool in cui si trova il server di gestione centrale, aprire Generatore di topologie, fare clic su **Lync Server**e cercare nel riquadro destro in **Central Management Server**.

Se il server di back-end che ospita l'archivio di gestione centrale è in una configurazione con mirroring e il database mirror è ancora funzionante, è consigliabile eseguire un backup di questo mirror ancora funzionante e quindi effettuare un ripristino completo sia nel database principale che in quello database mirror, usando questo backup, seguendo la procedura di ripristino seguente. Questa operazione è necessaria perché il ripristino di back-end richiede la modifica e la pubblicazione della topologia e questa operazione può essere eseguita solo se il database primario CMS ospitante è operativo. Si noti inoltre che i ruoli del database primario e mirror non possono essere intercambiati se non è possibile pubblicare la topologia.

<div>


> [!NOTE]  
> Se un server back-end o un server Standard Edition che non ospita il Central Management store non è riuscito, vedere <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">ripristino di un server back-end Enterprise Edition in Lync server 2013</A> o <A href="lync-server-2013-restoring-a-standard-edition-server.md">ripristino di un server standard in Lync Server 2013</A>. Se un server back-end che ospita l'archivio di gestione centrale è in una configurazione speculare e solo lo specchio non riesce, vedere <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">ripristino di un server back-end Enterprise con mirroring in Lync server 2013-mirror</A>. Se un altro server non è riuscito, vedere <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">ripristino di un server membro di Enterprise Edition in Lync server 2013</A>.



</div>

<div>


> [!TIP]  
> Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema. È possibile usare questa immagine come punto di rollback, in caso di problemi durante il ripristino. Potrebbe essere necessario prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare di nuovo i certificati.



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>Per ripristinare il Central Management store

1.  Iniziare con un nuovo server pulito o con lo stesso nome di dominio completo (FQDN) del computer non riuscito, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.
    
    <div>
    

    > [!NOTE]  
    > Per eseguire questo passaggio, seguire le procedure di distribuzione del server dell'organizzazione.

    
    </div>

2.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins e del gruppo Administrators locale, accedere al server che si sta ripristinando.

3.  Se si sta ripristinando un server Standard Edition, ripristinare l'archivio file copiando l'archivio file appropriato da $Backup nella posizione dell'archivio file nel server e quindi condividere la cartella.
    
    <div>
    

    > [!IMPORTANT]  
    > Il percorso e il nome file dell'archivio file ripristinato devono essere esattamente gli stessi dell'archivio di file di cui è stato eseguito il backup in modo che i componenti che usano i file possano accedervi.

    
    </div>

4.  Esegui una delle operazioni seguenti:
    
      - Se si sta installando un server Standard Edition, passare alla cartella di installazione o al supporto di Lync Server, quindi avviare la distribuzione guidata di Lync \\server\\in\\Setup amd64 Setup. exe. Nella distribuzione guidata fare clic su **prepara primo server Standard Edition** e seguire la procedura guidata per installare Central Management store.
    
      - Se si sta installando un server back-end aziendale, installare SQL Server 2012 o SQL Server 2008 R2, mantenendo i nomi delle istanze come prima dell'errore.
        
        <div>
        

        > [!NOTE]  
        > A seconda del server che si sta ripristinando e della distribuzione, il server può includere più database collocati o separati. Seguire la stessa procedura per installare SQL Server usato in origine per distribuire il server, incluse le autorizzazioni di SQL Server e gli accessi.

        
        </div>

5.  Da un server front-end avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

6.  Ricreare l'archivio di gestione centrale. Nella riga di comando digitare:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Ad esempio:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  Impostare il punto di controllo Active Directory Domain Services per l'Central Management store. Nella riga di comando digitare:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Ad esempio:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > Se si perde il punto di connessione, è possibile rieseguire questo cmdlet.

    
    </div>

8.  Importare i dati di Central Management store da $Backup. Nella riga di comando digitare:
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    Ad esempio:
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  Abilitare le modifiche appena apportate. Nella riga di comando digitare:
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Dopo aver abilitato la topologia, è possibile trovare il documento di topologia nel database.

    
    </div>

10. Se si esegue il ripristino di un server back-end Enterprise Edition che ospitava anche il CMS o se è necessario ricreare uno specchio del CMS, seguire questo passaggio. In caso contrario, passare al passaggio 11.
    
    Installare i database autonomi eseguendo le operazioni seguenti:
    
    1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.
    
    2.  Fare clic su **Scarica topologia dalla distribuzione esistente**e quindi fare clic su **OK**.
    
    3.  Selezionare la topologia e quindi fare clic su **Salva**. Fare clic su **Sì** per confermare la selezione.
    
    4.  Fare clic con il pulsante destro del mouse sul nodo **Lync Server 2013** e quindi scegliere **Installa database**.
    
    5.  Seguire la procedura guidata **Installa database** . Se si esegue il ripristino di un database diverso da Central Management store su questo server, nella pagina **Crea database** selezionare i database che si desidera ricreare.
        
        <div>
        

        > [!NOTE]  
        > Nella pagina <STRONG>Crea database</STRONG> sono visualizzati solo database autonomi. I database collocati vengono creati quando si esegue la distribuzione guidata di Lync Server.

        
        </div>
    
    6.  Se si sta ripristinando un server back-end con mirroring, continuare a seguire il resto della procedura guidata finché non viene visualizzato un messaggio di creazione di database mirror. Selezionare il database che si vuole installare e completare il processo.
    
    7.  Seguire il resto della procedura guidata e quindi fare clic su **fine**.
    
    <div>
    

    > [!TIP]  
    > Invece di eseguire Generatore di topologie, è possibile usare il cmdlet <STRONG>Install-CsDatabase</STRONG> per creare ogni database e il cmdlet <STRONG>Install-CsMirrorDatabase</STRONG> per configurare il mirroring. Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.

    
    </div>

11. Se si sta ripristinando un server Standard Edition, passare alla cartella di installazione o al supporto di Lync Server e avviare la distribuzione guidata di Lync \\server\\in\\Setup amd64 Setup. exe. Usare la distribuzione guidata di Lync Server per eseguire le operazioni seguenti:
    
    1.  Eseguire il **passaggio 1: installare l'archivio configurazione locale** per installare i file di configurazione locali.
    
    2.  Eseguire il **passaggio 2: configurare o rimuovere i componenti di Lync Server** per installare i ruoli di Lync Server Server.
    
    3.  Eseguire il **passaggio 3: richiedere, installare o assegnare certificati** per assegnare i certificati.
    
    4.  Eseguire il **passaggio 4: avviare i servizi** per avviare i servizi nel server.
    
    Per informazioni dettagliate sull'eseguire la distribuzione guidata, vedere la documentazione relativa alla distribuzione per il ruolo del server che si sta ripristinando.

12. Ripristinare i dati degli utenti eseguendo le operazioni seguenti:
    
    1.  Copiare ExportedUserData. zip da $Backup\\ a una directory locale.
    
    2.  Prima di ripristinare i dati utente, è necessario arrestare i servizi Lync. A tale scopo, digitare:
        
            Stop-CsWindowsService
    
    3.  Per ripristinare i dati utente, nella riga di comando digitare:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Ad esempio:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Riavviare i servizi Lync digitando:
        
            Start-CsWindowsService

13. Ripristinare i dati delle informazioni sulla posizione in Central Management store. Nella riga di comando digitare:
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    Ad esempio:
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. Se il gruppo di risposte è stato distribuito in questo pool o in un server Standard Edition, ripristinare i dati di configurazione di Response Group. Per informazioni dettagliate, vedere [ripristino delle impostazioni dei gruppi di risposte in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

15. Se si ripristina un server back-end che include l'archiviazione o il monitoraggio dei database, ripristinare i dati di archiviazione o monitoraggio tramite uno strumento di gestione di SQL Server, ad esempio SQL Server Management Studio. Per informazioni dettagliate, vedere [ripristinare il monitoraggio o l'archiviazione dei dati in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

