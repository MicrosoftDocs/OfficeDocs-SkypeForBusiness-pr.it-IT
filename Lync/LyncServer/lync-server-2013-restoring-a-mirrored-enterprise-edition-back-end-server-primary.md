---
title: Ripristino di un server back-end Enterprise con mirroring-Primary
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbf0c8562ed4180fb14bf0bda74a03dd4ee8f746
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>Ripristino di un server back-end Enterprise Edition con mirroring in Lync Server 2013-primario

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-17_

Se si ha un server back-end Enterprise Edition in una configurazione con mirroring e solo il database principale non riesce, seguire le procedure descritte in questa sezione. Se sia il database primario che il mirror non riescono, vedere [ripristino di un server back-end Enterprise Edition in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Se solo lo specchio non riesce, vedere [ripristino di un server back-end Enterprise Edition con mirroring in Lync server 2013-mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md). Se il database che ospita l'archivio di gestione centrale non riesce, vedere [ripristino del server che ospita l'archivio di gestione centrale in Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Se un server membro di Enterprise Edition che non è il server back-end non riesce, vedere [ripristino di un server membro di Enterprise Edition in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema. È possibile usare questa immagine come punto di rollback, in caso di problemi durante il ripristino. Potrebbe essere necessario prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare di nuovo i certificati.

In questo argomento, il database primario di esempio avrà un nome di dominio completo (FQDN) di BE1.contoso.com e il database mirror avrà un FQDN di BE2.contoso.com.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>Per ripristinare un database primario del server back-end Enterprise Edition

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere a un server front-end.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Forzare il failover di tutti i database configurati allo specchio. Per ogni tipo di database configurato in questo server, digitare il cmdlet seguente:
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    Ad esempio:
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > Se il database back-end è stato configurato per usare il mirroring sincronizzato con un testimone, il failover è automatico.

    
    </div>

4.  Dopo aver completato il failover, eseguire le operazioni seguenti:
    
      - Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.
    
      - Disabilitare il mirroring sul server back-end: fare clic con il pulsante destro del mouse sul pool in pool **Enterprise Edition front-end** e scegliere **modifica proprietà**. Nella scheda **generale** , in **associazioni**, deselezionare la casella di controllo **Abilita mirroring di SQL Server Store** . Eseguire questa operazione per l'archiviazione e il monitoraggio, se necessario. Quindi fare clic su **OK**.
    
      - Fare clic con il pulsante destro del mouse sul nodo Lync Server 2013, scegliere **topologia**e quindi fare clic su **pubblica**.
    
      - Selezionare il backend ancora funzionante (BE2.contoso.com) come nuovo archivio SQL. A questo scopo, fai clic con il pulsante destro del mouse sul pool in pool di **front end di Enterprise Edition** e scegli **modifica proprietà**. Nella scheda **generale** , in **associazioni**, digitare il nome di dominio completo del backend funzionante nel campo **Archivio di SQL Server** (in questo esempio, be2.contoso.com).
    
      - Fare clic con il pulsante destro del mouse sul nodo Lync Server 2013, scegliere **topologia**e quindi fare clic su **pubblica**.
    
      - Riavviare i servizi in modo che ogni server possa leggere la nuova topologia. Da un Lync Server Management Shell eseguire i cmdlet seguenti in ogni server front-end che appartiene a questo pool:
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  Disinstallare il mirroring. Da un Lync Server Management Shell eseguire il cmdlet seguente:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Ad esempio:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    Eseguire questa operazione per tutti i tipi di database nel server.

6.  Creare un server pulito o nuovo con lo stesso nome di dominio completo (in questo esempio, DB1.contoso.com) come computer non riuscito, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati. Questo server funzionerà come nuovo mirror.

7.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere al nuovo server.

8.  Installare SQL Server 2012 o SQL Server 2008 R2, mantenendo i nomi delle istanze come prima dell'errore.

9.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere a un server front-end.

10. Usare generatore di topologie per installare mirror DB. Eseguire la procedura seguente:
    
      - Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.
    
      - Abilitare il mirroring sul server back-end. A questo scopo, fai clic con il pulsante destro del mouse sul pool in pool di **front end di Enterprise Edition** e scegli **modifica proprietà**. Nella scheda **generale** , in **associazioni**, selezionare la casella di controllo **Abilita mirroring di SQL Server Store** . Eseguire questa operazione anche per l'archiviazione e il monitoraggio, se necessario.
        
        Nel campo archivio di **SQL Server mirroring** Digitare quindi il nome di dominio completo del nuovo server (n questo esempio, BE1.contoso.com). Quindi fare clic su **OK**.
    
      - Fare clic con il pulsante destro del mouse sul nodo Lync Server 2013, scegliere **topologia**e quindi fare clic su **Installa database**.
    
      - Seguire la procedura guidata **Installa database** . Nella pagina **Crea database** selezionare i database che si desidera ricreare.
    
      - Seguire la procedura guidata fino a raggiungere il prompt, **creare un database mirror**. Selezionare il database che si vuole installare e completare il processo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

