---
title: Connettere un Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b65eed74396eb7c373230358f29366f7d6d18e5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>Connettere un Survivable Branch Appliance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Ogni Survivable Branch Appliance (SBA) è associato a un pool Front end che funge da registrar di backup per la SBA. Quando si esegue la migrazione del pool Front end in Lync Server 2013, è necessario che l'SBA sia dissociata dal pool Front end Lync Server 2010 mentre il pool viene aggiornato, una volta che il pool è stato migrato a Lync Server 2013, l'SBA può essere riassociato al pool Front end aggiornato. Si tratta di eliminare l'ASB dalla topologia di Lync Server 2010 legacy in Generatore di topologie e quindi di aggiungere l'SBA alla topologia di Lync Server 2013. Gli utenti ospitati nell'ASB legacy di Lync Server 2010 devono essere prima spostati in un altro pool Front end prima di rimuovere la SBA dalla topologia. Dopo aver aggiunto l'SBA alla topologia di Lync Server 2013, gli utenti possono quindi essere spostati di nuovo nell'ASB. La procedura è sintetizzata sotto.

1.  Spostare gli utenti di succursale nell'legacy SBA Lync Server 2010 in un altro pool Front end.

2.  Rimuovere SBA dalla topologia di Lync Server 2010 legacy per disconnettere il pool Front end esistente come registrar di backup.

3.  Aggiungere SBA alla topologia di Lync Server 2013 e configurare questo nuovo pool Front end come registrazione di backup.

4.  Spostare gli utenti di succursale nella nuova SBA di Lync Server 2013.

**Aggiungere il sito di succursale del Survivable Branch Appliance di Lync Server 2010 alla topologia**

1.  Aprire **Generatore di topologie**.

2.  Nel riquadro sinistro fare clic con il pulsante destro del mouse su **Siti di succursale** e quindi fare clic su **Nuovo sito di succursale**.

3.  Nella finestra di dialogo **Definisci nuovo sito di succursale** fare clic su **Nome** e quindi digitare il nome del sito di succursale.

4.  (Facoltativo) Fare clic su **Descrizione** e quindi digitare una descrizione significativa del sito di succursale.

5.  Fare clic su **Avanti**.

6.  (Facoltativo) Nella successiva finestra di dialogo **Definisci nuovo sito di succursale** eseguire una delle operazioni seguenti:
    
    1.  Fare clic su **Città** e quindi digitare il nome della città in cui si trova il sito di succursale.
    
    2.  Fare clic su **Paese** e quindi digitare il nome del paese in cui si trova il sito di succursale.
    
    3.  Fare clic su **Codice paese** e quindi digitare il codice di chiamata in due cifre per il paese/area geografica in cui si trova il sito di succursale.

7.  Fare clic su **Avanti** e quindi eseguire una delle operazioni seguenti:
    
    1.  Se nel sito si utilizza un Survivable Branch Appliance o un Survivable Branch Server di Lync 2010, deselezionare l'opzione **Aprire la procedura guidata Nuovo Survivable Branch Appliance al termine di questa procedura guidata** e quindi fare clic su **Fine**.

8.  Per associare la SBA legacy Lync Server 2010 al pool Front End di Lync Server 2013:
    
    1.  Espandere il sito di succursale che è stato creato.
    
    2.  Fare clic con il pulsante destro del mouse su **Lync Server 2010** e quindi scegliere **Nuovo**.
    
    3.  Fare clic su **Survivable Branch Appliance…**

9.  Seguire le istruzioni nella procedura guidata visualizzata. Per informazioni sugli elementi della procedura guidata, vedere [define a Survivable Branch Appliance or server in Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
    <div>
    

    > [!NOTE]  
    > Un Survivable Branch Appliance di Lync Server 2010 può essere associato solo a un archivio di monitoraggio di Lync Server 2010.

    
    </div>

10. Se nel sito non si utilizza un Survivable Branch Appliance o un Survivable Branch Server, deselezionare la casella di controllo **Aprire la procedura guidata Nuovo Survivable Branch Appliance al termine di questa procedura guidata** e quindi fare clic su **Fine**.

11. Ripetere i passaggi precedenti per ogni sito di succursale che si desidera aggiungere alla topologia.

</div>

<span> </span>

</div>

</div>

</div>

