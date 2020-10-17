---
title: Verificare il completamento della replica utente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b1ffd7b82b4addb24170644e227b11d50020043
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517993"
---
# <a name="verify-user-replication-has-completed"></a>Verificare il completamento della replica utente

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-17_

Quando si esegue il cmdlet **Move-CsUser** , è possibile che si verifichi un errore perché le informazioni degli utenti tra servizi di dominio Active Directory e i database di Lync Server 2013 non sono sincronizzate perché la replica iniziale è incompleta. Il tempo necessario per il corretto completamento della sincronizzazione iniziale del servizio Lync Server 2013 User Replicator dipende dal numero di controller di dominio ospitati nella foresta di Active Directory che ospita il pool di Lync Server 2013. Il processo di sincronizzazione iniziale di Lync Server 2013 User Replicator viene eseguito quando il server Lync Server 2013 front end è stato avviato per la prima volta. Successivamente la sincronizzazione viene basata sull'intervallo di User Replicator. Eseguire la procedura seguente per verificare che la replica degli utenti sia completata prima di eseguire il cmdlet **Move-CsUser**.

<div>

## <a name="to-verify-user-replication-has-completed"></a>Per verificare che la replica degli utenti sia stata completata

1.  Accedere al computer in cui è installato il Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Fare clic su **Start** e scegliere **Esegui**.

3.  Digitare **eventvwr.exe** e fare clic su **OK**.

4.  Nel Visualizzatore eventi fare clic su **Registri applicazioni e servizi** per espanderlo, quindi selezionare Lync Server

5.  Nel riquadro **Azioni** fare clic su **Filtro registro corrente**.

6.  Nell'elenco **Origini eventi** fare clic su **LS User Replicator**.

7.  In **\<All Event IDs\>** immettere **30024** e quindi fare clic su **OK**.

8.  Nella scheda **Generale** dell'elenco degli eventi filtrati cercare una voce in cui viene indicato che la replica utente è stata completata correttamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

