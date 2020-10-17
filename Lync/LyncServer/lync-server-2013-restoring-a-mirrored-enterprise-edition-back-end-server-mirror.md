---
title: Ripristino di un mirroring del server back-end Enterprise Edition con mirroring
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
ms.openlocfilehash: 6e4bbb7d74c6bf660c69a15ff8250d95f04fed98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511583"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>Ripristino di un server back-end Enterprise Edition con mirroring in Lync Server 2013-mirror

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-19_

Se si dispone di un server back-end Enterprise Edition in una configurazione con mirroring e solo il mirror ha esito negativo, seguire le procedure descritte in questa sezione. Se il database primario e il mirror non riescono, vedere [Restoring an Enterprise Edition back end server in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Se solo l'operazione principale ha esito negativo, vedere [Restoring a mirroring Enterprise Edition back end server in Lync server 2013-Primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md). Se il database che ospita l'archivio di gestione centrale ha esito negativo, vedere [ripristino del server che ospita l'archivio di gestione centrale in Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Se si verifica un errore di un server membro Enterprise Edition che non è il server back-end, vedere [Restoring an Enterprise Edition member server in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema. È possibile utilizzare questa immagine come punto di rollback, in caso di problemi durante il ripristino. È possibile che si desideri prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare nuovamente i certificati.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>Per ripristinare un database mirror del server back-end Enterprise Edition

1.  Accedere a un front end server da un account utente membro del gruppo RTCUniversalServerAdmins.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Disinstallazione del mirroring. Per prima cosa, digitare il seguente cmdlet:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Ad esempio:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    Eseguire questa operazione per tutti i tipi di database sul server.

4.  Creare un server pulito o nuovo con lo stesso nome di dominio completo (FQDN) (DB1.contoso.com) del computer in cui si è verificato l'errore, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati. Questo server funzionerà come nuovo mirror.

5.  Accedere al nuovo server da un account utente membro del gruppo RTCUniversalServerAdmins.

6.  Installare SQL Server 2012 o SQL Server 2008 R2, mantenendo i nomi delle istanze identici a quelli precedenti all'errore.

7.  Accedere a un front end server da un account utente membro del gruppo RTCUniversalServerAdmins.

8.  Utilizzare Generatore di topologie per installare il database mirror. Eseguire le operazioni seguenti:
    
      - Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.
    
      - Fare clic con il pulsante destro del mouse sul nodo Lync Server 2013, scegliere **topologia**e quindi fare clic su **Installa database**.
    
      - Seguire la procedura guidata di **installazione del database** . Nella pagina **Crea database** selezionare i database che si desidera ricreare.
    
      - Seguire la procedura guidata fino a quando non viene visualizzata una richiesta di **creazione del database mirror** . Selezionare il database che si desidera installare e completare il processo.
        
        <div>
        

        > [!TIP]
        > Anziché eseguire Generatore di topologie, è possibile utilizzare il cmdlet <STRONG>Install-CsMirrorDatabase</STRONG> per configurare il mirroring. Per informazioni dettagliate, vedere la documentazione relativa a Lync Server Management Shell.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

