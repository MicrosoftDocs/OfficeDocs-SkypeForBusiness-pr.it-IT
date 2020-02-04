---
title: Ripristino di un server back-end con mirroring Enterprise Edition-mirror
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84a7c5a2aa12c1599d16ec563d10e8f5147df400
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>Ripristino di un server back-end Enterprise Edition con mirroring in Lync Server 2013-mirror

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-19_

Se si ha un server back-end Enterprise Edition in una configurazione con mirroring e solo lo specchio non riesce, seguire le procedure descritte in questa sezione. Se sia il database primario che il mirror non riescono, vedere [ripristino di un server back-end Enterprise Edition in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Se solo il principale non riesce, vedere [ripristino di un server back-end Enterprise Edition con mirroring in Lync server 2013-primario](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md). Se il database che ospita l'archivio di gestione centrale non riesce, vedere [ripristino del server che ospita l'archivio di gestione centrale in Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Se un server membro di Enterprise Edition che non è il server back-end non riesce, vedere [ripristino di un server membro di Enterprise Edition in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema. È possibile usare questa immagine come punto di rollback, in caso di problemi durante il ripristino. Potrebbe essere necessario prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare di nuovo i certificati.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>Per ripristinare un database mirror di Enterprise Edition back end server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere a un server front-end.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Disinstallare il mirroring. Prima di tutto, digitare il seguente cmdlet:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Ad esempio:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    Eseguire questa operazione per tutti i tipi di database nel server.

4.  Creare un nuovo server pulito o con lo stesso nome di dominio completo (FQDN) (DB1.contoso.com) del computer non riuscito, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati. Questo server funzionerà come nuovo mirror.

5.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere al nuovo server.

6.  Installare SQL Server 2012 o SQL Server 2008 R2, mantenendo i nomi delle istanze come prima dell'errore.

7.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere a un server front-end.

8.  Usare generatore di topologie per installare il database mirror. Eseguire le operazioni seguenti:
    
      - Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.
    
      - Fare clic con il pulsante destro del mouse sul nodo Lync Server 2013, scegliere **topologia**e quindi fare clic su **Installa database**.
    
      - Seguire la procedura guidata **Installa database** . Nella pagina **Crea database** selezionare i database che si desidera ricreare.
    
      - Seguire la procedura guidata fino a quando non viene visualizzata una richiesta di **creazione di database mirror** . Selezionare il database che si vuole installare e completare il processo.
        
        <div>
        

        > [!TIP]
        > Invece di eseguire Generatore di topologie, puoi usare il cmdlet <STRONG>Install-CsMirrorDatabase</STRONG> per configurare il mirroring. Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

