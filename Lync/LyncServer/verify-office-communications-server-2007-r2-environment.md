---
title: Verificare l'ambiente Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a7b44ee656462510ad6a27cf2e11bae30608f0b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a>Verificare l'ambiente Office Communications Server 2007 R2

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-16_

Prima di distribuire Lync Server 2013 in uno stato di coesistenza con Office Communications Server 2007 R2, è necessario verificare che i servizi Office Communications Server 2007 R2 siano configurati e avviati.

**Verificare che il pool venga avviato utilizzando lo strumento di amministrazione di Office Communications Server 2007 R2**

1.  Aprire lo strumento di amministrazione di Office Communications Server 2007 R2.

2.  Espandere il nodo **Foresta**, il nodo **Server Standard** o **Pool Enterprise** e quindi il nome del pool o del server.

3.  Verificare che i servizi siano in esecuzione nel server Standard Edition o nel pool Enterprise.
    
    ![Console di amministrazione di Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Console di amministrazione di Office Communications Server 2007 R2")

**Controllare gli utenti configurati per Office Communications Server 2007 R2**

1.  Aprire lo strumento di amministrazione di Office Communications Server 2007 R2.

2.  Espandere il nodo **Foresta**, il nodo **Server Standard** o **Pool Enterprise** e quindi il nome del pool o del server.

3.  Fare clic su **Utenti**.

4.  Verificare l'elenco degli utenti di Office Communications Server 2007 R2.
    
    ![Elencare gli utenti di fo nello strumento di amministrazione di OCS](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Elencare gli utenti di fo nello strumento di amministrazione di OCS")

**Verificare la configurazione del partner federato XMPP legacy**

1.  Dal server XMPP legacy, accedere all'applet servizi di amministrazione\\degli strumenti.

2.  Verificare che il servizio Office Communications Server XMPP Gateway sia stato avviato.
    
    ![Servizio gateway XMPP di Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Servizio gateway XMPP di Office Communications Server")

</div>

<span> </span>

</div>

</div>

</div>

