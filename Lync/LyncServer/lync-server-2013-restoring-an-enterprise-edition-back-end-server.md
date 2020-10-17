---
title: 'Lync Server 2013: ripristino di un server back-end Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9780963614a1d0f5049fdc5226391e2ee2b6d59c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511543"
---
# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>Ripristino di un server back-end Enterprise Edition in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-18_

Utilizzare la procedura descritta in questo argomento nei due casi seguenti:

  - I database primari e mirror di un server back-end Enterprise Edition con mirroring hanno esito negativo.

  - Un server back-end Enterprise Edition che non ha mirroring ha esito negativo.

Se si dispone di un back-end Enterprise Edition con mirroring e solo del database mirror o primario ha esito negativo, vedere [Restoring a mirroring Enterprise Edition back end server in Lync server 2013-Primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) per il ripristino del database primario e [ripristino di un server back-end con mirroring Enterprise Edition in Lync Server 2013-mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) per il ripristino del mirror.

Se l'archivio di gestione centrale ha esito negativo, vedere [ripristino del server che ospita l'archivio di gestione centrale in Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Se si verifica un errore di un server membro Enterprise Edition che non è il server back-end, vedere [Restoring an Enterprise Edition member server in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

<div>


> [!TIP]  
> Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema. È possibile utilizzare questa immagine come punto di rollback, in caso di problemi durante il ripristino. È possibile che si desideri prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare nuovamente i certificati.



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>Per ripristinare un server back-end Enterprise Edition

1.  Iniziare con un server pulito o nuovo che abbia lo stesso nome di dominio completo (FQDN) del computer in cui si è verificato l'errore, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.
    
    <div>
    

    > [!NOTE]  
    > Seguire le procedure di distribuzione dei server dell'organizzazione per eseguire questa operazione.

    
    </div>

2.  Da un account utente membro del gruppo RTCUniversalServerAdmins, eseguire l'accesso al server che si sta ripristinando.

3.  Installare SQL Server 2012 o SQL Server 2008 R2, mantenendo i nomi delle istanze identici a quelli precedenti all'errore.
    
    <div>
    

    > [!NOTE]  
    > A seconda della distribuzione, il server back-end può includere più database collocati o separati. Per installare SQL Server, eseguire la stessa procedura utilizzata originariamente per distribuire il server, inclusi gli account di accesso e le autorizzazioni di SQL Server.

    
    </div>

4.  Dopo aver installato SQL Server, eseguire le operazioni seguenti:
    
    1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.
    
    2.  Fare clic su **Scarica topologia dalla distribuzione esistente** e quindi su **OK**.
    
    3.  Selezionare la topologia e quindi fare clic su **Salva**. Fare clic su **Sì** per confermare la selezione.
    
    4.  Fare clic con il pulsante destro del mouse sul nodo **Lync Server 2013** e quindi scegliere **Pubblica topologia**.
    
    5.  Seguire le istruzioni della procedura guidata **Pubblicare la topologia**. Nella pagina **Crea database** selezionare i database che si desidera ricreare.
        
        <div>
        

        > [!NOTE]  
        > Nella pagina <STRONG>Creare database</STRONG> verranno visualizzati solo i database autonomi.

        
        </div>
    
    6.  Se si esegue il ripristino di un back-end con mirroring, continuare a seguire il resto della procedura guidata fino a quando non viene visualizzato il prompt di **creazione del database mirror** . Selezionare il database che si desidera installare e completare il processo.
    
    7.  Seguire il resto della procedura guidata e quindi fare clic su **Fine**.
    
    <div>
    

    > [!TIP]  
    > Anziché eseguire Generatore di topologie, è possibile utilizzare il cmdlet <STRONG>Install-CsDatabase</STRONG> per creare ogni database e il cmdlet <STRONG>Install-CsMirrorDatabase</STRONG> per configurare il mirroring. Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.

    
    </div>

5.  Ripristinare i dati degli utenti eseguendo le operazioni seguenti:
    
    1.  Copiare ExportedUserData.zip da $Backup \\ in una directory locale.
    
    2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.
    
    3.  Prima di ripristinare i dati degli utenti, è necessario arrestare i servizi Lync. A tale scopo, digitare:
        
            Stop-CsWindowsService
    
    4.  Per ripristinare i dati utente, nella riga di comando digitare:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Ad esempio:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  Riavviare i servizi di Lync digitando:
        
            Start-CsWindowsService

6.  Se è stato distribuito Response Group in questo pool, ripristinare i dati di configurazione di Response Group. Per informazioni dettagliate, vedere [Restoring Response Group Settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

7.  Se si sta ripristinando un server back-end che includeva il database di archiviazione o di monitoraggio, ripristinare i dati di archiviazione o monitoraggio mediante uno strumento di SQL Server, ad esempio SQL Server Management Studio. Per informazioni dettagliate, vedere [Restoring monitoring or Archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

