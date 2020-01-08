---
title: Verificare il completamento della replica utente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13f4fbd2e0d0236f9dc404ffa84ab2f0ce385e2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>Verificare il completamento della replica utente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

Quando si utilizza il cmdlet **Move-CsLegacyUser** , potrebbe verificarsi un errore a causa di informazioni utente tra servizi di dominio Active Directory e i database di Lync Server 2013 non sincronizzati perché la replica iniziale è incompleta. Il tempo necessario per il completamento della sincronizzazione iniziale di Lync Server 2013, dipende dal numero di controller di dominio ospitati nella foresta di Active Directory che ospita il pool di Lync Server 2013. Il processo di sincronizzazione iniziale di Lync Server 2013 User Replicator Service viene eseguito quando il server front-end di Lync Server 2013 viene avviato per la prima volta. Successivamente, la sincronizzazione si basa sull'intervallo User Replicator. Completare la procedura seguente per verificare che la replica degli utenti sia stata completata prima di eseguire il cmdlet **Move-CsLegacyUser** .

<div>

## <a name="to-verify-that-user-replication-has-completed"></a>Per verificare che la replica dell'utente sia stata completata

1.  Dal server front-end di Lync Server 2013 fare clic sul menu **Start** e quindi su **Esegui**.

2.  Immettere **eventvwr. exe** e quindi fare clic su **OK**.

3.  Nel Visualizzatore eventi fare clic su **registri applicazioni e servizi** per espanderlo e quindi selezionare Lync Server.

4.  Nel riquadro **azioni** fare clic su **Filtra log corrente**.

5.  Nell'elenco **origini eventi** fare clic su **LS User Replicator**.

6.  In ** \<tutti gli ID\> evento** immettere **30024** e quindi fare clic su **OK**.

7.  Nell'elenco eventi filtrati, nella scheda **generale** , cercare una voce che indica che la replica degli utenti è stata completata correttamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

