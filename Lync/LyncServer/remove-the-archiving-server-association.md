---
title: Rimuovere l'associazione del server di archiviazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ab171493890c610e0f11b7cd124c7c2e1c600c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a>Rimuovere l'associazione del server di archiviazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-04_

Per rimuovere un server di archiviazione, è necessario modificare o deselezionare la dipendenza dal pool Front-end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server. Si modificano le proprietà del pool Front-End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologia, viene visualizzato un avviso che l'oggetto archivio di database associato in Generatore di topologia verrà eliminata.

<div>

## <a name="to-remove-the-archiving-server-association"></a>Per rimuovere l'associazione del server di archiviazione

1.  Aprire il server front-end di Lync Server 2013, aprire Generatore di topologia.

2.  Passare al nodo Lync Server 2010.

3.  In Generatore di topologie espandere i **pool Front End di Enterprise Edition**, i **server front-end Standard Edition**o i **siti di succursale**in base alla posizione in cui è definito il server di archiviazione.

4.  Se si ha un Survivable Branch Server associato, espandere **siti di succursale**, espandere il nome del sito della filiale e quindi espandere **Survivable Branch Appliances**.
    
    <div>
    

    > [!NOTE]  
    > Gli <STRONG>elettrodomestici Survivable Branch</STRONG> nell'interfaccia utente si applicano sia a Survivable Branch Server che Survivable Branch Appliance.

    
    </div>

5.  Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al server di archiviazione e quindi scegliere **modifica proprietà**.

6.  In **modifica proprietà**, in **generale**, in **associazioni**deselezionare la casella di controllo **Associa server di archiviazione** e quindi fare clic su **OK**.

7.  Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al server di archiviazione che si vuole rimuovere.

8.  Fare clic con il pulsante destro del mouse sul server di archiviazione e quindi scegliere **Elimina**.

9.  In **eliminare gli archivi dipendenti**fare clic su **OK**.

10. Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata di Lync Server in base alle esigenze.

</div>

</div>

<span> </span>

</div>

</div>

</div>

