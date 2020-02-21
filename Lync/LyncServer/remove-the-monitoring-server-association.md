---
title: Rimuovere l'associazione di Monitoring Server
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
ms.openlocfilehash: 0b7559fcd513dcc3695b587be24e220ad74847ef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a>Rimuovere l'associazione di Monitoring Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-04_

Per rimuovere il Monitoring Server, è necessario modificare o cancellare la dipendenza dal pool Front end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server. È possibile modificare le proprietà del pool Front End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologie, verrà eliminato anche l'oggetto archivio database associato in Generatore di topologie.

<div>

## <a name="to-remove-the-monitoring-server-association"></a>Per rimuovere l'associazione del Monitoring Server

1.  Aprire Lync Server 2013 front end server, aprire Generatore di topologie.

2.  Passare al nodo Lync Server 2010.

3.  In Generatore di topologie espandere **pool Enterprise Edition front end**, **Standard Edition Front End Server**o **siti di succursale**, in base alla posizione in cui è definito il Monitoring Server.

4.  Se è presente un Survivable Branch Server associato, espandere **siti**di succursale, espandere il nome del sito di succursale e quindi espandere **Survivable Branch Appliance**.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Survivable Branch Appliance</STRONG> nell'interfaccia utente si applica sia a Survivable Branch Server che a Survivable Branch Appliance.

    
    </div>

5.  Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al Monitoring Server e quindi scegliere **modifica proprietà**.

6.  In **Modifica proprietà**, in **Generale**, in **Associazioni**, deselezionare la casella di controllo **Associa Monitoring Server** e quindi fare clic su **OK**.

7.  Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al Monitoring Server.

8.  Fare clic con il pulsante destro del mouse su Monitoring Server e quindi scegliere **Elimina**.

9.  In **Elimina archivi dipendenti** fare clic su **OK**.

10. Pubblicare la topologia, controllare lo stato della replica ed eseguire la distribuzione guidata di Lync Server in base alle esigenze.

</div>

</div>

<span> </span>

</div>

</div>

</div>

