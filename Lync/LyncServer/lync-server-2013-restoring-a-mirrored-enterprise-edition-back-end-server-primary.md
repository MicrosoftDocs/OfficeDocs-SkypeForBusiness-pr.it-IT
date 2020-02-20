---
title: Ripristino di un server back-end Enterprise Edition con mirroring-Primary
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dfc3f9a44adbd4967e3d32ac7a515a55bc5d974
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>Ripristino di un server back-end Enterprise Edition con mirroring in Lync Server 2013-Primary

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-17_

Se si dispone di un server back-end Enterprise Edition in una configurazione con mirroring e solo il database primario ha esito negativo, seguire le procedure descritte in questa sezione. Se il database primario e il mirror non riescono, vedere [Restoring an Enterprise Edition back end server in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Se solo il mirror ha esito negativo, vedere [Restoring a mirroring Enterprise Edition back end server in Lync server 2013-mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md). Se il database che ospita l'archivio di gestione centrale ha esito negativo, vedere [ripristino del server che ospita l'archivio di gestione centrale in Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Se si verifica un errore di un server membro Enterprise Edition che non è il server back-end, vedere [Restoring an Enterprise Edition member server in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema. È possibile utilizzare questa immagine come punto di rollback, in caso di problemi durante il ripristino. È possibile che si desideri prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare nuovamente i certificati.

In questo argomento, il database primario di esempio avrà un nome di dominio completo (FQDN) di BE1.contoso.com e il database mirror avrà un FQDN di BE2.contoso.com.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>Per ripristinare un database primario del server back-end Enterprise Edition

1.  Accedere a un front end server da un account utente membro del gruppo RTCUniversalServerAdmins.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Forzare il failover di tutti i database configurati verso il mirror. Per ognuno dei tipi di database configurati in questo server, digitare il cmdlet seguente:
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    Ad esempio:
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > Se è stato configurato il database back-end per l'utilizzo del mirroring sincronizzato con un'istanza di controllo, il failover è automatico.

    
    </div>

4.  Dopo aver completato il failover, eseguire le operazioni seguenti:
    
      - Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.
    
      - Disabilitare il mirroring sul server back-end: fare clic con il pulsante destro del mouse sul pool in **pool Enterprise Edition front end** e scegliere **modifica proprietà**. Nella scheda **generale** , in **associazioni**, deselezionare la casella di controllo **Abilita mirroring dell'archivio SQL Server** . Eseguire questa operazione per l'archiviazione e il monitoraggio, se necessario. Fare clic su **OK**.
    
      - Fare clic con il pulsante destro del mouse sul nodo Lync Server 2013, scegliere **topologia**e quindi fare clic su **pubblica**.
    
      - Selezionare il back-end funzionante (BE2.contoso.com) in modo che sia il nuovo archivio SQL. A tale scopo, fare clic con il pulsante destro del mouse sul pool in pool **Enterprise Edition front end** e scegliere **modifica proprietà**. Nella scheda **generale** , in **associazioni**, digitare il nome di dominio completo del back-end funzionante nel campo **Archivio SQL Server** (in questo esempio, be2.contoso.com).
    
      - Fare clic con il pulsante destro del mouse sul nodo Lync Server 2013, scegliere **topologia**e quindi fare clic su **pubblica**.
    
      - Riavviare i servizi in modo che ogni server possa leggere la nuova topologia. Da una Lync Server Management Shell, eseguire i cmdlet seguenti in ogni front end server che appartiene al pool:
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  Disinstallazione del mirroring. Da una Lync Server Management Shell, eseguire il cmdlet seguente:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Ad esempio:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    Eseguire questa operazione per tutti i tipi di database sul server.

6.  Creare un server pulito o nuovo che abbia lo stesso nome di dominio completo (in questo esempio, DB1.contoso.com) del computer in cui si è verificato l'errore, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati. Questo server funzionerà come nuovo mirror.

7.  Accedere al nuovo server da un account utente membro del gruppo RTCUniversalServerAdmins.

8.  Installare SQL Server 2012 o SQL Server 2008 R2, mantenendo i nomi delle istanze identici a quelli precedenti all'errore.

9.  Accedere a un front end server da un account utente membro del gruppo RTCUniversalServerAdmins.

10. Utilizzare Generatore di topologie per installare il database mirror. Eseguire le operazioni seguenti:
    
      - Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.
    
      - Abilitare il mirroring sul server back-end. A tale scopo, fare clic con il pulsante destro del mouse sul pool in pool **Enterprise Edition front end** e scegliere **modifica proprietà**. Nella scheda **generale** , in **associazioni**Selezionare la casella di controllo **Abilita mirroring dell'archivio SQL Server** . Eseguire questa operazione anche per l'archiviazione e il monitoraggio, se necessario.
        
        Quindi, nel campo **Archivio SQL Server mirroring** , digitare il nome di dominio completo del nuovo server (in questo esempio, BE1.contoso.com). Fare clic su **OK**.
    
      - Fare clic con il pulsante destro del mouse sul nodo Lync Server 2013, scegliere **topologia**e quindi fare clic su **Installa database**.
    
      - Seguire la procedura guidata di **installazione del database** . Nella pagina **Crea database** selezionare i database che si desidera ricreare.
    
      - Seguire la procedura guidata fino a quando non viene visualizzata la richiesta, **creare il database mirror**. Selezionare il database che si desidera installare e completare il processo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

