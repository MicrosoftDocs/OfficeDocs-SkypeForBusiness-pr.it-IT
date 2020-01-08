---
title: 'Lync Server 2013: ripristino di un server back-end Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e0121ee654846bcb60acc6da6847995b967a880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>Ripristino di un server back-end Enterprise Edition in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-18_

Usare la procedura descritta in questo argomento nei due casi seguenti:

  - I database primari e mirror di un server back-end Enterprise Edition con mirroring non riescono.

  - Un server back-end Enterprise Edition che non ha un mirroring non riesce.

Se si ha un back-end di Enterprise Edition con mirroring e il database mirror o PRIMARY non riesce, vedere [ripristino di un server back-end aziendale con mirroring in Lync server 2013-principale](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) per il ripristino del database primario e [ripristino di un server back-end di Enterprise Edition con mirroring in Lync Server 2013-mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) per il ripristino dello specchio.

Se l'archivio di gestione centrale non riesce, vedere [ripristino del server che ospita l'archivio di gestione centrale in Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Se un server membro di Enterprise Edition che non è il server back-end non riesce, vedere [ripristino di un server membro di Enterprise Edition in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

<div>


> [!TIP]  
> Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema. È possibile usare questa immagine come punto di rollback, in caso di problemi durante il ripristino. Potrebbe essere necessario prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare di nuovo i certificati.



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>Per ripristinare un server back-end Enterprise Edition

1.  Iniziare con un nuovo server pulito o con lo stesso nome di dominio completo (FQDN) del computer non riuscito, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.
    
    <div>
    

    > [!NOTE]  
    > Per eseguire questo passaggio, seguire le procedure di distribuzione del server dell'organizzazione.

    
    </div>

2.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere al server che si sta ripristinando.

3.  Installare SQL Server 2012 o SQL Server 2008 R2, mantenendo i nomi delle istanze come prima dell'errore.
    
    <div>
    

    > [!NOTE]  
    > A seconda della distribuzione, il server back-end può includere più database collocati o separati. Seguire la stessa procedura per installare SQL Server usato in origine per distribuire il server, incluse le autorizzazioni di SQL Server e gli accessi.

    
    </div>

4.  Dopo l'installazione di SQL Server, eseguire le operazioni seguenti:
    
    1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.
    
    2.  Fare clic su **Scarica topologia dalla distribuzione esistente**e quindi fare clic su **OK**.
    
    3.  Selezionare la topologia e quindi fare clic su **Salva**. Fare clic su **Sì** per confermare la selezione.
    
    4.  Fare clic con il pulsante destro del mouse sul nodo **Lync Server 2013** e quindi scegliere **Pubblica topologia**.
    
    5.  Seguire la procedura guidata **pubblica la topologia** . Nella pagina **Crea database** selezionare i database che si desidera ricreare.
        
        <div>
        

        > [!NOTE]  
        > Nella pagina <STRONG>Crea database</STRONG> sono visualizzati solo database autonomi.

        
        </div>
    
    6.  Se si esegue il ripristino di un back-end con mirroring, continuare a seguire il resto della procedura guidata fino a quando non viene visualizzato il messaggio **Crea mirror database** . Selezionare il database che si vuole installare e completare il processo.
    
    7.  Seguire il resto della procedura guidata e quindi fare clic su **fine**.
    
    <div>
    

    > [!TIP]  
    > Invece di eseguire Generatore di topologie, è possibile usare il cmdlet <STRONG>Install-CsDatabase</STRONG> per creare ogni database e il cmdlet <STRONG>Install-CsMirrorDatabase</STRONG> per configurare il mirroring. Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.

    
    </div>

5.  Ripristinare i dati degli utenti eseguendo le operazioni seguenti:
    
    1.  Copiare ExportedUserData. zip da $Backup\\ a una directory locale.
    
    2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.
    
    3.  Prima di ripristinare i dati utente, è necessario arrestare i servizi Lync. A tale scopo, digitare:
        
            Stop-CsWindowsService
    
    4.  Per ripristinare i dati utente, nella riga di comando digitare:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Ad esempio:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  Riavviare i servizi Lync digitando:
        
            Start-CsWindowsService

6.  Se il gruppo di risposte è stato distribuito in questo pool, ripristinare i dati di configurazione del gruppo di risposte. Per informazioni dettagliate, vedere [ripristino delle impostazioni dei gruppi di risposte in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

7.  Se si sta ripristinando un server di back-end che includeva l'archiviazione o il monitoraggio dei database, ripristinare i dati di archiviazione o monitoraggio tramite uno strumento di SQL Server, ad esempio SQL Server Management Studio. Per informazioni dettagliate, vedere [ripristinare il monitoraggio o l'archiviazione dei dati in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

