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
ms.openlocfilehash: 5ef6294deba25998c5ad16254e464b6f682fa660
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>Connettere un Survivable Branch Appliance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Ogni Survivable Branch Appliance (SBA) è associato a un pool Front-end che funge da registrar di backup per l'SBA. Quando il pool Front-end viene migrato a Lync Server 2013, l'SBA deve essere dissociato dal pool di front end di Lync Server 2010 mentre il pool viene aggiornato, dopo la migrazione del pool a Lync Server 2013, l'SBA può essere riassociato al pool Front-end aggiornato. Si tratta di eliminare l'ASB dalla topologia legacy di Lync Server 2010 in Generatore di topologia e quindi aggiungere l'ASB alla topologia di Lync Server 2013. Gli utenti ospitati nella SBA legacy Lync Server 2010 devono prima essere spostati in un altro pool Front-end prima di rimuovere l'SBA dalla topologia. Dopo aver aggiunto l'SBA alla topologia di Lync Server 2013, questi utenti possono quindi essere spostati di nuovo nella SBA. Questi passaggi sono riepilogati di seguito:

1.  Sposta gli utenti di Branch residenti nell'legacy SBA Lync Server 2010 in un altro pool Front-end.

2.  Rimuovere SBA dalla topologia legacy di Lync Server 2010 per disconnettere il pool Front end esistente come registrar di backup.

3.  Aggiungere SBA alla topologia di Lync Server 2013 e configurare il nuovo pool Front-end come registrar di backup.

4.  Trasferire gli utenti della filiale nel nuovo SBA di Lync Server 2013.

**Aggiungere il sito della filiale di Lync Server 2010 SBA alla topologia**

1.  Aprire **Generatore di topologie**.

2.  Nel riquadro sinistro fare clic con il pulsante destro del mouse su **siti di succursale**e quindi scegliere **nuovo sito filiale**.

3.  Nella finestra di dialogo **Definisci nuovo sito succursale** fare clic su **nome**e quindi digitare il nome del sito della filiale.

4.  Opzionale Fare clic su **Descrizione**e quindi digitare una descrizione significativa per il sito della filiale.

5.  Fare clic su **Avanti**.

6.  Opzionale Nella finestra di dialogo **Definisci nuovo sito della filiale** eseguire una delle operazioni seguenti:
    
    1.  Fare clic su **città**e quindi digitare il nome della città in cui si trova il sito della filiale.
    
    2.  Fare clic su **stato/area geografica**e quindi digitare il nome dello stato o dell'area geografica in cui si trova il sito della filiale.
    
    3.  Fare clic su **codice paese**e quindi digitare il codice di chiamata a due cifre per il paese/area geografica in cui si trova il sito della filiale.

7.  Fare clic su **Avanti**e quindi eseguire una delle operazioni seguenti:
    
    1.  Se si usa un server o un dispositivo Survivable Branch Lync 2010 in questo sito, deselezionare la casella di controllo **Apri la nuova procedura guidata per la procedura guidata** . Fare clic su **fine**.

8.  Per associare la SBA legacy di Lync Server 2010 al pool Front End di Lync Server 2013:
    
    1.  Espandere il sito della filiale che è stato creato.
    
    2.  Fare clic con il pulsante destro del mouse su **Lync Server 2010** e quindi scegliere **nuovo**.
    
    3.  Fare clic su **Survivable Branch Appliance..** .

9.  Seguire le indicazioni della procedura guidata visualizzata. Per informazioni sugli elementi della procedura guidata, vedere [definire un Survivable Branch Appliance o un server in Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
    <div>
    

    > [!NOTE]  
    > Un Survivable Branch Appliance di Lync Server 2010 può essere associato solo a un archivio di monitoraggio di Lync Server 2010.

    
    </div>

10. Se non si usa un Survivable Branch Appliance o un server in questo sito, deselezionare la casella di controllo **Apri la nuova procedura guidata per** la procedura guidata e quindi fare clic su **fine**.

11. Ripetere i passaggi precedenti per ogni sito di filiale che si vuole aggiungere alla topologia.

</div>

<span> </span>

</div>

</div>

</div>

