---
title: Rimuovere l'associazione del server di archiviazione
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3d9de311668bd43d913b0f746470235060bafe3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499973"
---
# <a name="remove-the-archiving-server-association"></a>Rimuovere l'associazione del server di archiviazione

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-04_

Per rimuovere un server di archiviazione, è necessario modificare o cancellare la dipendenza dal pool Front end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server. È possibile modificare le proprietà del pool Front End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza e aver eliminato il server in Generatore di topologie, viene notificato che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologie.

<div>

## <a name="to-remove-the-archiving-server-association"></a>Per rimuovere un'associazione a un server di archiviazione

1.  Aprire Lync Server 2013 front end server, aprire Generatore di topologie.

2.  Passare al nodo Lync Server 2010.

3.  In Generatore di topologie espandere **pool Enterprise Edition front end**, **Standard Edition Front End Server**o **siti di succursale**, in base alla posizione in cui è definito il server di archiviazione.

4.  Se è presente un Survivable Branch Server associato, espandere **siti**di succursale, espandere il nome del sito di succursale e quindi espandere **Survivable Branch Appliance**.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Survivable Branch Appliance</STRONG> nell'interfaccia utente si applica sia a Survivable Branch Server che a Survivable Branch Appliance.

    
    </div>

5.  Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al server di archiviazione, quindi scegliere **modifica proprietà**.

6.  In **Modifica proprietà**, **Generale**, **Associazioni** deselezionare la casella di controllo **Associa server di archiviazione** e quindi fare clic su **OK**.

7.  Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al server di archiviazione che si desidera rimuovere.

8.  Fare clic con il pulsante destro del mouse sul server di archiviazione e quindi scegliere **Elimina**.

9.  In **Elimina archivi dipendenti** fare clic su **OK**.

10. Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata di Lync Server in base alle esigenze.

</div>

</div>

<span> </span>

</div>

</div>

</div>

