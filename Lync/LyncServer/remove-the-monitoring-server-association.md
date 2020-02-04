---
title: Rimuovere l'associazione del server di monitoraggio
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f26a809056674c231212db3f824a2ecb7ce7ecd1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a>Rimuovere l'associazione del server di monitoraggio

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-04_

Per rimuovere il server di monitoraggio, è necessario modificare o deselezionare la dipendenza dal pool Front-end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server. Si modificano le proprietà del pool Front-End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologia, viene segnalato che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologia.

<div>

## <a name="to-remove-the-monitoring-server-association"></a>Per rimuovere l'associazione del server di monitoraggio

1.  Aprire il server front-end di Lync Server 2013, aprire Generatore di topologia.

2.  Passare al nodo Lync Server 2010.

3.  In Generatore di topologie espandere i **pool Front End di Enterprise Edition**, i **server front-end Standard Edition**o i **siti di succursale**in base alla definizione del server di monitoraggio.

4.  Se si ha un Survivable Branch Server associato, espandere **siti di succursale**, espandere il nome del sito della filiale e quindi espandere **Survivable Branch Appliances**.
    
    <div>
    

    > [!NOTE]  
    > Gli <STRONG>elettrodomestici Survivable Branch</STRONG> nell'interfaccia utente si applicano sia a Survivable Branch Server che Survivable Branch Appliance.

    
    </div>

5.  Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al server di monitoraggio e quindi scegliere **modifica proprietà**.

6.  In **modifica proprietà**, in **generale**, in **associazioni**deselezionare la casella di controllo **Associa server di monitoraggio** e quindi fare clic su **OK**.

7.  Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al server di monitoraggio.

8.  Fare clic con il pulsante destro del mouse sul server di monitoraggio e quindi scegliere **Elimina**.

9.  In **eliminare gli archivi dipendenti**fare clic su **OK**.

10. Pubblicare la topologia, controllare lo stato di replica ed eseguire la distribuzione guidata di Lync Server in base alle esigenze.

</div>

</div>

<span> </span>

</div>

</div>

</div>

