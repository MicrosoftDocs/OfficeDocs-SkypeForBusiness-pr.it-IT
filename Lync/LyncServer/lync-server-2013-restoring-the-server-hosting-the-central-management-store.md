---
title: "Lync Server 2013: ripristino del server che ospita l'archivio di gestione centrale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b10c83b5d81c28de21264a340fee3460ebd4ccdb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>Ripristino del server che ospita l'archivio di gestione centrale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Una distribuzione di Lync Server dispone di un unico archivio di gestione centrale, una copia di cui viene replicata in ogni server che esegue un ruolo del server Lync Server. In questo argomento viene descritto come ripristinare un server back-end o uno Standard Edition che ospita l'archivio di gestione centrale.

Per individuare il pool in cui si trova il server di gestione centrale, aprire Generatore di topologie, fare clic su **Lync Server**e quindi cercare nel riquadro destro in **server di gestione centrale**.

Se il server back-end che ospita l'archivio di gestione centrale si trova in una configurazione con mirroring e il database mirror è ancora funzionante, è consigliabile eseguire un backup di questo mirror ancora funzionante e quindi effettuare un ripristino completo sia sul database primario che sul database mirror, utilizzando questo backup, seguendo la procedura di ripristino seguente. Questa operazione è necessaria perché il ripristino di back-end richiede la modifica e la pubblicazione della topologia e questo può essere eseguito solo se il database primario che ospita il CMS è operativo. Si noti inoltre che i ruoli del database primario e mirror non possono essere intercambiati se non è possibile pubblicare la topologia.

<div>


> [!NOTE]  
> Se un server back-end o un server Standard Edition che non ospita l'archivio di gestione centrale non ha avuto esito negativo, vedere <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition back end server in Lync server 2013</A> o <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a server Standard Edition in Lync Server 2013</A>. Se un server back-end che ospita l'archivio di gestione centrale è in una configurazione con mirroring e solo il mirror ha esito negativo, vedere <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirroring Enterprise Edition back end server in Lync server 2013-mirror</A>. Se si è verificato un errore in un altro server, vedere <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync server 2013</A>.



</div>

<div>


> [!TIP]  
> Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema. È possibile utilizzare questa immagine come punto di rollback, in caso di problemi durante il ripristino. È possibile che si desideri prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare nuovamente i certificati.



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>Per ripristinare l'archivio di gestione centrale

1.  Iniziare con un server pulito o nuovo che abbia lo stesso nome di dominio completo (FQDN) del computer in cui si è verificato l'errore, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.
    
    <div>
    

    > [!NOTE]  
    > Seguire le procedure di distribuzione dei server dell'organizzazione per eseguire questa operazione.

    
    </div>

2.  Da un account utente membro del gruppo RTCUniversalServerAdmins e del gruppo Administrators locale, accedere al server che si sta ripristinando.

3.  Se si esegue il ripristino di un server Standard Edition, ripristinare l'archivio file copiando l'archivio file appropriato da $Backup al percorso dell'archivio file nel server e quindi condividere la cartella.
    
    <div>
    

    > [!IMPORTANT]  
    > Il percorso e il nome del file dell'archivio file ripristinato devono essere identici a quelli dell'archivio file di cui è stato eseguito il backup in modo che i componenti che utilizzano i file possano accedervi.

    
    </div>

4.  Eseguire una delle operazioni seguenti:
    
      - Se si sta installando un server Standard Edition, passare alla cartella o al supporto di installazione di Lync Server e quindi avviare la distribuzione guidata di Lync \\server\\in\\Setup amd64 Setup. exe. Nella distribuzione guidata fare clic su **prepara primo server Standard Edition** e seguire la procedura guidata per installare l'archivio di gestione centrale.
    
      - Se si sta installando un server back-end Enterprise, installare SQL Server 2012 o SQL Server 2008 R2, mantenendo i nomi delle istanze uguali a quelli precedenti all'errore.
        
        <div>
        

        > [!NOTE]  
        > A seconda del server che si sta ripristinando e della distribuzione, è possibile che il server includa più database collocati o separati. Seguire la stessa procedura di installazione di SQL Server utilizzata in origine per la distribuzione del server, inclusi le autorizzazioni e gli account di accesso di SQL Server.

        
        </div>

5.  Da un front end server, avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi **Lync Server Management Shell**.

6.  Ricreare l'archivio di gestione centrale. Nella riga di comando digitare il comando seguente:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Ad esempio:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  Impostare il punto di controllo dei servizi di dominio Active Directory per l'archivio di gestione centrale. Nella riga di comando digitare il comando seguente:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Ad esempio:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > Se si perde il punto di connessione, è possibile eseguire di nuovo questo cmdlet.

    
    </div>

8.  Importare i dati dell'archivio di gestione centrale da $Backup. Nella riga di comando digitare il comando seguente:
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    Ad esempio:
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  Abilitare le modifiche che sono state apportate. Nella riga di comando digitare:
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Dopo aver abilitato la topologia, è possibile trovare il relativo documento nel database.

    
    </div>

10. Se si esegue il ripristino di un server back-end Enterprise Edition che ha ospitato anche il CMS o se è necessario ricreare un mirror del CMS, seguire questo passaggio. In caso contrario, passare al passaggio 11.
    
    Installare i database autonomi eseguendo le operazioni seguenti:
    
    1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.
    
    2.  Fare clic su **Scarica topologia dalla distribuzione esistente** e quindi su **OK**.
    
    3.  Selezionare la topologia e quindi fare clic su **Salva**. Fare clic su **Sì** per confermare la selezione.
    
    4.  Fare clic con il pulsante destro del mouse sul nodo **Lync Server 2013** e quindi scegliere **Installa database**.
    
    5.  Seguire la procedura guidata di **installazione del database** . Se si esegue il ripristino di un database diverso da quello dell'archivio di gestione centrale nel server, nella pagina **Crea database** selezionare i database che si desidera ricreare.
        
        <div>
        

        > [!NOTE]  
        > Nella pagina <STRONG>Creare database</STRONG> verranno visualizzati solo i database autonomi. I database collocati vengono creati durante l'esecuzione della distribuzione guidata di Lync Server.

        
        </div>
    
    6.  Se si esegue il ripristino di un server back-end con mirroring, continuare a seguire il resto della procedura guidata fino a quando non si giunge a una richiesta di creazione di un database mirror. Selezionare il database che si desidera installare e completare il processo.
    
    7.  Seguire il resto della procedura guidata e quindi fare clic su **Fine**.
    
    <div>
    

    > [!TIP]  
    > Anziché eseguire Generatore di topologie, è possibile utilizzare il cmdlet <STRONG>Install-CsDatabase</STRONG> per creare ogni database e il cmdlet <STRONG>Install-CsMirrorDatabase</STRONG> per configurare il mirroring. Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.

    
    </div>

11. Se si esegue il ripristino di un server Standard Edition, passare alla cartella o al supporto di installazione di Lync Server e avviare la distribuzione guidata di \\Lync\\server\\in Setup amd64 Setup. exe. Utilizzare la distribuzione guidata di Lync Server per eseguire le operazioni seguenti:
    
    1.  Eseguire **Passaggio 1: Installazione dell'archivio di configurazione locale** per installare i file della configurazione locale.
    
    2.  Eseguire il **passaggio 2: installazione o rimozione dei componenti di Lync Server** per installare i ruoli del server Lync Server.
    
    3.  Eseguire **Passaggio 3: Richiesta, installazione o assegnazione dei certificati** per assegnare i certificati.
    
    4.  Eseguire **Passaggio 4: Avvio servizi** per avviare i servizi nel server.
    
    Per informazioni dettagliate sull'esecuzione della distribuzione guidata, vedere la documentazione relativa alla distribuzione per il ruolo del server che si sta ripristinando.

12. Ripristinare i dati utente eseguendo le operazioni seguenti:
    
    1.  Copiare ExportedUserData. zip da $Backup\\ in una directory locale.
    
    2.  Prima di ripristinare i dati degli utenti, è necessario arrestare i servizi Lync. A tale scopo, digitare:
        
            Stop-CsWindowsService
    
    3.  Per ripristinare i dati utente, nella riga di comando digitare:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Ad esempio:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Riavviare i servizi di Lync digitando:
        
            Start-CsWindowsService

13. Ripristinare i dati delle informazioni sulla posizione nell'archivio di gestione centrale. Nella riga di comando digitare il comando seguente:
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    Ad esempio:
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. Se è stato distribuito Response Group nel pool o nel server Standard Edition, ripristinare i dati di configurazione di Response Group. Per informazioni dettagliate, vedere [Restoring Response Group Settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

15. Se si esegue il ripristino di un server back-end che include database di archiviazione o di monitoraggio, ripristinare i dati di archiviazione o di monitoraggio utilizzando uno strumento di gestione di SQL Server, ad esempio SQL Server Management Studio. Per informazioni dettagliate, vedere [Restoring monitoring or Archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

